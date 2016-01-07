# Mime Mail

This Mime Mail module provides functions that can be used by other 
modules to accept an HTML message body and header, mime-endcode it 
and send it via Backdrop's core mail system. 
It also permits users to receive HTML email. 

If the HTML has embedded graphics, these graphics are MIME-encoded 
and included as a message attachment. It will also send uploaded 
files as attachments.

Sent messages are formatted by template, theme and styles. CSS
styles are converted into inline style attributes.

## Installation

- Install this module using the official Backdrop CMS instructions at
  https://backdropcms.org/guide/modules.

- Use the configuration page at /admin/config/system/mimemail to
  set values for:
  + sender name
  + sender email address
  + use simple address format
  + include site style sheets
  + send plain text email only 
  + link images only
	+ preserve class attributes
	+ text format (HTML or plain text) 
	
## Supplementary modules

There are three submodules:

- Mime Mail Example is a simple form for input of an
  email to send via Mime Mail.
	
- Mime Mail Compress converts CSS to inline styles in
  an HTML message. (Requires the PHP DOM extension.)
	
- Mime Mail Action provides additional actions for Mime Mail.
  (Not yet tested with Backdrop.)
	
## Help & Documentation

Please see the readme.txt file for more information.

## License

This project is GPL v2 software. See the LICENSE.txt 
file in this directory for complete text.
    
## Current Maintainer for Backdrop

Graham Oliver (github.com/Graham-72/)

## Credits

### Port to Backdrop

+ Graham Oliver (github.com/Graham-72)
+ Andy Martha (github.com/biolithic)

### Maintainers for Drupal:

+ Robert Castelo <https://www.drupal.org/user/3555>
+ Gerhard Killesreiter <https://www.drupal.org/user/227>
+ Allie Micka <https://www.drupal.org/user/15091>
+ Gabor Seljan <https://www.drupal.org/user/232117>

### Acknowledgement

This port to Backdrop would not, of course, be possible without all
the work done by the developers and maintainers of the Drupal module.
