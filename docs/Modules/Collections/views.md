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
| `collections_config`      | Holds the configuration settings for the collections module.                |
| `collection_results`      | Stores the query results for collections to be displayed.                   |
| `access_values`           | Stores the access permissions for the content.                              |
| `landing_page_item_image_format`      | Specifies the format of the image (e.g., `contain` or `cover`). |
| `vs_image_class`          | Defines the CSS class for styling images based on the selected format.      |
| `landing_page_item_display_template`  | Holds the template for displaying collection items.             |
| `landing_page_intro_text_global_value`| Introductory text configuration for the landing page.           |

## Variables for `child_list_html.php`

| Variable                          | Description                                                                                   |
|-----------------------------------|-----------------------------------------------------------------------------------------------|
| `access_values`               | Stores the access permissions for the content.                                                |
| `collections_config`           | Holds the configuration settings for the collections module.                                  |
| `description_template`               | Template used to render the collection description.                                           |
| `item`                         | The current item being processed                                                              |
| `collection_id`               | ID of the current collection being rendered.                                                  |
| `exclude_collection_type_ids` | Array of collection type IDs that should be excluded.                                         |
| `non_linkable_collection_type_ids` | Array of collection type IDs that should not link to detail pages.                       |
| `collection_type_icons`       | Array mapping collection type IDs to their corresponding icons for display.                   |
| `collapse_levels`             |                      |
| `po_request`                     |                             |
| `va_collection_ids`              | Array of collection IDs to be displayed at the current level.                                 |
| `o_config`                       |                                      |
| `vn_level`                       | Indicates the current level of the hierarchy being rendered.                                  |
| `va_options`                     | Array of options          |
| `qr_collections`                 | Stores the query results for collections to be displayed.                          |
| `vs_output`                      | Accumulates the HTML for collections.                           |
| `vn_rel_object_count`            | Number of related objects linked to the current collection.                                   |
| `ca_collections.children.collection_id` | Array of child collection IDs for the current collection.                              |


## Variables for `collection_hierarchy_html.php`

| Variable                          | Description                                                                                   |
|-----------------------------------|-----------------------------------------------------------------------------------------------|
| `access_values`               | Stores the access permissions for the content.                                                |
| `collections_config`           | Holds the configuration settings for the collections module.                                  |
| `description_template`               | Template used to render the collection description.                                           |
| `item`                         | The current item being processed.                                                             |
| `collection_id`               | ID of the current collection being rendered.                                                  |
| `exclude_collection_type_ids` | Array of collection type IDs that should be excluded.                            |
| `non_linkable_collection_type_ids` | Array of collection type IDs that should not link to detail pages.                       |
| `collection_type_icons`       | Array mapping collection type IDs to their corresponding icons for display.                   |
| `vb_has_children`                | Boolean indicating whether the current collection has child collections.                      |
| `vb_has_grandchildren`           | Boolean indicating whether the current collection has grandchild collections.                 |
| `va_collection_children`         | Array of child collection IDs for the current collection.                                     |
| `qr_collection_children`         | Query result object containing data for child collections.                                    |
| `va_grand_children_type_ids`     | Array of type IDs for the grandchildren of the current collection.                            |
| `vn_rel_object_count`            | Number of related objects linked to the current collection.                                   |
| `vs_record_count`                | The count of related objects for a collection.                       |
| `vb_link_to_detail`              | Boolean indicating whether the collection links to a detail page.                             |