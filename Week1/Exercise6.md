# Creating and editing files with Vim
```
theia@theia-quyduong106:/home/project$ vim
help.txt        For Vim version 8.0.  Last change: 2017 Oct 28

                        VIM - main help file
                                                                         k
      Move around:  Use the cursor keys, or "h" to go left,            h   l
                    "j" to go down, "k" to go up, "l" to go right.       j
Close this window:  Use ":q<Enter>".
   Get out of Vim:  Use ":qa!<Enter>" (careful, all changes are lost!).

Jump to a subject:  Position the cursor on a tag (e.g. bars) and hit CTRL-].
   With the mouse:  ":set mouse=a" to enable the mouse (in xterm or GUI).
                    Double-click the left mouse button on a tag, e.g. bars.
        Jump back:  Type CTRL-T or CTRL-O.  Repeat to go further back.

Get specific help:  It is possible to go directly to whatever you want help
                    on, by giving an argument to the :help command.
                    Prepend something to specify the context:  help-context

                          WHAT                  PREPEND    EXAMPLE
                      Normal mode command                  :help x
help.txt [Help][RO]                                                                    
```


When you're done typing text in the buffer, press the Escape key, Esc, to exit the Insert mode. This brings you to Command mode.

In Vim, it's easy to accidentally end up in a mode you didn't intend to be in. No worries - you can use the Esc key to return to Command mode.

Now that you are back in Command mode, you can save your work by entering the command :w. This writes the contents of the text buffer to your text file.

Finally, you can exit your Vim session by entering :q.
```
theia@theia-quyduong106:/home/project$ vim
theia@theia-quyduong106:/home/project$ vim hello_world_2.txt
theia@theia-quyduong106:/home/project$ cat hello_world_2.txt
Hello World!
This is the second line.
```