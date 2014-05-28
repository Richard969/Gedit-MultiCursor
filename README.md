Gedit-MultiCursor
=================

A plugin for gedit 3+ that adds multiple cursor support as popularized by [Sublime Text](http://www.sublimetext.com/). Not all features are implemented yet, see below for details about what is and isn't supported.

Installing
==========

By cloning the repo:

    $ git clone git@github.com:jessecrossen/Gedit-MultiCursor.git
    $ cd Gedit-MultiCursor
    $ ./install.sh
    
By unpacking a snapshot:

    $ wget https://github.com/jessecrossen/Gedit-MultiCursor/archive/master.zip
    $ unzip master.zip
    $ cd Gedit-MultiCursor-master
    $ ./install.sh

Then restart gedit from the console and enable the MultiCursor plugin in the preferences dialog. If you see something like this in your console output:

    (gedit:4579): libpeas-WARNING **: Could not find loader 'python3' for plugin 'multicursor'
    
Edit the second line of multicursor.plugin to read as follows:

    Loader=python
    
Then re-run install.sh and try again from there.

Configuration
=============

There's no configuration UI yet, but it would be great if someone handier than me with Gtk would write one! You can change the keyboard shortcuts by editing the strings at the top of multicursor.py. Sorry if you liked using **Control-d** to delete a line, but it should be pretty easy to change if you want to.

Usage
=====

You can add a cursor by selecting some text and using the **Control-d** shortcut. All instances of that text will be highlighted, and the next one will get a cursor around it. Use **Control-u** to remove the last cursor you added. Start typing, move the cursor, or delete to modify the text at all the current cursors. You can also add cursors anywhere by clicking while holding down the **Control** key. Use **Escape** or click anywhere to go back to one cursor.

Shortcomings
============

* Support for undo is fairly bad, and will actually mess up your document. I'm working on understanding gedit's undo system better so I can improve on that.
* As mentioned above, there's not an easy way to configure the plugin.
* All matching is case sensitive right now. I'm working on that plus an even cooler feature relating to casing conventions. Stay tuned.
* Column selection mode isn't supported yet.
* The extra cursors don't blink like the main one. Maybe it's a feature?


