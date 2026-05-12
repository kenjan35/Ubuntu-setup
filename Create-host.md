## Create the Dockerfile

We use Alpine because it contains busybox by default.

*Note: BusyBox - The Swiss Army Knife of Embedded Linux

- Syntax:
  busybox <applet> [arguments...]

BusyBox combines tiny versions of many common UNIX utilities into a single small executable.
It provides minimalist replacements for most of the utilities you usually find in GNU coreutils, util-linux, etc.

You can also invoke BusyBox by issuing a command as an argument on the command line. For example, entering:
  /bin/busybox ls*
