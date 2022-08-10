
*check_arubaos_health* is an icinga2 check which queries AurubaOS based
switches for various health parameters.

Depending on the switch type and OS version different things are available
and will be reported.

Monitored Health Parameters:

  * Fan status e.g. hpicfFanState
  * Stack status e.g. hpStackMemberState, hpStackMemberEntryStatus
  * Sensors e.g. hpicfSensorDescr, hpicfSensorStatus
  * VSF Status e.g. hpicfVsfVCMemberState, hpicfVsfVCAdminStatus, hpicfVsfVCOperStatus
  * PSU Status e.g. hpicfPsState, 
  * Temperatures e.g. hpSystemAirCurrentTemp, hpSystemAirOverTemp

Example output:

	ARUBAOS_HEALTH OK - HP J9728A 2920-48G Switch Temp status: 25C/ok PSU status: psPowered(1) Sensor status: External Power Supply 1 Sensor=good,Over-temperature Sensor=good,Fan Sensor=good,Power Supply 3 Sensor=good,External Power Supply 2 Sensor=good,Power Supply 4 Sensor=good,Power Supply 2 Sensor=good,Power Supply 1 Sensor=good Fan status: ok(3)

	ARUBAOS_HEALTH OK - Aruba 2930F VSF VC PSU status: psPowered(2) VSF status: standby(1),commander(1) Fan status: ok(9)

	ARUBAOS_HEALTH OK - HP J9777A 2530-8G Switch Sensor status: Fan Sensor=good,Power Supply Sensor=good

	ARUBAOS_HEALTH OK - Aruba JL357A 2540-48G-PoE+-4SFP+ Switch PSU status: psPowered(1) Fan status: ok(3)

	ARUBAOS_HEALTH OK - Aruba 3810M Switch Stack Temp status: 28C/ok,28C/ok PSU status: psPowered(4) Stack status: 1=active/commander,2=active/standby Fan status: ok(15)


Usage
-----

	check_arubaos_health [-CHt] [long options...] <some-arg>
		-H STR --host STR       ArubaOS hostname
		-C STR --community STR  SNMP community
		-t INT --timeout INT    Timeout
	
		--help                  print usage message and exit

Installation
------------

You will need some perl modules. On Debian/Ubuntu based systems:

	apt-get install libnet-snmp-perl liblist-moreutils-perl \
		libmonitoring-plugin-perl libgetopt-long-descriptive-perl 
		
