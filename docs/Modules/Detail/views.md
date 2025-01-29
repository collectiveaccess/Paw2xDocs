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

Within the Details view directory is a sub directory called `snippets`, currently containing reusable pieces of code for the various detail views.
    - The `related_entities_by_rel_type_html.php` snippet generates a list of related entities for the current item and groups them by relationship type. It retrieves related entities, organizes them based on their relationship type, and outputs a list of links to the related entities.
    - The `copy_link_html.php` snippet provides functionality for copying the current page's URL to the clipboard. It includes a button to trigger the copy action and displays a modal notification confirming the action.
    - The `lightbox_list_html.php` snippet is designed to manage and display the list of lightboxes associated with a specific item.

## Variables for `ca_collections_default_html.php`

| Variable                | Description                                                                                   |
|-------------------------|-----------------------------------------------------------------------------------------------|
| `$t_item`               | The collection item being rendered.                                                          |
| `$access_values`        | Stores access permissions for visibility of collection data.                      |
| `$options`              | Configuration options for rendering the collection details.                                   |
| `$comments`             | User comments associated with the collection.                                                |
| `$tags`                 | Array of tags associated with the collection.                                                |
| `$comments_enabled`     | Boolean indicating whether comments are enabled for the collection.                           |
| `$pdf_enabled`          | Boolean indicating whether PDF export is enabled for the collection.                          |
| `$inquire_enabled`      | Boolean indicating whether the inquire action is enabled for the collection.                  |
| `$copy_link_enabled`    | Boolean indicating whether the copy link action is enabled for the collection.                |
| `$id`                   | The ID of the current collection being rendered.                                              |
| `$show_nav`             | Boolean indicating whether navigation controls should be displayed.                             |
| `$map_options`          | Array of options for rendering a map.                         |
| `$collections_config`   | Configuration object for the collections module.                                              |
| `$show_hierarchy_viewer`| Boolean indicating whether the hierarchy viewer should be displayed.                          |
| `$top_level_collection_id` | The ID of the top-level parent in the collection hierarchy.  |


## Variables for `ca_entities_default_html.php`

| Variable                | Description                                                                                   |
|-------------------------|-----------------------------------------------------------------------------------------------|
| `$t_item`               | The entity item being rendered.                                                              |
| `$access_values`        | Stores access permissions for visibility of entity data.                          |
| `$options`              | Configuration options for rendering the entity details.                                       |
| `$comments`             | User comments associated with the entity.                                                    |
| `$tags`                 | Array of tags associated with the entity.                                                    |
| `$comments_enabled`     | Boolean indicating whether comments are enabled for the entity.                               |
| `$pdf_enabled`          | Boolean indicating whether PDF export is enabled for the entity.                              |
| `$inquire_enabled`      | Boolean indicating whether the inquire action is enabled for the entity.                      |
| `$copy_link_enabled`    | Boolean indicating whether the copy link action is enabled for the entity.                    |
| `$id`                   | The ID of the current entity being rendered.                                                 |
| `$show_nav`             | Boolean indicating whether navigation controls should be displayed. |
| `$map_options`          | Array of options for rendering a map.                         |


## Variables for `ca_objects_default_html.php`

| Variable                | Description                                                                                   |
|-------------------------|-----------------------------------------------------------------------------------------------|
| `$t_object`             | The object item being rendered.                                                              |
| `$access_values`        | Stores access permissions for visibility of object data.                          |
| `$options`              | Configuration options for rendering the object details.                                       |
| `$comments`             | User comments associated with the object.                                                    |
| `$tags`                 | Array of tags associated with the object.                                                    |
| `$comments_enabled`     | Boolean indicating whether comments are enabled for the object.                               |
| `$pdf_enabled`          | Boolean indicating whether PDF export is enabled for the object.                              |
| `$inquire_enabled`      | Boolean indicating whether the inquire action is enabled for the object.                      |
| `$copy_link_enabled`    | Boolean indicating whether the copy link action is enabled for the object.                    |
| `$id`                   | The primary key of the current object being rendered.                                         |
| `$show_nav`             | Boolean indicating whether navigation controls should be displayed.         |
| `$map_options`          | Array of options for rendering a map.                         |
| `$media_options`        | Configuration options for rendering the media viewer.                                         |
| `$lightboxes`           | Array of lightboxes the object can be added to.                               |
| `$in_lightboxes`        | Array of lightboxes the object is already included within.   |


