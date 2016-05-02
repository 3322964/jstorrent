JSTorrent - The Torrent client for Google Chrome and ChromeOS
=========

https://chrome.google.com/webstore/detail/jstorrent/anhdpjpojoipgpmfanmedjghaligalgb (JSTorrent Available for install Chrome Web Store)

https://chrome.google.com/webstore/detail/bnceafpojmnimbnhamaeedgomdcgnbjk (Helper extension, adds right click "Add to JSTorrent" menu)

---

JSTorrent is the original Chrome Packaged/Platform App for downloading
torrents. It stands for "JavaScript Torrent." It is perfect for cheap
ARM Chromebooks when you need to torrent some stuff, but also perfect
for your $1200 high end Pixel. :-) While it is specifically designed
to integrate well with ChromeOS, it will also run on Windows / Mac /
Linux, or anywhere else you are able to install Google Chrome.

JSTorrent is the world's most secure Torrent client. It runs in the
Chrome sandbox, so it does not have access to any files on your system
(except the Download folder you choose). With JSTorrent, you are in
control.

I don't frequently keep this readme very up to date. You can find the
actual changelogs in the [https://chrome.google.com/webstore/detail/jstorrent/anhdpjpojoipgpmfanmedjghaligalgb](chrome web store), or sometimes in the [https://github.com/kzahel/jstorrent/blob/fresh/CHANGES.txt](CHANGES) file

One of my main goals with this project is to get it nearly as fast as
the other clients. Disk I/O is pretty slow with the chrome APIs, which I am working on optimizing for.
Some other bottlenecks at this point include SHA1 hashing (done in a worker)
as well as suboptimal peer selection and queueing.

I am frequently adding features and improvements to this project, and
welcome user feedback, as it directs the future growth of the program.

This software was totally rewritten from scratch (Dec 2013). This is
about the third time I've written a torrent client, so it should be
the least buggy of them all :-)

I'm currently charging $3 for the install on the chrome web store. But
you can also run it from source here. I want to do some kind of
donate/freemium model, once I can figure out this:
http://stackoverflow.com/questions/21147236/get-user-openid-url-without-user-interaction
(I want to be able to detect users who already paid $3)

The source code is available here for auditing and education
purposes. I believe open software is great, and I would not ask any
user to install something that they can't reasonably verify is not
doing anything malicious. However, the license does permit
redistribution of the source code in your own projects.

Installation:
====
Most people would usually install by the Chrome Web Store ([https://chrome.google.com/webstore/detail/jstorrent/anhdpjpojoipgpmfanmedjghaligalgb](link)) but you can install from 
source too.
* Click the "Download ZIP" button on the sidebar.***
* Unzip it.
* Visit "chrome://extensions"
* Click "load unpacked extension"
* Browse to the unzipped file then press "Open"
* You're done! (Note that you will not get updates this way, you will need to manually update)
* NOTE***: This project now uses a submodule "web-server-chrome" (https://github.com/kzahel/web-server-chrome) so you probably have to download that project separately and put it in the "js" folder. (you may need to rename folder from "web-server-chrome-master" to "web-server-chrome")

Websites:
----

https://www.jstorrent.com

https://google.com/+jstorrent (Official Google+ Community Page)

https://twitter.com/jstorrent (Twitter Page)


Special New Features
=======

- Support downloading directly to directory of choice
  - download to external media (usb drives)
  - Per-torrent download directories
  - multiple download directories
- Unlimited size downloads (multi gigabyte torrents)

Private tracker support notes for site admins
=======

Private tracker support is very lacking. I don't know of any sites
that have whitelisted/allowed JSTorrent. I am working on addressing
this, and improving the situation

- The "User-Agent" header looks like: (JSTorrent/{version}) (current x-user-agent string version: "JSTorrent/2480") for version 2.4.8
- The peer id begins with "-JS{version}-", currently peer id begins with "-JS2480-"

I have disabled the spoofing feature.

Todo
=======
- see [https://github.com/kzahel/jstorrent/blob/fresh/TODO.txt](TODO file)
- too many things
- figure out chrome.fileSystem getting in broken state bugs (persistently problematic)
- smarter disk cache
- better seeding disk access / read entire piece at a time
- implement i8n
- pNaCL sha1 hashing benchmark vs native JS vs window.crypto
- use chrome.identity and GCM for remote control (pushMessaging) (in progress)
- DHT
- uPNP+bind/listen TCP - (in progress)
- SOCKS5 proxy support
- headless operation (in progress)

Credits
=======
- JSTorrent Logo - Michael Cook (https://plus.google.com/+michaelcook)
- Users and supporters that produce good bug reports :-)
