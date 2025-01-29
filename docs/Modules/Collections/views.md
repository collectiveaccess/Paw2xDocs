---
sidebar_position: 3
---

# Views

Views for the `Collections` module are defined in the themes `views/Collections` directory.

The `index_html.php` file defines the layout and behavior for displaying the main landing page of the collections module.

The `child_list_html.php` file handles the hierarchical display of child collections within the collections module, allowing users to view collections and their nested children.

The `collection_hierarchy_html.php` file renders the hierarchy view for the collections module. It displays collections, their child collections, and grandchildren collections in a nested, hierarchical format.

## Variables for `index_html.php`

| Variable                  | Description                                                                 |
|---------------------------|-----------------------------------------------------------------------------|
| `$o_collections_config`   | Holds the configuration settings for the collections module.                |
| `$qr_collections`         | Stores the query results for collections to be displayed.                   |
| `$va_access_values`       | Stores the access permissions for the content.                              |
| `$vs_image_format`        | Specifies the format of the image (e.g., `contain` or `cover`).             |
| `$vs_image_class`         | Defines the CSS class for styling images based on the selected format.      |
| `$vs_item_display_template` | Holds the template for displaying collection items.                       |
| `$vs_intro_global_value`  | Introductory text configuration for the landing page.                       |

## Variables for `child_list_html.php`

| Variable                          | Description                                                                                   |
|-----------------------------------|-----------------------------------------------------------------------------------------------|
| `$va_access_values`               | Stores the access permissions for the content.                                                |
| `$o_collections_config`           | Holds the configuration settings for the collections module.                                  |
| `$vs_desc_template`               | Template used to render the collection description.                                           |
| `$t_item`                         | The current item being processed                                                              |
| `$vn_collection_id`               | ID of the current collection being rendered.                                                  |
| `$va_exclude_collection_type_ids` | Array of collection type IDs that should be excluded.                                         |
| `$va_non_linkable_collection_type_ids` | Array of collection type IDs that should not link to detail pages.                       |
| `$va_collection_type_icons`       | Array mapping collection type IDs to their corresponding icons for display.                   |
| `$vb_collapse_levels`             |                      |
| `$po_request`                     |                             |
| `$va_collection_ids`              | Array of collection IDs to be displayed at the current level.                                 |
| `$o_config`                       |                                      |
| `$vn_level`                       | Indicates the current level of the hierarchy being rendered.                                  |
| `$va_options`                     | Array of options          |
| `$qr_collections`                 | Stores the query results for collections to be displayed.                          |
| `$vs_output`                      | Accumulates the HTML for collections.                           |
| `$vn_rel_object_count`            | Number of related objects linked to the current collection.                                   |
| `$va_child_ids`                   | Array of child collection IDs for the current collection.                                     |
| `$vb_link`                        |                |
| `$vb_collapse_link`               |  |
| `$vs_icon`                        | Icon for the collection.                                                  |
| `$vs_desc`                        | Description for the collection.                      |

## Variables for `collection_hierarchy_html.php`

| Variable                          | Description                                                                                   |
|-----------------------------------|-----------------------------------------------------------------------------------------------|
| `$va_access_values`               | Stores the access permissions for the content.                                                |
| `$o_collections_config`           | Holds the configuration settings for the collections module.                                  |
| `$vs_desc_template`               | Template used to render the collection description.                                           |
| `$t_item`                         | The current item being processed.                                                             |
| `$vn_collection_id`               | ID of the current collection being rendered.                                                  |
| `$va_exclude_collection_type_ids` | Array of collection type IDs that should be excluded.                            |
| `$va_non_linkable_collection_type_ids` | Array of collection type IDs that should not link to detail pages.                       |
| `$va_collection_type_icons`       | Array mapping collection type IDs to their corresponding icons for display.                   |
| `$vb_has_children`                | Boolean indicating whether the current collection has child collections.                      |
| `$vb_has_grandchildren`           | Boolean indicating whether the current collection has grandchild collections.                 |
| `$va_collection_children`         | Array of child collection IDs for the current collection.                                     |
| `$qr_collection_children`         | Query result object containing data for child collections.                                    |
| `$va_grand_children_type_ids`     | Array of type IDs for the grandchildren of the current collection.                            |
| `$vb_link_sublist`                |                            |
| `$vn_rel_object_count`            | Number of related objects linked to the current collection.                                   |
| `$vs_record_count`                | The count of related objects for a collection.                       |
| `$vb_link_to_detail`              | Boolean indicating whether the collection links to a detail page.                             |
| `$vs_icon`                        | Icon for the collection.                                                  |
