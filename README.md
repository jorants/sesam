# Sesam
Very simple xdg-open replacement in python.
xdg-open sucks without a full desktop environment, plus, things should be simple.

## Install
Just add the `xdg-open` file in this repo to your path (before the real xdg-open) and make sure it is executable.


## Config

The configuration file is in `~/.sesam` for the user and `/etc/sesam.conf` for the system wide config.
A simple example:

	# you can simply list your mimetypes:
	application/pdf = zathura

	# mimetypes might have wildcards:
	text/* = xemacs
	video/* = mpv

	# you can use shorthands to include (parts of) the filename where needed
	uimage/* = feh <file> -.Z

	# URLs are also handled by scheme type:

	x-scheme-handler/mailto = thunderbird
	x-scheme-handler/http = firefox
	x-scheme-handler/https = firefox

	# You can even fallback on xdg-open if you would like
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


## Inspiration

This project is inspired by [mimi](https://github.com/march-linux/mimi).
However, I did not like everything about mimi, so i wrote my own.
