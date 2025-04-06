# media_metadata.conf

The `media_metadata.conf` file controls how metadata is added to media files. It allows you to turn metadata embedding on or off, which can help with performance when handling large media sets. The file sets up export mappings that fill in details like titles, descriptions, copyright info, and identifiers using IPTC and XMP metadata standards. These mappings apply to specific types of media, with a fallback __default__ setting for anything not specifically defined. This ensures that downloaded media files include important information directly in their metadata, making them more useful.

## General Options

| Option                 | Explanation                                                            | Example |
|------------------------|------------------------------------------------------------------------|---------|
| `do_metadata_embedding` | Enables or disables embedding metadata into media files. Setting this to `0` disables metadata embedding.  | `do_metadata_embedding = 1` |
| `export_mappings`      | Defines how metadata should be embedded into media files. Mappings are specified per table and type.   | See nested table below. |

### `export_mappings` Nested Configuration

| Option                 | Explanation                                                             | Example |
|------------------------|-------------------------------------------------------------------------|---------|
| `ca_objects`           | Specifies metadata embedding rules for objects. | `{ ca_objects = { ... } }` |
| `__default__`          | Fallback rule that applies when a specific object type does not have a defined mapping. | `{ __default__ = { ... } }` |
| `XMP:Title`            | Embeds the title of the media file.    | `XMP:Title = "^ca_objects.preferred_labels.name"` |
| `XMP:Copyright`        | Embeds copyright information into the media file.    | `XMP:Copyright = "©2025 Cecily Brown Studio"` |
| `XMP:Description`      | Embeds the description of the object  | `XMP:Description = "media object"` |
| `XMP:Identifier`       | Embeds the object’s identifier into the metadata.   | `XMP:Identifier = "^ca_objects.idno"` |
| `XMP:createdate`       | Embeds the object's creation date in metadata.   | `XMP:createdate = "^ca_objects.date_container.date"` |
| `XMP:Metadatadate`     | Records the date the metadata was last modified.   | `XMP:Metadatadate => "xmp:MetadataDate"` |
| `IPTC:Headline`        | Embeds the object's title as the media file’s headline. | `IPTC:Headline = "^ca_objects.preferred_labels.name"` |
| `IPTC:Credit`          | Embeds credit line information in the media file.  | `IPTC:Credit = "^ca_objects.credit_line"` |
| `IPTC:CopyrightNotice` | Embeds a copyright notice for the media file.  | `IPTC:CopyrightNotice = "©2025 Cecily Brown Studio"` |
| `IPTC:Source`          | Embeds the entity responsible for the object.  | `IPTC:Source = "<unit relativeTo='ca_entities' restrictToRelationshipTypes='source'>^ca_entities.preferred_labels.displayname</unit>"` |
| `IPTC:Contact`         | Embeds contact information in the media file. | `IPTC:Contact = "info@myorganization.org"` |
| `IPTC:Caption-Abstract`| Embeds the object's description in the media file’s metadata.  | `IPTC:Caption-Abstract = "^ca_objects.description"` |

### Sample Configuration

```
do_metadata_embedding = 1

export_mappings = {
	ca_objects = {
		__default__ = {
		    XMP:Title = "^ca_objects.preferred_labels.name",
		    XMP:Copyright = "©2025 Studio",
			XMP:Description = "<div>
                            <ifdef code='ca_objects.dimensions_container.display_dimensions'>Dimensions: ^ca_objects.dimensions_container.display_dimensions <br></ifdef>
                            <ifdef code='ca_objects.medium'>Medium: ^ca_objects.medium <br></ifdef>
                            <ifdef code='ca_objects.work_type'>Work Type: ^ca_objects.work_type <br></ifdef>
                            <ifdef code='ca_objects.description'>Description: ^ca_objects.description</ifdef>
		        </div>",
                    XMP:Identifier = "^ca_objects.idno",
                    XMP:createdate = "^ca_objects.date_container.date",
                    XMP:Metadatadate => "xmp:MetadataDate",
		    IPTC:Headline = "^ca_objects.preferred_labels.name",
		    IPTC:Credit = "^ca_objects.credit_line",
		    IPTC:CopyrightNotice = "©2025 Studio",
		    IPTC:Source = "<unit relativeTo='ca_entities' restrictToRelationshipTypes='source'>^ca_entities.preferred_labels.displayname</unit>",
		    IPTC:Contact = "info@myorganization.org",
		    IPTC:Caption-Abstract = "^ca_objects.description",

		}
	}
}
```