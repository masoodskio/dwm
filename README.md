## Sofian's build of DWM - dynamic window manager
dwm is an extremely fast, small, and dynamic window manager for X.
I've added the following patches
-Vanitygaps: Gaps allowed across all layouts

-Sticky: Windows can be made sticky (super+s)

-True fullscreen (super+f) and prevents focus shifting

-Stacker: Move windows up the stack manually (super+K/J)

-Shiftview: Cycle through tags (super+semicolon/super+apostrophe;)

-ShiftTag: Move windows to prev/next tag (supet+shift+semicolon/super+shift+apostrophe

-Swallow: If a program run from a terminal would make it inoperable, it temporarily takes its place to save space.

-It reads colors from Xresources (works with pywal)

## Requirements

In order to build dwm you need the Xlib header files.

## Installation

Edit config.mk to match your local setup (dwm is installed into
the /usr/local namespace by default).

Afterwards enter the following command to build and install dwm (if
necessary as root):

    make clean install


## Running dwm

Add the following line to your .xinitrc to start dwm using startx:

    exec dwm

In order to connect dwm to a specific display, make sure that
the DISPLAY environment variable is set correctly, e.g.:

    DISPLAY=foo.bar:1 exec dwm

(This will start dwm on display :1 of the host foo.bar.)

In order to display status info in the bar, you can do something
like this in your .xinitrc:

    while xsetroot -name "`date` `uptime | sed 's/.*,//'`"
    do
    	sleep 1
    done &
    exec dwm


## Configuration

The configuration of dwm is done by creating a custom config.h
and (re)compiling the source code.



