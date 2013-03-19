# setuid-wrapper

Just a simple tool that can be used to start shell scripts with elevated
privileges.

## Compiling

    gcc -o setuid-wrapper setuid-wrapper.c

## Installing

    chmod 4755 setuid-wrapper

## Usage

Assuming myscript.sh is the script you want to run with elevated privileges,
create a script that contains:

    #!/bin/sh
    /path/to/setuid-wrapper /path/to/myscript.sh

Then just run the above script in order to execute myscript.sh with superuser
privileges.

Note that this is a personal tool.  It wasn't designed with multiuser security
in mind.  Pretty much anyone will be able to execute anything with superuser
privileges by using this script.
