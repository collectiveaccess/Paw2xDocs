---
sidebar_position: 3
---

# Views
 
The `form_login_html.php` file is responsible for rendering the login form in the LoginReg module. It displays a standard login interface with fields for a username and password, a submit button, and links to register or reset a forgotten password.

The `form_profile_html.php` file is responsible for displaying and managing the user profile settings within the LoginReg module. It allows users to update their name, email, password, and additional profile settings. 

The `form_register_html.php` file is responsible for rendering the user registration form. It collects user information such as first name, last name, email, password, and optional group codes. It also supports additional profile settings security features such as Google reCAPTCHA for spam prevention.

The `form_reset_html.php` file is responsible for handling the password reset process in the login and registration module. It displays different views based on the reset action.

## Variables for `form_login_html.php`

| Variable                     | Description                                                            |
|------------------------------|------------------------------------------------------------------------|
| `message`                    | Displays an error message if there was an issue with the login attempt. |
| `dontAllowRegistrationAndLogin`| A configuration value that prevents user registration and login. |
| `dontAllowRegistration`       | A configuration value that prevents user registration. |


## Variables for `form_profile_html.php`

| Variable           | Description                                                                        |
|--------------------|------------------------------------------------------------------------------------|
| `errors`           | Error messages for various input fields. |
| `t_user`           | The current user object, used to retrieve and update user profile information. |
| `profile_settings` | Stores additional profile settings that may be customized in the system. |
| `registration_show_group_code` | A configuration setting that determines whether the group code field is shown. |

## Variables for `form_register_html.php`

| Variable           | Description                                               |
|--------------------|-----------------------------------------------------------|
| `errors`          | Validation errors for the registration form fields. |
| `t_user`          | The user object, used to generate form elements. |
| `registration_show_group_code`| Indicates if a group code input field should be displayed during registration. |
| `registration_security`| Specifies the security applied during registration. |
| `profile_settings`| Stores additional profile settings included in the registration form. |

## Variables for `form_reset_html.php`

| Variable       | Description |
|---------------|-------------|
| `message`     | Error message if any issue occurs during the password reset process. |
| `action`      |  |
| `email`       | The support email address to contact for assistance. |
| `key`         | The reset key sent to the user. |
