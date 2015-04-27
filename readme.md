MIMEMAIL
===================

CONTENTS OF THIS FILE
---------------------

 - Introduction
 - Tested
 - Known Issues
 - Special Thanks
 - Requirements
 - Installation
 - Coming From Drupal?
 - Usage
 - License
 - Credits
 - Maintainers

INTRODUCTION
------------

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

Email Modules
The following modules ported to Backdrop are inter-related to the mailing system:

simplenews

simplenews_scheduler

mimemail

mandrill

mailsystem

smtp

They have been converted from Drupal to Backdrop but are still not working.  They need debugging into what was changed between the systems and how to fix it. I, biolithic the one who did the intial conversion, lack the heart or time in the spring of 2015 to debug them currently.

Do you have a need or desire for email newsletters?  You are welcome to submit pull requests to finish these modules.  It may not be a lot of work.  Thanks!

KNOWN ISSUES
---------------------

The Drupal version of this module used the registry database table extensively.  Backdrop CMS removed this table and we are re-engineering the module to work within the Backdrop way.

SPECIAL THANKS
--------------

Big thanks to Allie Micka.

REQUIREMENTS
------------

This requires the Mail System module.


INSTALLATION
------------

Install this module using the official Backdrop CMS instructions at https://backdropcms.org/guide/modules


COMING FROM DRUPAL?
-------------------

The Drupal version of this module used the registry database table extensively.  Backdrop CMS removed this table and we are re-engineering the module to work within the Backdrop way.

PERMISSIONS
------------

@todo


USAGE
-----

This module may be required by other modules, but in favor of the recently
  added system actions and Rules integration, it can be useful by itself too.

  Once installed, any module can send MIME-encoded messages by specifing
  MimeMailSystem as the responsible mail system for a particular message
  or all mail sent by one module.

  This can be done through the web by visiting admin/config/system/mailsystem
  or in a program as follows:

  mailsystem_set(array(
    '{$module}_{$key}' => 'MimeMailSystem', // Just messages with $key sent by $module.
    '{$module}' => 'MimeMailSystem', // All messages sent by $module.
  ));

  You can use the following optional parameters to build the e-mail:
    'plain':
      Boolean, whether to send messages in plaintext-only (optional, default is FALSE).
    'plaintext':
      Plaintext portion of a multipart e-mail (optional).
    'attachments':
      Array of arrays with the path or content, name and MIME type of the file (optional).
    'headers':
      A keyed array with headers (optional).

  You can set these in $params either before calling drupal_mail() or in hook_mail()
  and of course hook_mail_alter().

  Normally, Mime Mail uses email addresses in the form of "name" <address@host.com>,
  but PHP running on Windows servers requires extra SMTP handling to use this format.
  If you are running your site on a Windows server and don't have an SMTP solution such
  as the SMTP module installed, you may need to set the 'Use the simple format of
  user@example.com for all email addresses' option on the configuration settings page.

  This module creates a user preference for receiving plaintext-only messages.
  This preference will be honored by all messages if the format is not explicitly set
  and the user has access to edit this preference (allowed by default).

  Email messages are formatted using the mimemail-message.tpl.php template.
  This includes a CSS style sheet and uses an HTML version of the text.
  The included CSS is either:
    the mail.css file found anywhere in your theme folder or
    the combined CSS style sheets of your theme if enabled.

  Since some email clients (namely Outlook 2007 and GMail) is tend to only regard
  inline CSS, you can use the Compressor to convert CSS styles into inline style
  attributes. It transmogrifies the HTML source by parsing the CSS and inserting the
  CSS definitions into tags within the HTML based on the CSS selectors. To use the
  Compressor, just enable it.

  To create a custom mail template copy the mimemail-message.tpl.php file from
  the mimemail/theme directory into your default theme's folder. Both general and
  by-mailkey theming can be performed:
    mimemail-message--[module]--[key].tpl.php (for messages with a specific module and key)
    mimemail-message--[module].tpl.php (for messages with a specific module)
    mimemail-message--[key].tpl.php (for messages with a specific key)
    mimemail-message.tpl.php (for all messages)

  Messages can be rendered using different themes. You can choose the following
  settings to render the e-mail:
    'current': Theme currently used by the user who runs drupal_mail().
    'default': Default theme, obtained via variable theme_default.
    'domain': Theme obtained via Domain Theme module.
  or any other active theme.

  Images with absolute URL will be available as remote content. To embed images
  into emails you have to use a relative URL or an internal path. Due to security
  concerns, only files residing in the public file system (e.g sites/default/files)
  can be used by default.

  For example:
    instead of http://www.mysite.com/sites/default/files/mypicture.jpg
    use /home/www/public_html/drupal/sites/default/files/mypicture.jpg
    or /sites/default/files/mypicture.jpg
    or public://mypicture.jpg

  The 'send arbitrary files' permission allows you to attach or embed files located
  outside Drupal's public files directory. Note that this has security implications:
  arbitrary means even your settings.php! Give to trusted roles only!

LICENSE
-------

This project is GPL v2 software. See the LICENSE.txt file in this directory for complete text.

CREDITS
-----------

This module is based on the Mimemail module for Drupal, originally written and maintained by a large number of contributors, including:

Robert Castelo <https://www.drupal.org/user/3555>
Gerhard Killesreiter <https://www.drupal.org/user/227>
Allie Micka <https://www.drupal.org/user/15091>
Gabor Seljan <https://www.drupal.org/user/232117>

MAINTAINERS
-----------

- seeking

Ported to Backdrop by:

 - biolithic <https://github.com/biolithic>
