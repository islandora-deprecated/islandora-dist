This script will:

Back up your current version of web.xml
Add both a filter and a filter-mapping element to web.xml
Back up $FEDORA_HOME/server/config/filter-drupal.xml if present
Write a fresh filter-drupal.xml.

Note:  This installation affects the Fedora installation only.  If your Drupal site accesses a remote Fedora server, the administrator of that server will have to install and configure the filter.

IF YOU CURRENTLY HAVE ENTRIES IN FILTER-DRUPAL.XML YOU WILL HAVE TO MANUALLY COMBINE THE TWO.


Mac/Unix
./InstallFilter.sh


Windows 
InstallFilter.bat