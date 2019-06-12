# xkeypass

A command-line tool that performs CRUD operations on json-formatted records
stored with password-store.

## Website

* [Website](https://github.com/rpdelaney/xkeypass)

## Installation

To install, copy `xkeypass` into your $PATH.

### Dependencies

xkeypass depends on:

* [password-store](http://www.zx2c4.com/projects/password-store/) by Jason Donenfeld
* [jshon](http://kmkeen.com/jshon/) by Kyle Keen

Optional dependency:

* [xdotool](http://www.semicomplete.com/projects/xdotool/) by Jordan Sissel

If xdotool is not available, xkeypass won't be able to type passwords.

## Usage

```
xkeypass acts as a front-end to pass, extracting stored json data types.

Usage: xkeypass [OPTION] TITLE COMMAND KEY

Options
  -?, --help                  print this help and exit
  -v, --verbose               increase verbosity of debugging output

Commands
  a, add                      create a new record named TITLE
  d, del KEY                  delete a key from TITLE
  g, get KEY                  retrieve a key from TITLE
  s, select KEY               print TITLE in json format to standard output
  u, update KEY VALUE         update or create a key in TITLE. if VALUE is -
                              then read from standard input
  x, drop                     remove the record TITLE from the password store
  t, type KEY                 type the key with xdotool
  p, password [LENGTH]        generate a secure password using pwgen and update
                              "password" with the new value.
  c, clip KEY                 copy KEY to the X clipboard
```

## Integration with X

The `xkeypass type` command can come in handy if your window manager supports
customizable key bindings. For example, I use the following in my i3 config:

```
bindsym $mod+w exec i3-input -F 'exec xkeypass %s type password'
```

By pressing $mod+w I can enter the record title. pinentry will prompt for the
password to unlock the password store, then xkeypass types the password at the
current cursor position.

## To-Do / known issues

* Print a warning or require confirmation when a stored password would include
  characters outside of 7-bit ASCII: this can lead to broken passwords when the
  encoding changes for any reason
* Support json arrays
* Doesn't type whitespace characters if they are found in the key

## Legal

This program is free software: you can redistribute it and/or modify it
under the terms of the GNU General Public License as published by the
Free Software Foundation, either version 3 of the License, or (at your
option) any later version.

You should have received a copy of the GNU General Public License along
with this program.  If not, see <http://www.gnu.org/licenses/>.
