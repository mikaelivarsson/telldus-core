
CMAKE_MINIMUM_REQUIRED( VERSION 2.4.0 )

SET(BUILD_PLUGIN_TELLDUS-CORE	TRUE	CACHE BOOL "Build plugin 'TelldusCore'")

IF (BUILD_LIBTELLDUS-GUI)
	SET(BUILD_PLUGIN_DEVICES	TRUE	CACHE BOOL "Build plugin 'Devices'")
	SET(BUILD_PLUGIN_SYSTRAY	TRUE	CACHE BOOL "Build plugin 'Systray'")
ENDIF (BUILD_LIBTELLDUS-GUI)

SET(BUILD_PLUGIN_DBUS	FALSE	CACHE BOOL "Build plugin 'DBus'")
SET(BUILD_PLUGIN_LIVE	FALSE	CACHE BOOL "Build plugin 'Telldus Live!'")
SET(BUILD_PLUGIN_XPL	FALSE	CACHE BOOL "Build plugin 'xPL'")
SET(BUILD_PLUGIN_SCHEDULERGUISIMPLE	FALSE	CACHE BOOL "Build plugin 'Simple Scheduler GUI'")
SET(BUILD_PLUGIN_SENSORS	TRUE	CACHE BOOL "Build plugin 'Sensors'")

ADD_SUBDIRECTORY(telldus)

IF(BUILD_PLUGIN_TELLDUS-CORE)
	ADD_SUBDIRECTORY(TelldusCore)
ENDIF(BUILD_PLUGIN_TELLDUS-CORE)

IF(BUILD_PLUGIN_DEVICES)
	ADD_SUBDIRECTORY(Devices)
ENDIF(BUILD_PLUGIN_DEVICES)

IF(BUILD_PLUGIN_SYSTRAY)
	ADD_SUBDIRECTORY(Systray)
ENDIF(BUILD_PLUGIN_SYSTRAY)

IF(BUILD_PLUGIN_DBUS)
	ADD_SUBDIRECTORY(DBus)
ENDIF(BUILD_PLUGIN_DBUS)

IF(BUILD_PLUGIN_LIVE)
	ADD_SUBDIRECTORY(Live)
ENDIF(BUILD_PLUGIN_LIVE)

IF(BUILD_PLUGIN_SENSORS)
	ADD_SUBDIRECTORY(Sensors)
ENDIF()

IF(BUILD_PLUGIN_XPL)
	ADD_SUBDIRECTORY(xPL)
ENDIF(BUILD_PLUGIN_XPL)

IF(BUILD_PLUGIN_SCHEDULERGUISIMPLE)
	ADD_SUBDIRECTORY(SchedulerGUISimple)
ENDIF(BUILD_PLUGIN_SCHEDULERGUISIMPLE)

IF(REQUIRE_PLUGIN_SCHEDULER)
	ADD_SUBDIRECTORY(Scheduler)
ENDIF(REQUIRE_PLUGIN_SCHEDULER)

IF(REQUIRE_PLUGIN_SUNCALCULATOR)
	ADD_SUBDIRECTORY(SunCalculator)
ENDIF(REQUIRE_PLUGIN_SUNCALCULATOR)

IF(REQUIRE_PLUGIN_QML)
	ADD_SUBDIRECTORY(QML)
ENDIF(REQUIRE_PLUGIN_QML)

IF(REQUIRE_PLUGIN_SETTINGS)
	ADD_SUBDIRECTORY(Settings)
ENDIF(REQUIRE_PLUGIN_SETTINGS)
