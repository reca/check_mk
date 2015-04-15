# check_mk

## check_mk Plugins
This repository contains unofficial check_mk plugins or changes to official check_mk plugins.

### some ideas
* compare Cisco Nexus Cluster switch profile, useful when not using config-sync
* count switchports depending on their description (e.g. for free capacity reasons)

#### Extension to if.include for counting LACP members (cisco specific)
* CISCO-LAG-MIB returns an octet string where the first two octets counts  the LACP members

`$ snmpwalk -v2c -c$SOME_COMMUNITY $SOME_HOST ifAlias | grep 369098978
IF-MIB::ifAlias.369098978 = STRING: $SOME_DESCRIPTION`

`$ snmpwalk -v2c -c$SOME_COMMUNITY $SOME_HOST 1.3.6.1.4.1.9.9.225.1.4.1 | grep 369098978
SNMPv2-SMI::enterprises.9.9.225.1.4.1.1.1.369098978 = Hex-STRING: 00 02 XX XX XX XX`

