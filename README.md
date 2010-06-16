# surf.rc

A small helper script for surf which:

- on MOD+g calls dmenu to read user input

- interprets stuff like

    g rtp sdp

  as a request to google for the latter two strings.

## Usage

To use it put in it your PATH and use the following SETPROP
definition in config.h:

    #define SETPROP(p, q)     { .v = (char *[]){ "/bin/sh", "-c", \
	    "surf.rc $0 $1 $2",\
	    p, q, winid, NULL } }

## Notes

This script is heavily inspired by the original shell version
surf.sh from the suckless mailing list.
