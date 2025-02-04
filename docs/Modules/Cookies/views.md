---
sidebar_position: 3
---

# Views

Views for the `Cookies` module are defined in the themes `views/Cookies` directory.

The `banner_html.php` file displays the cookie consent banner to users when they visit the website. It checks if the cookie banner should be shown, retrieves the configured banner text, and allows the user to manage or accept cookies.

The `form_manage_html.php` file provides a view for managing cookie preferences. Users can enable or disable different types of cookies based on categories and can also accept all cookies or update their choices.

## Variables for `banner_html.php`

| Variable                   | Description                                                            |
|----------------------------|------------------------------------------------------------------------|
| `caGetCookiesConfig`       | Stores the cookie configuration settings.                              |
| `cookiesBannerGlobalValue` or `cookiesBannerText`| Holds the text to be displayed in the cookie banner.|

## Variables for `form_manage_html.php`

| Variable                   | Description                                                           |
|----------------------------|-----------------------------------------------------------------------|
| `cookiesByCategory`        | Stores the different cookie categories and their settings.            |
| `config`                   | Stores the cookie configuration settings.                             |
| `cookiesFormIntro`         | The introductory text shown at the top of the form.                   |
