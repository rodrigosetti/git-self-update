# Git Self Update

The purpose of this project is to allow you install a self-updating script for
a production environment files where the production environment is severely
limited without tools like git or any scripting language except shell script.

The goal is to use this script as a cron job (or called by a cron script) to
pull new stable code from github and update the production files.

The script only fetches and updates new files, it doesn't restart services or
set configurations. This must be carried by adjacency scripting.

The usage is:

    self-update.sh <github's username> <github's repo name> [stable ref] [destination folder] [excluded patterns]

 * The stable ref is optional and defaults to heads/master.
 * The destination dir is optional and defaults to current dir.
 * The excluded patterns are a list (enclosed in quotes) of patterns of files to be not overwritten.

There is no backup of older data. It's not the purpose of the script.

## Examples

    $ ./self-update.sh johnsmith my-site

    $ ./self-update.sh johnsmith my-site 'heads/stable'

    $ ./self-update.sh johnsmith my-site 'heads/stable' /var/www/site

    $ ./self-update.sh johnsmith my-site 'heads/stable' /var/www/site 'README *.sql config.php'

## TODO

 * Unix style command line and help

