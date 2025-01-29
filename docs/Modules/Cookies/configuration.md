---
sidebar_position: 2
---

# Configuration

The `cookies.conf` file defines the behavior of the Cookies Module, including settings for the cookie consent banner, cookie categories, and user preferences

| Option                 | Explanation                          | Example                                   |
|------------------------|--------------------------------------|-------------------------------------------|
| `enable_cookie_manager`| Enables or disables the cookie manager feature. (`1` = enabled, `0` = disabled). | `enable_cookie_manager = 0`|
| `cookiesBannerText`    | The message displayed on the cookie consent banner.  | `"We use cookies on our website to enhance your user experience."`|
| `cookiesBannerGlobalValue` | Reference to a global variable for the banner text.  | `cookiesBannerGlobalValue = cookies_banner_text`|
| `cookiesFormIntro`     | Introduction text shown in the cookie management form.  | `"<p>We use cookies on our website to enhance your user experience.</p>"`|
| `cookiesIntroGlobalValue`  | Reference to a global variable for the cookie form intro text. | `cookiesIntroGlobalValue = manage_cookies_intro`|
| `cookiesByCategory`    | Defines categories of cookies and their descriptions. | `{ essential, performance, analytics, marketing, social }`|
|`title`         | Title of the cookies category. | `"Essential"`  |
|`description`   | Description of essential cookies (required). | `"These cookies are strictly necessary..."`|
|`cookies`       | List of essential cookies, including names and descriptions.  | `{ collectiveaccess = { name: "Session cookie", description: "..."} }`|