## Variables for `ca_occurrences_default_html.php`

| Variable                | Description                                                                                   |
|-------------------------|-----------------------------------------------------------------------------------------------|
| `$t_item`               | The occurrence item being rendered.                                                          |
| `$access_values`        | Stores access permissions for visibility of occurrence data.                      |
| `$options`              | Configuration options for rendering the occurrence details.                                   |
| `$comments`             | User comments associated with the occurrence.                                                |
| `$tags`                 | Array of tags associated with the occurrence.                                                |
| `$comments_enabled`     | Boolean indicating whether comments are enabled for the occurrence.                           |
| `$pdf_enabled`          | Boolean indicating whether PDF export is enabled for the occurrence.                          |
| `$inquire_enabled`      | Boolean indicating whether the inquire action is enabled for the occurrence.                  |
| `$copy_link_enabled`    | Boolean indicating whether the copy link action is enabled for the occurrence.                |
| `$id`                   | The ID of the current occurrence being rendered.                                              |
| `$show_nav`             | Boolean indicating whether navigation controls should be displayed. |
| `$map_options`          | Array of options for rendering a map.                         |


## Variables for `ca_places_default_html.php`

| Variable                | Description                                                                                   |
|-------------------------|-----------------------------------------------------------------------------------------------|
| `$t_item`               | The place item being rendered.                                                               |
| `$access_values`        | Stores access permissions for visibility of place data.                           |
| `$options`              | Configuration options for rendering the place details.                                        |
| `$comments`             | User comments associated with the place.                                                     |
| `$tags`                 | Array of tags associated with the place.                                                     |
| `$comments_enabled`     | Boolean indicating whether comments are enabled for the place.                                |
| `$pdf_enabled`          | Boolean indicating whether PDF export is enabled for the place.                               |
| `$inquire_enabled`      | Boolean indicating whether the inquire action is enabled for the place.                       |
| `$copy_link_enabled`    | Boolean indicating whether the copy link action is enabled for the place.                     |
| `$id`                   | The ID of the current place being rendered.                                                  |
| `$show_nav`             | Boolean indicating whether navigation controls should be displayed. |
| `$map_options`          | Array of options for rendering a map.                         |


## Variables for `related_entities_by_rel_type_html.php`

| Variable                | Description                                                                                   |
|-------------------------|-----------------------------------------------------------------------------------------------|
| `$t_item`           | The current item being processed.                  |
| `$va_access_values` | Stores access permissions for visibility of related entities.                     |
| `$va_restrict_to_relationship_types` | Restricts the retrieval of related entities to specific relationship types. |
| `$va_entities`      | Array of related entities retrieved based on the configured parameters.                       |
| `$va_entities_by_type`| Array grouping related entities by their `relationship_typename`.                             |
| `$va_entity_links`    | Array of generated HTML links for entities within a specific relationship type group.         |
| `$vs_type`            | The name of the relationship type (e.g., "Creator", "Contributor").                          |


## Variables for `lightbox_list_html.php`

| Variable                        | Description                                                                                |
|---------------------------------|--------------------------------------------------------------------------------------------|
| `$in_lightboxes`                | Array of lightboxes that already include the current item.                                 |
| `$errors`                       | Array of error messages.                                                         |
| `$success`                      | Success message when a lightbox action is successfully.                   |
| `$lightbox_conf`                | Configuration for lightboxes.                                  |
| `$lightboxes`                   | List of all available lightboxes for the dropdown menu.                            |
| `$t_item`                       | The current item being processed.                               |
| `$id`                           | The primary key of the current item.                                                       |
| `$lightbox_displayname_singular` | Singular display name for a lightbox.                                  |
| `$lightbox_displayname_plural`  | Plural display name for lightboxes.                                   |
| `$lightbox_icon`                | Icon used for lightbox buttons.                                                            |
| `$not_in_lightbox_template`     | Template for the "Add to lightbox" option.                                                 |
| `$in_lightbox_template`         | Template for the "Remove from lightbox" option.                                            |



