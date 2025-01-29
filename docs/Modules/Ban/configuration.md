---
sidebar_position: 2
---

# Configuration


## General Options

| Option Name   | Explanation  |
| --- | --- | 
|  enabled |  Controls whether the `Ban` module is active. Set to a non-zero value to enable. | 
| evaluation_mode |  Controls how bans are evaluated. Must be either `absolute` or `average`. In absolute mode, ban probabilities returned by enabled plugins are summed. If the sum exceeds the threshold the user is banned. In average mode if the average probability returned by enabled plugins exceeds the threshold the user is banned. | 
| threshold |  The numeric ban threshold. If the ban probabilities returned by enabled plugins exceed this value the user is banned. This value must be a number between zero and 1. | 

## Plugin Configuration

Tests are implemented as plugins. Each plugin may be configured in the `ban_hammer.conf` configuration file under an entry in the form `plugins.<plugin name>`. The value of the entry is an object defining the plugin-specific options described below. A typical entry for a plugin (in this case the IPAddress plugin) would appear in `ban_hammer.conf` in this form:

```
plugins.IPAddress = {
	ttl = 86400,
	
    banned_ip_addresses = [
        127.0.0.10
    ]
}
```

:::note
Tests are implemented as plugin classes stored in the `app/lib/Plugins/BanHammer/` directory. You can add additional tests by dropping new classes into this directory.
:::

## IPAddress Plugin

The IPAddress plugin bans users based upon their IP address. Use it to block potentially malicious IP ranges.

:::note
Currently only IPv4 addresses are supported
:::

| Option Name   | Explanation  | 
| --- | --- |
|  ttl |  Length of user ban, in seconds | 
|  banned_ip_addresses |  A list of ip addresses to bans. Wildcards may be used to match ranges. For example:  10.55.\*.\* will match any IP address in the 10.55 class-B network. | 


## UserAgent Plugin

The UserAgent plugin bans users based upon the user agent string sent with their request. The user agent should identify the software used to connection, whether that is a browser, a scripting extension or a bot. 

Users with user agents matching entries in the `banned_useragents` list, in whole or in part, will be banned. If the `banned_useragents` list includes an entry for "bot", then *any* user agent containing "bot" anywhere will be banned.

Several projects maintain online lists of abusive user agents. You can employ these lists to automatically ban users by setting the `use_useragent_list` option and providing a URL to a validly formatted list. Lists should be in the JSON format used by https://github.com/monperrus/crawler-user-agents. If a list is used, it will automatically be downloaded and periodically updated. The period between updates can be controlled using the `useragent_list_ttl` option.

| Option Name   | Explanation  | 
| --- | --- |
|  ttl |  Length of user ban, in seconds | 
| banned_useragents | List of user agents to ban  | 
| use_useragent_list |  Ban user agent using a dynamically loaded ban list | 
| useragent_list_url | URL for user agent ban list. List is JSON in the format defined at https://github.com/monperrus/crawler-user-agents  | 
| useragent_list_ttl | Time in seconds between refreshed of user agent ban list  | 
| exclude_useragents | List of user agent patterns to always pass (eg. exclude from useragent list)  | 
| useragent_list_force_reload | Force reload of user agent list regardless of ttl  | 

## RequestFrequency Plugin

The RequestFrequency plugin bans users connecting to the site too quickly. Frequent connections may indicate an abusive bot or scraper.

| Option Name   | Explanation  | 
| --- | --- |
|  ttl |  Length of user ban, in seconds | 
|  frequency_threshold |  Maximum number of page loads per second before user is banned | 
|  ban_probability |  Probability of ban on test failure. Must be a number between 0 and 1.0, where 1.0 indicates an absolute ban. | 

## ExportFrequency Plugin

The ExportFrequency plugin bans users requesting PDF or Excel data exports too quickly or frequently. Frequent exports often indicate an abusive bot or scraper.

| Option Name   | Explanation  | 
| --- | --- |
|  ttl |  Length of user ban, in seconds | 
|  frequency_threshold |  Maximum number of exports per second before user is banned | 
|  allowed_exports_per_session |  Maximum number of exports in a session user is banned. Set to zero for no limit. | 
|  ban_probability |  Probability of ban on test failure. Must be a number between 0 and 1.0, where 1.0 indicates an absolute ban. | 

## CAPTCHA Support

The tests provided by the `Ban` module are imperfect and can sometimes ban legitimate users. By default bans last for a period of time, typically one day. To allow legitimate users to un-ban themselves the module can display a Google CAPTCHA puzzle to banned users. Users successfully completing the CAPTCHA are placed on a "no ban" list for a period of time (also usually one day).

To display a CAPTCHA on ban, register with Google CAPTCHA at https://www.google.com/recaptcha/about/, and create a CAPTCHA for the URL under which Pawtucket runs. Google will provide two keys, public and secret, for the CAPTCHA. Copy these keys into the `__CA_GOOGLE_RECAPTCHA_KEY__` and `__CA_GOOGLE_RECAPTCHA_SECRET_KEY__` settings in the `setup.php` file. Once configured in `setup.php` the `Ban` module will automatically display CAPTCHA whenever a user is banned.

:::note
CAPTCHA settings in `setup.php` are PHP language constants, rather than configuration file settings. Note the syntax in the examples above.
:::