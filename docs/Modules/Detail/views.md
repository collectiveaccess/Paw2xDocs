---
sidebar_position: 3
---

# Views

Views for the `Details` module are defined in the theme `views/Details` directory.

The `ca_collections_default_html.php` file is in the Details module and is responsible for rendering the detailed view of a single collection. It provides a comprehensive overview of the selected collection, displaying its metadata and relationships.

The `ca_entities_default_html.php` file in the Details module renders the detailed view of a single entity. It provides the view to display metadata about an entity and its relationships.

The `ca_objects_default_html.php` file in the Details module renders the detailed view of an individual object. It provides a view to display metadata, related records, media and relationships associated with the object.

The `ca_objects_default_1column_html.php` file is a variation of `ca_objects_default_html.php` tailored for a single-column layout.

The `ca_occurrences_default_html.php` file in the Details module renders the detailed view of a specific occurrence. It provides a view to display metadata, related records, and relationships for an occurrence.

The `ca_places_default_html.php` file in the Details module is responsible for rendering the detailed view of a specific place. It provides a view for displaying metadata and relationships for a place.

The `representation_viewer_html.php` file is responsible for displaying media representations associated with a record in CollectiveAccess. It provides a media viewer with controls for navigation, zooming, downloading, and an overlay mode for full-screen viewing.

Within the Details view directory is a sub directory called `snippets`, currently containing reusable pieces of code for the various detail views.
    - The `related_entities_by_rel_type_html.php` snippet generates a list of related entities for the current item and groups them by relationship type. It retrieves related entities, organizes them based on their relationship type, and outputs a list of links to the related entities.
    - The `copy_link_html.php` snippet provides functionality for copying the current page's URL to the clipboard. It includes a button to trigger the copy action and displays a modal notification confirming the action.
    - The `lightbox_list_html.php` snippet is designed to manage and display the list of lightboxes associated with a specific item.

## Variables for `ca_collections_default_html.php`

| Variable                | Description                                                                                   |
|-------------------------|-----------------------------------------------------------------------------------------------|
| `item`                  | The collection item being rendered.                                                          |
| `access_values`         | Stores access permissions for visibility of collection data.                      |
| `config_options`        | Configuration options for rendering the collection details.                                   |
| `comments`              | User comments associated with the collection.                                                |
| `tags_array`            | Array of tags associated with the collection.                                                |
| `commentsEnabled`       | Boolean indicating whether comments are enabled for the collection.                           |
| `pdfEnabled`            | Boolean indicating whether PDF export is enabled for the collection.                          |
| `inquireEnabled`        | Boolean indicating whether the inquire action is enabled for the collection.                  |
| `copyLinkEnabled`       | Boolean indicating whether the copy link action is enabled for the collection.                |
| `id`                    | The ID of the current collection being rendered.                                              |
| `previousLink`          | Link to previous record.                             |
| `resultsLink`           | Link to collection results.                             |
| `nextLink`              | Link to next record.                             |
| `mapOptions`            | Array of options for rendering a map.                         |

## Variables for `ca_entities_default_html.php`

| Variable             | Description                                                                                   |
|----------------------|-----------------------------------------------------------------------------------------------|
| `item`               | The entity item being rendered.                                                              |
| `access_values`      | Stores access permissions for visibility of entity data.                          |
| `config_options`     | Configuration options for rendering the entity details.                                       |
| `comments`           | User comments associated with the entity.                                                    |
| `tags_array`         | Array of tags associated with the entity.                                                    |
| `commentsEnabled`    | Boolean indicating whether comments are enabled for the entity.                               |
| `pdfEnabled`         | Boolean indicating whether PDF export is enabled for the entity.                              |
| `inquireEnabled`     | Boolean indicating whether the inquire action is enabled for the entity.                      |
| `copyLinkEnabled`    | Boolean indicating whether the copy link action is enabled for the entity.                    |
| `id`                 | The ID of the current entity being rendered.                                                 |
| `previousLink`       | Link to previous record.                                      |
| `resultsLink`        | Link to collection results.                             |
| `nextLink`           | Link to next record.                             |
| `mapOptions`         | Array of options for rendering a map.                         |


## Variables for `ca_objects_default_html.php`

