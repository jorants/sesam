# Sesam
Very simple xdg-open replacement in python.
xdg-open sucks without a full desktop environment, plus, things should be simple.

## Install
Just add the `xdg-open` file in this repo to your path (before the real xdg-open) and make sure it is executable.


## Config

The configuration file is in `~/.sesam` for the user and `/etc/sesam.conf` for the system wide config.
A simple example:

	text/* = emacs
	image/* = feh <file> -.Z
	x-scheme-handler/mailto = thunderbird
	video/* = mpv
	# or, even fall back:
	* = /usr/bin/xdg-open


### Shorthands

You can use the following shorthand to the path for a filetype:

 - `<filename>` - name of the file, without the path.
 - `<folder>` - the folder of the file without the filename.

For URLs you can use the following shorthand:

 - `<scheme>` - URL scheme that was matches
 - `<path>` - Everything after the scheme

For both file types and URLs you can add:

 - `<mime>` - the mimetype that was matched
 - `<file>` - full path as passed

If no shorthand is present, then the the full filename is added at the end of the command.
