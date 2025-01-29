---
sidebar_position: 2
---

# Configuration
The collections.conf file configures the behavior and appearance of the Collections module, including settings for the landing page, collection hierarchy browser, and PDF exports.

|Option                 | Explanation                                | Example                               |
|-----------------------|--------------------------------------------|---------------------------------------|
| `cache_timeout` | `0` disables caching.      | `cache_timeout = 0`  |
| `collections_section_name` | Title displayed for the collections section.          | `collections_section_name = Collections` |
| `landing_page_intro_text_global_value`  | Global variable for the intro text for the collections landing page.  | `landing_page_intro_text_global_value = collections_intro_text`   |
| `landing_page_collection_type`  | The type of collection to display on the landing page.   | `landing_page_collection_type = project` |
| `landing_page_sort` | Attribute to sort collections on the landing page.   | `landing_page_sort = ca_collections.idno_sort`   |
| `landing_page_item_image_format`  | Image format for collection items on the landing page (`none`, `contain`, `cover`).   | `landing_page_item_image_format = cover`  |
| `landing_page_item_display_template`   | Template for displaying collection items on the landing page.   | `<div class='card-title'>^ca_collections.preferred_labels</div>`  |
| `do_not_display_collection_browser`    | Hides the collection browser if set to `1`.    | `do_not_display_collection_browser = 0`  |
| `collapse_levels`   | Enables collapsible hierarchy levels | `collapse_levels = 1`      |
| `max_levels`  | Maximum number of hierarchy levels to include  | `max_levels = 4`  |
| `collection_type_icons`  | Icons for specific collection types, defined by typecode.  | `{box = <i class='bi bi-archive'></i>, file = <i class='bi bi-folder2'></i>}` |
| `link_out_icon`    | Icon for "link out".   | `<i class='bi bi-box-arrow-up-right' aria-label='link out'></i>`     |
| `description_template`  | Template for collection descriptions.  | `<div class='small'>^ca_collections.description</div>` |
| `non_linkable_collection_types` | Collection types that should not link to detail pages.  | `non_linkable_collection_types = {}` |
| `exclude_collection_types`    | Collection types excluded from the hierarchy browser.    | `exclude_collection_types = {}` |
| `always_link_to_detail`   | Links to detail pages even if there are no related objects or child collections.  | `always_link_to_detail = 0` |
| `always_link_to_hierarchy_viewer_sublist` | Links always open additional information in the hierarchy browser panel.    | `always_link_to_hierarchy_viewer_sublist = 1` |
| `dont_show_top_level_description` | Don't display top-level descriptions. | `dont_show_top_level_description = 0`   |
| `export_sub_collection_label_template`  | Template for labeling sub-collections in PDF exports.   | `export_sub_collection_label_template = ^ca_collections.description`  |
| `export_sub_collection_sort`  | Sort order for sub-collections in PDF exports.  | `export_sub_collection_sort = ^ca_collections.idno_sort`   |
| `export_object_label_template`  | Template for object labels in PDF exports. | `export_object_label_template = ^ca_objects.preferred_labels.name`|
| `export_max_levels`      | Maximum levels to include in PDF exports.    | `export_max_levels = 4`    |
| `export_exclude_collection_types`    | Exclude specific collection types from PDF exports.      | `export_exclude_collection_types = {}`   |
| `export_collection_type_icons`   | Icons for collection types in PDF exports, keyed by typecode.  | `{file = <div class='fileIcon'></div>}` |
