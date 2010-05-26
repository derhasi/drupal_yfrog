; $Id$

This module provides an additional input filter, that converts yfrog-URLS, e.g.
from twitter messages, to a clickable Link, Image or Video.

The module implements the specifications of
http://code.google.com/p/imageshackapi/wiki/YFROGurls

REGEXP PATTERN
==============

If there are any problems with this regexp, please post an issue.

main REGEX:
-----------
http://(www\.)?yfrog\.(com|us|ru|com\.tr|it|co\.il|co\.uk|com\.pl|pl|eu)/[A-z0-9]+[jpbtgsdfzx](:frame|:iphone|\.th\.jpg)?

It allows:
* only specified TLDs (@see [1])
* only specified content types (@see [1])
* only http URLs
* URLS with and without 'www.'
* Special URLs appended with :frame, :iphone or .th.jpg

[1] http://code.google.com/p/imageshackapi/wiki/YFROGurls

Prepended by REGEX:
------------------------
(<h[1-9]>|<p>|<li>|<br\s*/?>|[ \n\r\t\(])

this assures that only URLs are replaced, that are prepended by
* <h1>,<h2>,<h3>,... tag
* <p>, <li>, <br/> -tag
* a space " "
* linebreak (\n, \r, \t)
* open braket "("