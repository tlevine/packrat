PackRat: Backups that you can't delete
=====

I back things up on email, SmugMug, Google Docs, &c. rather than on my own
hardware because it's **hard to delete** them from these services; the delete
buttons are buried inside of menus, and that button normally puts the stuff
in some intermediate place (the "trash") before deleting them.

Why not have a more general, less clumsy thing that works like that?

I propose a tool that makes it easy to take backups and hard to delete them.
Let's call it "PackRat". Minimally, it has a command-line interface with four
text commands.

    # Upload one file. Name clashes are reported;
    # existing files are never overwritten.
    packrat put foobar.tar.gz
    
    # List the files that have been uploaded
    packrat list

    # Retrieve one file that has been backed up
    packrat get foobar.tar.gz
    
    # "Trash" a file. The file will be deleted in 30 days, and multiple
    # stages of confirmation will be requested.
    packrat delete foobar.tar.gz

It could also have more commands and be a website and whatnot.
If I make it, there will probably be a minimal client that sends files and
commands to a server over SSH. The server would send files to some storage
backend, like a cloud hosting provider or a distributed filesystem.

If I made this and let you use it for free, would you use it?
