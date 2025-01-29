---
sidebar_position: 1
---

# About

The `Ban` module provides a configurable, extensible system for filtering bots, scrapers and other abusive users.

Incoming requests are evaluated using tests specified in the `ban_hammer.conf` configuration file. Each test can be calibrated to the desired level of restriction using options in the configuration file. Standard tests include:

| Test   | Explanation   |
| --- | --- |
| IPAddress  |  Ban user based upon IP address. Addresses may be a specific address or range of addresses.  | 
| UserAgent  |  Ban user based upon user agent. Agent matches may be partial. A preconfigured list of abusive user agents may be automatically loaded.  | 
| RequestFrequency  |  Ban user based upon frequency of connection. Users exceeding the specified maximum connection rate are banned.  | 
| ExportFrequency  |  Ban user if the frequency of exports (PDF or Excel) exceeds the specified rate, or if user exports exceed a maximum number within a single session.  | 

## How Requests are Evaluated

The `Ban` module applies each configured test to a request. Each test returns a "ban probability" - a number between zero and one indicating confidence of user ban. Some tests, such as IPAddress, are straightforward - the user either is or isn't at the specified IP - and always return either zero or one. Other tests may indicate uncertainty be returning a fractional value.

The module can be configured to ban users if the sum or average of the returned probabilities exceeds a threshold. By manipulating the returned probabilities and threshold it is possible to control the overall sensitivity of the system.

If the overall probability of test failure exceeds the defined threshold the user is banned for a configured period of time. Bans are enforced by IP address. While a ban is in place, no requests from the user's IP address will be accepted.

## Allowing Users to Bypass Bans

Legitimate users can, and almost certainly will, be incorrectly flagged as malicious bots and banned. The `Ban` module offers an optional process for users to prove they are individuals by solving a [CAPTCHA](https://support.google.com/a/answer/1217728). If the user successfully solves the CAPTCHA they are exempted from bans regardless of subsequent behavior for a configured period (typically one day).  

## Extending the `Ban` Module

You can implement your own tests as a `BanHammer` plugin class located in the `app/lib/Plugins/BanHammer/` directory. All plugins should inherit from the `BaseBanHammerPlugin` base class.

