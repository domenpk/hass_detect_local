# hass_detect_local
Simple HTML+JS to redirect to home-assistant on LAN (if it exists) or to web


## What is this?

I have hass (home-assistant) on LAN, but also proxied over the web, so it can be accessed when I'm not at home.
This script detects if there is hass on LAN, and redirects accordingly.


## How to use?

Upload the html to some webpage (I'm using http://detect.lucke.cba.si/ as example here - you can use this URL as a demo, but I provide no guarantees), then access it.

On first use, it will present a simple config screen (you can access that screen by appending ?set to URL).

For example:
Go to http://detect.lucke.cba.si/ (or http://detect.lucke.cba.si/?set when you want to change settings; you could also clear cookies to reset).

Input:
http://192.168.0.15:8123/ (for LAN hass access)
https://my-hass-proxy.example.com/ (for hass proxied to web)

Click set, and you're good to go. Next time just access http://detect.lucke.cba.si/ and it will redirect you to correct URL.

Many projects where you want to access different URL from home or elsewhere could use this with minor modification (favicon.ico path).


## How does it work?

It uses cookies to store LAN and publicly accessible URLs.

To detect hass, it tries to load an 'img' from hass.


## Issues

It must be accessed over HTTP (not HTTPS), because it makes an HTTP request to detect hass on LAN.

Code nor user interface is very nice, but works for me. I'd happily accept pull requests that improve this.
