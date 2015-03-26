MIMEMAIL
===========

CONTENTS OF THIS FILE
---------------------

 - Introduction
 - Requirements
 - Installation
 - Permissions
 - Usage
 - Sponsors

INTRODUCTION
------------

Big thanks to Allie Micka.

This is a Mime Mail component module (for use by other modules).

It permits users to receive HTML email and can be used by other modules. The mail functionality accepts an HTML message body, mime-endcodes it and sends it.
If the HTML has embedded graphics, these graphics are MIME-encoded and included as a message attachment.
Adopts your site's style by automatically including your theme's stylesheet files in a themeable HTML message format
If the recipient's preference is available and they prefer plaintext, the HTML will be converted to plain text and sent as-is. Otherwise, the email will be sent in themeable HTML with a plaintext alternative.
Allows you to theme messages with a specific mailkey.
Converts CSS styles into inline style attributes.
Provides simple system actions and Rules actions to send HTML email with embedded images and attachments.
Note that there are some serious limitations you need to take into consideration when creating email layouts, see the Email Standard Project for more information.

This module is required by the Send module.

TESTED
-----

@todo
This module has NOT BEEN TESTED and is being ported to Backdrop.  It may work.

KNOWN ISSUES
---------------------
@todo


REQUIREMENTS
------------

This branch requires the Mail System module.

INSTALLATION
------------

MimeMail can be installed via the standard Backdrop installation process
(http://drupal.org/documentation/install/modules-themes/modules-7).


PERMISSIONS
------------

@todo


USAGE
-----
@todo


License
-------

This project is GPL v2 software. See the LICENSE.txt file in this directory for
complete text.

Maintainers
-----------

- seeking

Current Maintainers on Drupal:

This project is based on work efforts by Robert Castelo, Gerhard Killesreiter, Allie Micka and Gabor Seljan.

Robert Castelo <https://www.drupal.org/user/3555>
Gerhard Killesreiter <https://www.drupal.org/user/227>
Allie Micka <https://www.drupal.org/user/15091>
Gabor Seljan <https://www.drupal.org/user/232117>

Ported to Backdrop by:

 - biolithic <https://github.com/biolithic>
