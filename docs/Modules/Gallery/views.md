---
sidebar_position: 3
---

# Views

The views for the `Gallery` module are located in the `views/Gallery` directory.

The `index_html.php` file in the Gallery module is displays the main landing page for galleries. It retrieves and displays gallery sets and links to individual gallery pages.

The `detail_html.php` file in the Gallery module displays the details of a selected gallery set, including its title, description, and items.

The `detail_item_info_html.php` file in the Gallery module displays information about a selected gallery item, including its image and metadata. It includes navigation buttons to move between items within a gallery set.

## Variables for `index_html.php`

| Variable                               | Description                                               |
|----------------------------------------|-----------------------------------------------------------|
| `caGetGalleryConfig`                   | Retrieves gallery configuration settings. |
| `t_set`                                | An instance of the `ca_sets` class, used to manage gallery sets. |
| `caGetUserAccessValues`                | Get user access permissions for gallery sets. |
| `landing_page_item_image_format`       | Determines the format of gallery images.|
| `vs_image_class`                       | CSS class for image formatting. |
| `gallery_set_description_element_code` | The element code for the gallery set description. |
| `landing_page_dont_show_featured_gallery`| Determines if a featured gallery should be displayed. |
| `sets`                                 | Gallery sets to be displayed on the landing page. |
| `first_items_from_sets`                | The first media items from each gallery set for preview. |
| `section_name`                         | Name of the Gallery section. |
| `landing_page_intro_text_global_value` | Retrieves the global intro text value from `gallery.conf`. |


## Variables for `detail_html.php`

| Variable        | Description                                               |
|-----------------|-----------------------------------------------------------|
| `set_items`     | The list of items in the gallery set. |
| `set_id`        | The ID of the current gallery set being displayed. |
| `set`           | The gallery set object. |
| `label`         | The title of the gallery set. |
| `description`   | The description of the gallery set. |
| `set_item_id`   | The ID of the currently selected item within the set. |
| `table`         | The database table associated with the set items. |
| `instance`      | An instance of an item within the set. |
| `access_values` | User access permissions for the gallery items. |


## Variables for `detail_item_info_html.php`

| Variable                   | Description |
|----------------------------|------------|
| `previous_item_id`         | The ID of the previous item in the gallery set.|
| `next_item_id`             | The ID of the next item in the gallery set. |
| `previous_row_id`          | The row ID of the previous item in the gallery. |
| `next_row_id`              | The row ID of the next item in the gallery. |
| `previous_representation_id` | The ID of the previous item's media representation. |
| `next_representation_id`   | The ID of the next item's media representation. |
| `set_id`                   | The ID of the current gallery set being displayed. |
| `row_id`                   | The row ID of the current item. |
| `table`                    | The table where the current item is stored. |
| `representation_id`        | The media representation ID of the current displayed item. |
| `instance`                 | Instance of the current gallery item. |
| `set_item`                 | The set item in the gallery. |
| `config`                   | The configuration settings for the gallery module. |
| `set_item_num`             | The current item's position in the gallery set. |
| `set_num_items`            | The total number of items in the gallery set. |
