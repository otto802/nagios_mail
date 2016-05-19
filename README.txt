Extended Nagios Notification Mail

INSTALL:

replace the notifying definitions in the misccomands.cfg. Make sure that PHP
is installed and the path to the PHP-binary is correct.


# Example misccommands.cfg
define command{
      command_name    host-notify-by-email
      command_line    /usr/bin/php -q /opt/nagios_mail.php
      }

define command{
      command_name    notify-by-email
      command_line    /usr/bin/php -q /opt/nagios_mail.php
      }


CONFIGURATION:

configure your domain address etc. at the top of the nagios_mail.php file.


TEST:

put your email-address in $config["mail_add_to_address"] statement. 
Then run the script from command-line:

/usr/bin/php -q /opt/nagios_mail.php

You should recieve a test-email to the specified address.


@author     Otto Berger <otto@bergerdata.de>
@copyright  Copyright (c) 2009, Otto Berger
@license    http://opensource.org/licenses/lgpl-license.php GNU Lesser General Public License
@version    $Id$
