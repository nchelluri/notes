Notes in Bash
-------------

Quick Notes from the terminal, anywhere.

Installing
----------
Run the following:

    git clone https://github.com/nchelluri/notes.git ~/bin/notes
    mkdir ~/.notes

Then add:

    source ~/bin/notes/notes

to `~/.profile` or `~/.bash_profile`

Done.

Using
-----

Now you should be able to use Notes, like so:

    notes              # to list all notes
    new-note asdf      # to create a note named asdf
    note as<TAB>       # to view the note named asdf
    edit-note asdf     # to edit the note named asdf
    archive-note asdf  # to move the note named asdf to $NOTES_DIR/.archive
