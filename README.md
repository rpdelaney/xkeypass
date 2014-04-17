##xkeypass
A command-line tool that performs CRUD operations on json-formatted records stored with pass.

#####Website
* [Website](https://github.com/rpdelaney/xkeypass)

##Installation
xkeypass depends on [pass](http://www.zx2c4.com/projects/password-store/) by Jason Donenfeld and [jshon](http://kmkeen.com/jshon/) by Kyle Keen.

To install, copy `xkeypass` into your $PATH.

##Usage
```
xkeypass acts as a front-end to pass, extracting stored json data types.

Usage: xkeypass [OPTION] [COMMAND] [FIELD] [VALUE]

Options
  -?, --help                  print this help and exit
  -v, --verbose               increase verbosity
  a, add [FIELD] [VALUE]      add a new field
  d, del [FIELD]              delete a field
  g, get [FIELD]              extract a field and decode it
  u, update [FIELD] [VALUE]   update a field with a new value
```

##To-Do
* Type the passwords using xdotool
