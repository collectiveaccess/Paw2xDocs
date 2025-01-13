---
sidebar_position: 2
---

# Theming

## Getting Started 
	- Site specific themes allow for extensive customization of the look and functionality of Pawtucket while building upon what exists in the default theme.
	- When creating a new theme, keep in mind all views and css in the default theme are the base you are building upon.  The views in your theme will be used instead of what is in default, but you ONLY need to have the files you are making modifications to in your theme.  Pawtucket will first look for views in the configured theme and fall back to those in default when not avaiable.  For this reason, there is no need to copy all the views from the default theme into your theme.
    

## Creating a new theme
    - Create a copy of the copyme theme in the themes directory, giving it a new name. This will serve as a good starting point for your new theme. Remember when views are not in a theme, the views in the default theme are used.
    - Copy the configuration folder from the default theme into the new theme.  It is located in /themes/default/config
    - Configure your new theme to be used by Pawtucket.  In /setup.php, set <code>$_CA_THEMES_BY_DEVICE = ['_default_' 	=> 'yourTheme'];</code>
    - Install all dependencies by running <code>npm i</code>
    - Webpack your theme by running <code>npx webpack</code> to compile your new theme's assets

## Styling

    - Pawtucket uses Boostrap for its grid system, forms, components and overall styling.
    - The version of Bootstrap being used is [v5.3.2](https://getbootstrap.com/docs/5.3/getting-started/introduction/)
    - Stylesheets are located in the css directory of the configured theme. `main.scss` loads the stylesheets in the default and configured theme so that styles in configured theme will override those in default.  Enter theme specific variables and styles in the configured theme's `css/_bs_variables_theme.scss` and `css/theme.scss`.  Blank versions of these files will be in the theme if you created it by copying the copyme theme.
    - The default theme's Bootstrap sass variables are being set in `themes/default/css/_bs_variables.scss`.  You can override these variables or any boostrap variables in the configured theme's `_bs_variables_theme.scss` to style various bootstrap components and general styling across the site.  <br/>Note: Do not include !default in variable declarations in your theme's `_bs_variables.scss` if they've already been defined in `themes/default/css/_bs_variables.scss`.
    - More custom styling should be done in `theme.scss` which is the last loaded stylesheet. 

## Setting a Logo in the header

    - Add your logo to the assets/graphics directory
    - Go into views/pageFormat directory and into the `pageHeader.php` file
    - Find the caGetThemeGraphic function, and change it to link to your logo in the graphics directory

## Setting up the Front page

### Adding an image to the parallax on the front page
    - Add the image in the assets/graphics directory

    - In the main.scss file, go to the `.parallax` style and change the background image url to the image you've added to the graphics directory

    - If you want a variety of images to appear at random for the parallax, you can set the styles `.hero1`, `.hero2` and `.hero3` to images of your choice.

### Explore the archive
    - As a default this section will link to the Objects Browse, Gallery and Collections landing pages. This can be changed in the `front_page_html.php` file in the views/Front directory. 

    - You are also able to change the images used for these by adding them to the graphics directory and alter the caGetThemeGraphic function to link to the image.

### Carousel
    - There is also a default bootstrap carousel on the front page. The view for this carousel is in the `Front/featured_set_slideshow_html.php` directory. 
    - There is also a corresponding configuration file for the front page called `front.conf`. There is an option to configure the captions for the carousel called `front_page_set_item_caption_template`, where you can add bootstrap utility classes:
        ```
            front_page_set_item_caption_template = <l><div class='carousel-caption bg-black bg-opacity-50 p-2'>^ca_objects.preferred_labels.name</div></l>``` 

## Setting Global Values
    - There are global values, which are text values that can be updated and maintained in the backend. To add them:
        1. Define your global values in the theme’s conf/app.conf
        2. Copy the global values defined in the theme’s conf/app.conf to admin/app/conf/app.conf
        3. Enter some text for the global values under Manage > Content Management > Global Values in the backend

    - To add these global values to any view, add the value name within a template like `{{{example_value}}}`

    - Example Configuration: 

        ```
        global_template_values = {
            hp_search_text = {
                name = Home Page Search Box Text,
                description = Gallery page introduction,
                width = 600px,
                height = 100px,
                usewysiwygeditor = 0
            },
            hp_welcome_title = {
                name = Home Page Welcome Title,
                description = Home page welcome title,
                width = 600px,
                height = 100px,
                usewysiwygeditor = 0
            }
        }
        ```

## Site Page Creation

    - Site pages are used to create static pages for a site. Their content can managed on the backend under Manage > Content Management > Site Pages.  
    - To start you need to create one or more templates in your theme’s templates directory. There is a basic template in the default theme. In a template, you can name variables that are surrounded by `{{{}}}`. This indicates the text that is editable in the backend. This template example will have content that can be edited for an about page:

        ```
        <div class="row">
            <div class="col-sm-12">
                <h1>{{{title}}}</h1><br>
            </div>
            <div class="row">
                <div class="col-md-8">
                    <h2>{{{subtitle}}}</h2>
                    <p>{{{bodytext}}}</p>
                </div>
                <div class="col-md-4">
                    <address>{{{contact_info}}}</address>
                </div>
            </div>
        </div>
        ```

    - For the variables you create in a template, you must define them in the `template.conf` configuration file. For Example: 

        ```
        fields = {
            title = {
                label = Page title,
                description = Title of page,
                
                width = 600px,
                height = 1
            },
            subtitle = {
                label = Page subtitle,
                description = Subtitle of page,
                
                width = 600px,
                height = 1
            },
        }
        ```

    - When you have your templates defined and the options set in template.conf for the variables, you need to run a command line utility to process your templates.
    Navigate to the support/bin directory for in the root of your Pawtucket installation and run the command: 
    
        `php caUtils scan-site-page-templates`
    
    - Your templates will now be available on the backend to create site pages. 

## Detail Pages

    - Detail Pages are the pages where you are able to add metadata for various record types.
    
### Page Types

    The default detail pages are:

    | Detail Page   | Explanation  |
    | --- | --- | 
    | **ca_collections_default_html**  |   |  
    | **ca_entities_default_html**  |   |  
    | **ca_objects_default_html**  |   |  
    | **ca_occurrences_default_html**  |   |  
    | **ca_places_default_html**  |   |  
    | **ca_entities_default_html**  |   |  

### Adding additional pages

    - You are able to add additional detail views. For instance in cases where a record may have multiple types, such as objects, where there is a type called 'photograph' and a type called 'postcard'. You may want to create separate detail pages for those objects instead of encompassing all the metadata in a single default page. To do so you can create a copy of the default detail page and rename it to include the type code of the record. For example: `ca_objects_photograph_html` and `ca_objects_postcard_html`. 

## Browse




