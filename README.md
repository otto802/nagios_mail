
# Extended Nagios Notification Mail

## INSTALL

* replace the notifying definitions in the misccomands.cfg
* Make sure that PHP is installed and the path to the PHP-binary is correct.


## Example misccommands.cfg

```
define command {
      command_name    host-notify-by-email
      command_line    /usr/bin/php -q /opt/nagios_mail.php
      }

define command {
      command_name    notify-by-email
      command_line    /usr/bin/php -q /opt/nagios_mail.php
      }
```

## CONFIGURATION

* configure your domain address etc. at the top of the nagios_mail.php file.


## TEST

* put your email-address in $config["mail_add_to_address"] statement.
* Then run the script from command-line:

```
/usr/bin/php -q /opt/nagios_mail.php
```

* You should recieve a test-email to the specified address.

## FAQ

    Q: i want to use ICINGA with it. Is it possible?
    A: Yes, but you have to replace in Line 643 „_NAGIOS“ with „_ICINGA“

    Q: Notifications through Nagios/Ichinga are empty. What to check?
    A: check your php.ini for variables_order = “EGPCS”, the „E“ is important.

    Q: Notifications through Nagios/Ichinga are still empty. What to check?
    A: check nagios.cfg/icinga.cfg for the following setting: enable_environment_macros=1


## Author

```
@author     Otto Berger <otto@bergerdata.de>
@copyright  Copyright (c) 2009, Otto Berger
@license    http://opensource.org/licenses/lgpl-license.php GNU Lesser General Public License
@version    $Id$
```
