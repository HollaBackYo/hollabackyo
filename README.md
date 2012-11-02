HollaBackYo
===========

Asterisk and Tornado based HTML5 based callback mobile app and server

CheckItOutYo
============

git clone git@github.com:HollaBackYo/hollabackyo.git

WhatItIsYo
==========

Simply put.  HollaBackYo allows iOS and Android users the ability to place custom callback apps on their device and
with a single click send a signal to a remote Asterisk server to have it call them in a definable way.

WhyTheHeckYo
============

I needed a really quick way for our mobile workforce to get in touch with our customer support and order dispatching
departments without having them:

  - Hold the line waiting
  - Go in through a custom IVR
    - Requires DIDs for all of our local offices

HowsItWorkYo
============

By using manifest files, html5 and javascript and json we can have a server which can create apps of specific quickdials
that can be offloaded onto a supported mobile device.  Quick and dirty app.

Doing this also allows us to create custom, on demand, templated apps that contain information like the number the user
registered as their cell phone which, once downloaded, is now hard coded into the application and cannot simply have it's
settings rewritten without deleting the app and redownloading it.

Depending on how the "app" was configured before it was downloaded, once the user clicks on the apps icon it loads up an
informative display and triggers the dial through the server interface which is configured to work with Asterisk using a
simple AJAM/AMI client or the asterisk spool directory.

Custom routing engines are supported to allow, for example, a GeoIP based solution that sends the call request to the
nearest office.  Backup servers are supported as well.

The AMIty service, along with Asterisk, can optionally announce several attributes on top of some of the mandetory ones
required to understand if the call was accepted:

  - Suggested wait time
  - What office it was sent to

This is done by using Pure JSON templating