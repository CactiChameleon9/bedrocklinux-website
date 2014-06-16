Title: Bedrock Linux 1.0beta1 Hawky Known Issues
Nav: hawky.nav

# Bedrock Linux 1.0beta1 Hawky Known Issues

This page lists major known issues with the release at the time it was
released; more up-to-date information may be found at [the issue
tracker](https://github.com/bedrocklinux/bedrocklinux-userland/issues?state=open)

- [No init hooks for daemons](#init)
- [Nvidia proprietary driver installer SIGBUS's due to bru bug](#nvidia-sigbus)
- [One cannot use a client as a stand-alone system](#etc-merge)

## {id="init"} No init hooks for daemons

On typical Linux distributions, upon installing a package which should start a
daemon at boot, the package would somehow leave indications for the init system
on how it should be started.  Bedrock Linux does not currently recognize any of
these.  It is still possible to utilize daemons (start them at boot, stop at
shutdown, start/stop/restart/get-status during normal usage, etc); however, it
is up to the user to determine exactly what commands should be run to make this
happen and configure the system to do these manually.

## {id="nvidia-sigbus"} Nvidia proprietary driver installer SIGBUS's due to bru bug

The Nvidia proprietary Linux driver installer dies with SIGBUS on Bedrock Linux
1.0beta1 Hawky due, likely, to a bug in Bedrock Linux's bru utility.  The
[troubleshooting](troubleshooting.html) page has a work-around for the time
being.

## {id="etc-merge"} One cannot use a client as a stand-alone system

If one reboots into a ~{client~} as its own stand-alone system, UIDs and GIDs will
be out-of-sync from what may be on the rest of the filesystem.  There are plans
to have Bedrock Linux merge certain /etc files when enabling/disabling a ~{client~}
to remedy this, but it is not yet implemented.