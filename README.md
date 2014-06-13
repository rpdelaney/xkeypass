##xkeypass
A command-line tool that performs CRUD operations on json-formatted records
stored with pass.

#####Website
* [Website](https://github.com/rpdelaney/xkeypass)

##Installation
#####Dependencies
xkeypass depends on:

* [xdotool](http://www.semicomplete.com/projects/xdotool/) by Jordan Sissel
* [pass](http://www.zx2c4.com/projects/password-store/) by Jason Donenfeld
* [jshon](http://kmkeen.com/jshon/) by Kyle Keen

To install, copy `xkeypass` into your $PATH.

##Usage
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
  t, type KEY                 type the key with xdotool
  p, password TITLE [LENGTH]  generate a secure password using pwgen and update
                              "password" with the new value.
```

##Integration with X
The `xkeypass type` command can come in handy if your window manager supports
customizable key bindings. For example, I use the following in my i3 config:

```
bindsym $mod+w exec i3-input -F 'exec xkeypass %s type password'
```

By pressing $mod+w I can enter the record title, and xkeypass will prompt for
the password to unlock the password store, then type the password at the
current cursor position.

##To-Do / known issues
* xdokey cannot handle some symbols in passwords
* xdokey could theoretically expose passwords through the process name
* Print a warning or require confirmation when a stored password would include
  characters outside of 7-bit ASCII: this can lead to broken passwords when the
  encoding changes for any reason
* Support json arrays

##Legal
This program is free software: you can redistribute it and/or modify it
under the terms of the GNU General Public License as published by the
Free Software Foundation, either version 3 of the License, or (at your
option) any later version.

You should have received a copy of the GNU General Public License along
with this program.  If not, see <http://www.gnu.org/licenses/>.

####TERMS AND CONDITIONS
© Copyright 2014 Ryan Delaney. All rights reserved.

THERE IS NO WARRANTY FOR THE PROGRAM, TO THE EXTENT PERMITTED BY
APPLICABLE LAW.  EXCEPT WHEN OTHERWISE STATED IN WRITING THE COPYRIGHT
HOLDERS AND/OR OTHER PARTIES PROVIDE THE PROGRAM “AS IS” WITHOUT
WARRANTY OF ANY KIND, EITHER EXPRESSED OR IMPLIED, INCLUDING, BUT NOT
LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A
PARTICULAR PURPOSE. THE ENTIRE RISK AS TO THE QUALITY AND PERFORMANCE
OF THE PROGRAM IS WITH YOU.  SHOULD THE PROGRAM PROVE DEFECTIVE, YOU
ASSUME THE COST OF ALL NECESSARY SERVICING, REPAIR OR CORRECTION.

IN NO EVENT UNLESS REQUIRED BY APPLICABLE LAW OR AGREED TO IN WRITING
WILL ANY COPYRIGHT HOLDER, OR ANY OTHER PARTY WHO MODIFIES AND/OR
CONVEYS THE PROGRAM AS PERMITTED ABOVE, BE LIABLE TO YOU FOR DAMAGES,
INCLUDING ANY GENERAL, SPECIAL, INCIDENTAL OR CONSEQUENTIAL DAMAGES
ARISING OUT OF THE USE OR INABILITY TO USE THE PROGRAM (INCLUDING BUT
NOT LIMITED TO LOSS OF DATA OR DATA BEING RENDERED INACCURATE OR LOSSES
SUSTAINED BY YOU OR THIRD PARTIES OR A FAILURE OF THE PROGRAM TO
OPERATE WITH ANY OTHER PROGRAMS), EVEN IF SUCH HOLDER OR OTHER PARTY
HAS BEEN ADVISED OF THE POSSIBILITY OF SUCH DAMAGES.

If the disclaimer of warranty and limitation of liability provided
above cannot be given local legal effect according to their terms,
reviewing courts shall apply local law that most closely approximates
an absolute waiver of all civil liability in connection with the
Program, unless a warranty or assumption of liability accompanies a
copy of the Program in return for a fee.
