---
sidebar_position: 2
---

# Configuration

## General Gallery Options 

This section defines the general configuration settings for the Gallery module, located in `conf/gallery.conf`

| Option Name | Description | Example |
|----------|------------|---------|
| `gallery_section_name` | The display name for the gallery section. | `"Gallery"` |
| `gallery_section_item_name` | The singular name for an item in the gallery section. | `"gallery"` |
| `gallery_section_item_name_plural` | The plural name for items in the gallery section. | `"galleries"` |
| `gallery_set_type` | The type of set to display in the gallery section. | `"public_presentation"` |
| `landing_page_dont_show_featured_gallery` | Determines whether to display a featured gallery on the landing page (`0` show, `1` hide). | `0` |
| `landing_page_featured_heading` | The heading for the featured gallery section. | `"Featured Gallery"` |
| `landing_page_item_image_format` | The image format for galleries on the landing page (`contain` or `cover`). | `"cover"` |
| `landing_page_intro_text_global_value` | The global value for the introduction text on the gallery landing page. | `"gallery_intro_text"` |
| `gallery_set_description_element_code` | The metadata element code for the description of sets displayed on landing and detail pages. | `"set_description"` |
| `gallery_include_all_tables` | Determines whether to include sets with any content type (`1`) or only objects (`0`). | `1` |
| `omit_front_page_set_from_gallery` | Exclude a front-page set from appearing in the gallery (`1` omit, `0` include). | `1` |
