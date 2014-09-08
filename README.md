# Zabbix SNMP Template Builder

zload_snmpwalk builds templates for Zabbix 2.2 by using snmpwalk

## Changelog

* v2.0.0 This script has been updated so that the XML output works in Zabbix 2.2.6.
 Testing was done by running the following command and then importing the resulting
 XML file into Zabbix via the web interface:

 `$ zload_snmpwalk -v1 -mALL -x public PrinterMIB 10.10.27.6 printmib > PrinterMIB.xml`

 The version number was extended to 3 digits so as to more accurately represent the
 types of changes expected to come as more testing is done.

* v1.1 (develop@dieploegers.de)  
 Changed arguments ”-r” and ”-d” to ”-R” and ”-D” to avoid double arguments 
 (thanks to Raymond)

* v1.0 (develop@dieploegers.de)  
 * Added a version number ;-)
 * Added the argument ”-r” to alter the way, the script generates the description. It
  usually uses the mib-parsed oid and cuts off the two last indexes and uses that as
  the description. Sometimes this is to few (I got 1.1 and 1.2 as descriptions and
  keys). The ”-r”-argument can change the number of these cuts
 * Added snmp-version “3” (very basic tough with no extra v3-attributes)
 * Added a check, so that v1-snmpwalks will produce v1-items and v2c-snmpwalks will
  produce v2c-items

* v0.1 - Design phase

