# Screen

Screen is a useful program for mantaining terminal sessions, allowing the user to attach & deattach them at will. The most useful use-case I've found is keeping non-daemon programs running between SSH sessions, such as IRC.

Each screen can have a series of windows attached to it too, these are essentially more terminal sessions associated with the screen terminal session. It gets a bit complicated to explain.

Screen can get some weird rendering artifacts, especially when running in conjunction with things like Lynx. It's not too much to worry about though.

## Controls

### Out of screen

* `screen` - start a new session.
* `screen -ls` - get a list of the current screen sessions.
* `screen -r <screen id>` - reattach a session.
* `screen -d <screen id>` - dettach a session. A use-case being if you're SSH'd into a server twice & want to swap which SSH session has control over a particular session, it needs to be dettached & then reattached.

### In screen

The majority of the in-screen controls are accessed after the `CTRL`, `a` keys.

* `CTRL` + `a` `d` - deattach the current session.
* `CTRL` + `a` `"` - gets a list of associated windows.
* `CTRL` + `a` `c` - creares a new window.
* `CTRL` + `a` `n` - next window.
* `CTRL` + `a` `p` - previous window.
* `CTRL` + `a` `<number of window>` - go to certain window.
* `CTRL` + `a` `k` - destroy the current window (`CTRL` + `d` (bash) will work too).
