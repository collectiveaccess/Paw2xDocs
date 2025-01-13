---
sidebar_position: 3
---

# Views

Views for the `Ban` module are defined in the theme `views/Ban` directory.
The `verify_html.php` view is used to generate the notice when a user has been banned. If CAPTCHA-based ban bypasses are configured the view will include a CAPTCHA, otherwise a text message with contact for the site administration will be displayed.

## Variables for `verify_html.php`

The `verify_html.php` view formats the ban notice.

Variables available in `verify_html.php` include:

| Variable  				| Description  				| 
| --- 						| --- 						|
| **errors**	| An array of error messages set if submission of form has failed.	|

