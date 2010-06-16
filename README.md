# surf.rc

A small helper script for surf which, on:

- MOD+g calls dmenu to read user input interprets stuff like

      g rtp sdp

  as a request to google for the latter two strings.

- MOD+b adds a bookmark to a preconfigured file

## Usage

### Installation

To use it put in it your PATH and use the following SETPROP
definition in config.h:

    #define SETPROP(p, q)     { .v = (char *[]){ "/bin/sh", "-c", \
	    "surf.rc $0 $1 $2",\
	    p, q, winid, NULL } }

and add

    { MODKEY, GDK_b, spawn, SETPROP("_SURF_BMARK", "_SURF_B    MARK") },

to the keys array.

### Googling

`g <word>[ <word>]*`

or

`<word>[ <word>]+`

(a single `<word>` is interpreted as an URL)


## Notes

This script is heavily inspired by the original shell version
surf.sh from the suckless mailing list.

See also:

  - [surf at suckless](http://surf.suckless.org)

  - [bmarks script at
    suckless](http://surf.suckless.org/files/bmarks)
