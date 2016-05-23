Decode UKHASnet packets with a RTL SDR dongle
==================

This is a simple UKHASnet decoder for RTL SDR dongles. Other similar decoder might already exist but this was a way for me to understand the protocol and get used to it.

You need to have a working dongle and rtl_fm running.

Before starting
-------
`rtl_test`

`rtl_test -p 10` to get ppm error or use kalibrate but it did not work for me on OSX.

Gateway Name
-------
The compile time default is now configured via the makefile and is set to UKHASGW by default, This can be overridden by editing the makefile.

You can also specify the name to use at run time by adding the -n flag, this will override the default value. Unless running in Quiet mode it will display, at start up, whether the deafult Gateway or provided name is being used.

Get started
-------
`make`

`./UKHASnet-decoder -h`

Compiling for Windows
-------
It's possible to Cross Compile a windows .exe version from a Raspberry Pi (or other Linux System).
You will need the mingw-w64 toolchain (these are different to the Mingw32 toolchain) and libraries for zlib, openssl and curl.
Details for setting up the environment are avaialble at: https://ukhas.net/wiki/guides:rtlsdr_decoder_windows

TODO (see code for details)
-------
- Synchronisation:
	- Add tolerance bit option (and possibly use the preamble for more robustness)
	- Support inverted bits
- Confirm that RFM CRC computation is weird (has someone had some experience with that ?)
- Find better threshold formula to account for packet with no sufficient bit transitions