| Variable                | Description                                                                                   |
|-------------------------|-----------------------------------------------------------------------------------------------|
| `item`                 | The object item being rendered.                                                              |
| `access_values`        | Stores access permissions for visibility of object data.                          |
| `config_options`       | Configuration options for rendering the object details.                                       |
| `comments`             | User comments associated with the object.                                                    |
| `tags_array`           | Array of tags associated with the object.                                                    |
| `commentsEnabled`      | Boolean indicating whether comments are enabled for the object.                               |
| `pdfEnabled`           | Boolean indicating whether PDF export is enabled for the object.                              |
| `inquireEnabled`       | Boolean indicating whether the inquire action is enabled for the object.                      |
| `copyLinkEnabled`      | Boolean indicating whether the copy link action is enabled for the object.                    |
| `id`                   | The primary key of the current object being rendered.                                         |
| `previousLink`         | Link to previous record.                                      |
| `resultsLink`          | Link to collection results.                             |
| `nextLink`             | Link to next record.                             |
| `mapOptions`           | Array of options for rendering a map.                         |
| `media_options`        | Options for rendering the media viewer.                                         |
| `lightboxes`           | Array of lightboxes the object can be added to.                               |
| `inLightboxes`         | Array of lightboxes the object is already included within.   |


## Variables for `ca_occurrences_default_html.php`

| Variable             | Description                                                                                   |
|----------------------|-----------------------------------------------------------------------------------------------|
| `item`               | The occurrence item being rendered.                                                          |
| `access_values`      | Stores access permissions for visibility of occurrence data.                      |
| `config_options`     | Configuration options for rendering the occurrence details.                                   |
| `comments`           | User comments associated with the occurrence.                                                |
| `tags_array`         | Array of tags associated with the occurrence.                                                |
| `commentsEnabled`    | Boolean indicating whether comments are enabled for the occurrence.                           |
| `pdfEnabled`         | Boolean indicating whether PDF export is enabled for the occurrence.                          |
| `inquireEnabled`     | Boolean indicating whether the inquire action is enabled for the occurrence.                  |
| `copyLinkEnabled`    | Boolean indicating whether the copy link action is enabled for the occurrence.                |
| `id`                 | The ID of the current occurrence being rendered.                                              |
| `previousLink`       | Link to previous record.                                      |
| `resultsLink`        | Link to collection results.                             |
| `nextLink`           | Link to next record.                             |
| `mapOptions`         | Array of options for rendering a map.                         |


## Variables for `ca_places_default_html.php`

| Variable             | Description                                                                                   |
|----------------------|-----------------------------------------------------------------------------------------------|
| `item`               | The place item being rendered.                                                               |
| `access_values`      | Stores access permissions for visibility of place data.                           |
| `config_options`     | Configuration options for rendering the place details.                                        |
| `comments`           | User comments associated with the place.                                                     |
| `tags_array`         | Array of tags associated with the place.                                                     |
| `commentsEnabled`    | Boolean indicating whether comments are enabled for the place.                                |
| `pdfEnabled`         | Boolean indicating whether PDF export is enabled for the place.                               |
| `inquireEnabled`     | Boolean indicating whether the inquire action is enabled for the place.                       |
| `copyLinkEnabled`    | Boolean indicating whether the copy link action is enabled for the place.                     |
| `id`                 | The ID of the current place being rendered.                                                  |
| `previousLink`       | Link to previous record.                                      |
| `resultsLink`        | Link to collection results.                             |
| `nextLink`           | Link to next record.                             |
| `mapOptions`         | Array of options for rendering a map.                         |


## Variables for `related_entities_by_rel_type_html.php`

| Variable            | Description                                                                                   |
|---------------------|-----------------------------------------------------------------------------------------------|
| `item`           | The current item being processed.                  |
| `access_values` | Stores access permissions for visibility of related entities.                     |
| `restrict_to_relationship_types` | Restricts the retrieval of related entities to specific relationship types. |

## Variables for `lightbox_list_html.php`

| Variable                       | Description                                                                                |
|--------------------------------|--------------------------------------------------------------------------------------------|
| `in_lightboxes`                | Array of lightboxes that already include the current item.                                 |
| `errors`                       | Array of error messages.                                                         |
| `success`                      | Success message when a lightbox action is successfully.                   |
| `lightbox_conf`                | Configuration for lightboxes.                                  |
| `lightboxes`                   | List of all available lightboxes for the dropdown menu.                            |
| `item`                         | The current item being processed.                               |
| `id`                           | The primary key of the current item.                                                       |
| `lightbox_displayname_singular`| Singular display name for a lightbox.                                  |
| `lightbox_displayname_plural`  | Plural display name for lightboxes.                                   |
| `lightbox_icon`                | Icon used for lightbox buttons.                                                            |
| `not_in_lightbox_template`     | Template for the "Add to lightbox" option.                                                 |
| `in_lightbox_template`         | Template for the "Remove from lightbox" option.                                            |

## Variables for `representation_viewer_html.php`

| Variable            | Description                                                                  |
|---------------------|------------------------------------------------------------------------------|
| `media_list`       | Media items associated with the current record. |
| `media_viewers`    | HTML elements for displaying different media formats. |
| `media_viewer_overlays` | HTML content for media overlays. |
| `subject`          | Represents the subject whose media is being displayed. |


