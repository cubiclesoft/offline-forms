Offline Forms
=============

A form designer and data gathering tool for use in areas with spotty or unknown Internet connectivity.  Powered by any standard web browser.  Offline Forms is a useful solution to the problem of digitally gathering data even when Internet access is not functional or only partially functional.  Choose from a MIT or LGPL license.

[![Offline Forms Screenshot](https://user-images.githubusercontent.com/1432111/196460161-52411c41-359c-4fc9-ad37-3153a7986fe5.png)](https://cubiclesoft.com/demos/offline-forms/index.html)

[Live demo](https://cubiclesoft.com/demos/offline-forms/index.html)

[![Donate](https://cubiclesoft.com/res/donate-shield.png)](https://cubiclesoft.com/donate/) [![Discord](https://img.shields.io/discord/777282089980526602?label=chat&logo=discord)](https://cubiclesoft.com/product-support/github/)

Features
--------

* Can be loaded one time from your web server and then saved offline.  See below for details.
* Excellent for trade shows, expos, and conferences for gathering potential client information (e.g. newsletter signups).
* Great for use in areas where Internet connectivity might be spotty or nonexistent (e.g. gathering door-to-door survey responses).
* Blazing fast.  Changes to what is displayed happen almost instantaneously.
* Password protected access to manage forms.  With caveats - see below.
* Supports custom HTML and Javascript.
* Export and import prepared offline forms.  Create on a desktop and then export the form and subsequently import the form on a phone or tablet.
* Export submitted data as CSV and JSON Lines.
* Has a liberal open source license.  MIT or LGPL, your choice.
* Designed for relatively painless integration into your data gathering project.
* Sits on GitHub for all of that pull request and issue tracker goodness to easily submit changes and ideas respectively.

Getting Started
---------------

Just follow this simple, 5-step process:

1. Upload the contents of this repository to your own web server.  Alternatively, use the [Live demo](https://cubiclesoft.com/demos/offline-forms/index.html).
2. Visit the URL on each device.
3. Save the page offline (see below).
4. Access the saved offline page.
5. Follow the instructions to set a password and start creating and using Offline Forms.

Offline Use
-----------

Each device and web browser has a different way to save webpages offline so they are accessible even when Internet connectivity is spotty or not working at all.  Even different versions of device + OS + web browser combination can have vastly different instructions.  A search for "make website available offline" plus browser name plus OS or device (or all three) will generally turn up reasonably decent results.

Here are some helpful Google searches for making web pages available offline in the most popular OSes and web browsers:

* [Apple/iOS + Safari](https://www.google.com/search?q=make+website+available+offline+ios)
* [Android + Chrome](https://www.google.com/search?q=make+website+available+offline+android)
* [Chrome](https://www.google.com/search?q=make+website+available+offline+chrome)
* [Firefox](https://www.google.com/search?q=make+website+available+offline+firefox)
* [Edge](https://www.google.com/search?q=make+website+available+offline+edge)
* [Safari](https://www.google.com/search?q=make+website+available+offline+safari)
* [Opera](https://www.google.com/search?q=make+website+available+offline+opera)

Once Offline Forms has been made offline, a good verification test is to go into Airplane mode and try to load Offline Forms.  If it still loads, then both the core application and its dependencies will work entirely offline.

Example Form
------------

Copy and paste the following JSON to import a working example form for handling email newsletter signups:

```
{"id":"form_example_1","title":"Subscribe to our Newsletters","desc":"We have a couple of really great newsletters offering everything from product information to early bird seasonal sales.","init_js":"","enabled":true,"thanks":"Thank you for signing up for our newsletter(s).  We really appreciate it and look forward to interacting with you in the future.","options":{"fields":["startrow",{"type":"text","title":"First name","width":"19em","required":true,"name":"firstname","default":"","desc":"","validator":""},{"type":"text","title":"Last name","width":"18em","required":true,"name":"lastname","default":"","desc":"","validator":""},"endrow",{"type":"text","subtype":"email","title":"Email address","width":"38em","required":true,"name":"email","default":"","desc":"We won't spam you or sell your email address.","validator":""},{"type":"checkbox","required":false,"name":"list_main","value":"","display":"Main newsletter - Get new and updated product announcements monthly.","default":true,"desc":"","validator":""},{"type":"checkbox","required":false,"name":"list_deals","value":"","display":"Deals newsletter - The best deals in the business delivered to your inbox.","default":true,"desc":"","validator":""}],"submit":"Submit"}}
```

The form is the same as the screenshot at the top of this README.

Security Considerations
-----------------------

Everything regarding Offline Forms is stored in the local web browser using what is known as Local Storage (aka `window.localStorage`).  The management interface may be password protected and the data gathered is stored in Local Storage as well but the way these items are stored means it is relatively easy to circumvent the limited protections in place and extract all of the information that has been stored there.  An attacker could also inject Javascript into the Offline Forms application such that it results in an [Advanced Persistent Threat (APT)](https://en.wikipedia.org/wiki/Advanced_persistent_threat).

Unfortunately, there is no particularly good way to secure Local Storage to create a functional digital rights management (DRM) zone.  This tool should therefore not be used to gather and store:  User passwords, credit card numbers, social security numbers (SSNs), bank account information, or anything else that, if leaked by an attacker (or even an unscrupulous employee) who gains access to the information, could be severely damaging to the reputation or image of an individual or organization.  The password used to protect the management interface is only meant as a deterrent and not an actual security mechanism.  Someone signing up for a newsletter or supplying inconsequential contact information, which is the main purpose of Offline Forms, is vastly different from paying for goods and services.
