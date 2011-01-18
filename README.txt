// $Id$

Description
===========
Iran.tc SMS Gateway enables the smsframework (http://drupal.org/project.smsframework) to use Iran.tc (http://iran.tc/) service as a gateway.

Requirements
============
- A valid line number, username and password provided by Iran.tc.


Dependencies
============
- SOAP Client (http://drupal.org/project/soapclient)


Installation
============
1. Install & enable SOAP Client (http://drupal.org/project/soapclient).
  - Go to admin/settings/soapclient.
  - Under "Active SOAP Library" check the "nuSOAP" option.
  - Leave other options as default.
  
2. Install and enable Iran.tc SMS Gateway (http://drupal.org/project/sms_irantc)
  - Go to admin/smsframework/gateways/irantc.
  - Fill the required fields by the credentials provided by Iran.tc.
  - Leave other fields as their defaults and save the configuration.

3. If you wish to also be able to receive SMS messages:
  - Go to admin/smsframework/gateways/irantc.
  - Copy the URL under the Incoming SMS Settings section labeled "Traffic Relay Gateway".
  - Login to your Iran.tc (http://iran.tc/) control panel at their website.
  - Under "Web Services" menu, click on "Incoming messages", paste the URL and save.


Important Notice
================
Unfortunately nuSOAP library is written in PHP4 style and in my opinion it could be better in its configuration and design.
Anyway You need to change the nuSOAP class charset encoding configs manually to make this module work properly, otherwise you'll get something like:

    Error in msg parsing:
    Charset from HTTP Content-Type 'UTF-8' does not match encoding from XML declaration 'ISO-8859-1'.
    
To prevent this, open the `nusoap.php` file and:
    
    // Change this:
    var $soap_defencoding = 'ISO-8859-1';
    
    // To:
    var $soap_defencoding = 'UTF-8';


Author and Maintainer
=====================
sepehr (Sepehr Lajevardi)

