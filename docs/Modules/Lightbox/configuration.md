---
sidebar_position: 2
---

# Configuration

This section describes the configuration options for the lightbox feature.

## Lightbox Display Names

These settings define the display names used for the lightbox section:

| Option                      | Explanation                                 | Example         |
|-----------------------------|---------------------------------------------|-----------------|
| `lightbox_displayname_singular` | Singular display name for the lightbox section. | `lightbox`      |
| `lightbox_displayname_plural`   | Plural display name for the lightbox section.   | `lightboxes`    |

## Detail View Configuration

These options control the templates used for adding/removing items from the lightbox in the detail view:

| Option                     | Explanation                                       | Example                                                                                 |
|----------------------------|---------------------------------------------------|-----------------------------------------------------------------------------------------|
| `not_in_lightbox_template` | Template for items not in the lightbox.           | `<i class='bi bi-bag-dash'></i> ^ca_sets.preferred_labels.name`                         |
| `in_lightbox_template`     | Template for items already in the lightbox.       | `<i class='bi bi-bag-check-fill'></i> ^ca_sets.preferred_labels.name`                   |
| `lightbox_description_element_code` | Element code used for the lightbox description. | `set_description`                                                                       |

## Sorting Options

The `lightbox_options` object provides sorting options for items in the lightbox:

```plaintext
lightbox_options = {
	ca_objects = {
		sorts = {
			Identifier = ca_objects.idno,
			Title = ca_object_labels.name
		},
		sort_directions = {
			Identifier = asc,
			Title = desc
		},
	}
}
```

### Explanation of Sorting Options

| Option                      | Explanation                                  | Example           |
|-----------------------------|----------------------------------------------|-------------------|
| `sorts.Identifier`          | Sorts items by their identifier.            | `ca_objects.idno` |
| `sorts.Title`               | Sorts items by their title.                 | `ca_object_labels.name` |
| `sort_directions.Identifier`| Sorting direction for identifiers.          | `asc`             |
| `sort_directions.Title`     | Sorting direction for titles.               | `desc`            |





| Option Name   | Explanation  | Example  |
| --- | --- | --- |
|  |   |  |
|  |   |  |
|  |   |  |
|  |   |  |