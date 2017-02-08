# NOTICE: This Software is distributed under GNU GENERAL PUBLIC LICENSE (see LICENSE.txt) and comes with absolutely NO WARANTY. It's a fork of https://github.com/AlertusTechnologiesLLC/yaai with modifications for SuiteCRM and Asterisk 13

# PLease backup all your Data before installing this software.

# preparation
You will need:
- shell access to your SuiteCRM
- admin privileges in your SuiteCRM
- forwarded the asterisk manager api (Port 5038) to your SuiteCRM machine.
- asterisk manager credentials

# module setup
- login into SuiteCRM with admin privileges
- go to Module Loader, upload yaai-2017-01-07.zip and install module.
- accept the GPL if you want to
- continue to module configuration (further editing: admin dashboard->callinize)
- edit Asterisk host, login, port and secret
- edit Sugar CRM SOAP user and password
- edit if necessary: Dialout Prefix and Dial Context
- save

# customizing user management
- go to admin dashboard and choose Studio
- on the left choose Users, Layouts, EditView
- create a new panel from the toolbox and drag a new row into panel (2 rows needed)
- drag Fields "Personal Extensions", "Magic Dialbuttons" and "Call notification" into your panel
- label your panel with "cti" or sth else
- save & deploy your changes

# edit cti enabled user
- go to admin dashboard and choose User management.
- edit your user
- on your created panel edit user extensions and set both checkboxes
- User extensions must be a sip interface WITHOUT "SIP/"
- save user

# start the daemon
- login to your SuiteCRM machine via ssh or console
- change dir to SuiteCRM_Root/custom/modules/Asterisk
- start php asteriskLogger.php and test your installation by calling your extension
- if youre happy with the installation, use the asterisk_logger from misc as init script (edit USER, SUGAR_ROOT and PHP_BIN)
