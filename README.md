E EDITOR
--------

`e` is a minimalistic text editor, inspired by Norton Editor for DOS.

Features
--------

- Insert/replace mode, block operations with highlighting, find and replace,
  go to line
- Written on C with `ncurses`, should compile anywhere
- Tested with
  - Ubuntu 14.04 LTS
- File loaded entirely in memory, you're limited only to what `realloc`(3) returns

Controls
--------
    Enter, Up, Down, Left, Right, Home, End, PgUp, PgDn, Del, Backspace have standard behavior
    Insert: toggle insert mode
    ^X: exit
    ^O: save file
    ^T: go to top of text
    ^B: go to bottom of text
    ^Y: delete current line
    ^Q: quote next character (put in text non printable symbol)
    ^A: go to line by number (or beginning of selection if number not specified)
    ^F: find string (not reg exp, usual string, exact case)
    ^R: replace one string by another
    ^N: repeat last operation of find or replace
    - ^B: mark begin of block (you'll see if beginning mark before ending)
    - ^E: mark end of block
    ^C: copy marked block to current position
    ^V: move marked block to current position
    ^D: delete marked block
    ^P: put (write) block in file
    ^G: get (load) block from file

Hints
-----
- You can edit binary files because `e` doesn't format anything
- To reset block selection put ending mark before or at beginning mark (^B^E)
- You can convert Dos files (crlf) to Unix (lf) easily: while pressing
Ctrl type trqmmmnnnnnnnnn... :)
- ...and back to Dos: trqjmqmqjmnnn...
- By analogy be careful to Ctrl while typing something like 'tboed'
- There is no auto save feature, so backup your data in time 

Bugs
----
- Many operations on every getch: erase() and COLS*LINES addch(),
but I don't think it's so bad (scrolling is optimised, so on telnet session
to 386 I feel the same speed like vi).

Copyrights
----------
- as is, no warranties at all
- you can do with this sources whatever you want, except if you use
latest version of this program and found a bug, you must inform me about it

Credits
-------
Mtv Europe <mtve1927@gmail.com>
    Initial release

Min4Builder
    Fixed Makefile, changed some keybindings and added mad(1) page
