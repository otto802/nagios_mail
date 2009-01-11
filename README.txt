Extended Nagios Notification Mail

Install:

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


Configuration:

configure your domain address etc. at the top of the nagios_mail.php file.


@author     Otto Berger <otto@bergerdata.de>
@copyright  Copyright (c) 2009, Otto Berger
@license    http://opensource.org/licenses/lgpl-license.php GNU Lesser General Public License
@version    $Id$
