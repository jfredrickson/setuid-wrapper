# setuid-wrapper

Just a simple tool that can be used to start shell scripts with elevated
privileges.

## Why?

Linux ignores the setuid bit on interpreted executables (e.g., shell scripts,
interpreted languages, etc). This is for security reasons. Therefore, in order
to run a script with setuid privileges, we need to execute it from a native
binary executable that actually has the setuid bit on it. That's where this
wrapper comes into the picture: it serves as the native binary that carries the
setuid bit.

## Compiling

    gcc -o setuid-wrapper setuid-wrapper.c

## Installing

    chown root setuid-wrapper
    chmod 4755 setuid-wrapper

## Usage

Assuming myscript.sh is the script you want to run with elevated privileges,
create a script that contains:

    #!/bin/sh
    /path/to/setuid-wrapper /path/to/myscript.sh

Then just run the above script in order to execute myscript.sh with superuser
privileges.

## Security Warning

Note that this is a personal tool.  It wasn't designed with multiuser security
in mind.  Pretty much anyone will be able to execute anything with superuser
privileges by using this script.
