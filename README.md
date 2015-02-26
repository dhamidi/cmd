# Description

This repository contains little, useful (at least for me) scripts that
make using existing software more convenient.  It was created in an
attempt to move complexity away from single, monolithic programs (vim)
and platforms (emacs).  The goal is to have many small tools that work
together well and consantly add to this set of tools.  Due to this, the
configuration in this repository leans towards software that is tried,
proven and provides just enough functionality to be usable (bash instead
of zsh), and implements well-known paradigms (text editing command
language -- nvi).

Modifying your existing environment should be as easy as it is in Emacs
at the moment.  This is goal is met by providing a little set of helpers.
These helpers encapsulate the knowledge about where configration files are
found and provide a uniform access layer independent of the underlying
programs.  This reduces friction when replacing individual pieces of
software, such as the text editor.

# Helpers

## `defcmd CMD`

Opens your editor to edit a script file that is on `$PATH`.  After
editing, executable permissions are added to the newly created file.
Running `defcmd` for an existing command, opens the existing script to
facilitate changes to existing configurations.

## `undefcmd CMD` 

The counterpart to `defcmd`.  Deletes the named command.

## `edit FILE`

Opens `$EDITOR` on `FILE` and runs hooks associated with the file
extension.  Editing a file named `foo.coffee` runs `after-edit-coffee`,
if such a program exists.

## `editconf`

Edits the configuration file for the current shell and then sources the
commands in that file.  Use this for modifying the behavior of your shell.
