
This greatly reduces the number of commands in nushell down to
around 20 commands.  In order to do this the following files
get either modified or deleted...

There are many things you can do and test with a reduced command
set but the simple functionality to witness in this branch is

* help commands

to see a greatly reduced command set in action...

### The following commands are being presented:

* autoenv, autoview, clear, debug, def
* echo, exit, flatten, get, help
* history, let, let-env, ls, pivot
* source, table, touch, uniq, version
* with-env

The following 3 files get modified:

* src/commands.rs
* src/commands/default_context.rs
* src/prelude.rs

This file gets completely commented out:

* src/commands/constants.rs

The following 2 files get deleted:

* from_delimited_data.rs, to_delimited_data.rs
