Source for telldus-core to be used with a Telldus Tellstick (old model that only works for transmitting (turning on/off) 433 MHz devices).
Source is slightly modified from a repo I found at Telldus, to allow it to be compiled with my current Debian as per 2024-04-15.

Build with cmake etc..

TellStick_conf.html contains some info how to configure the /etc/tellstick.conf configuration file to allow for devices to be remote controlled.

Start by running telldusd daemon and then control with tdtool.
I enabled telldusd as a systemd service to have it start after each reboot; and used "crontab -e" to configure devices to be turned on/off at specific times.
