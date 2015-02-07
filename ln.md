# ln

POSIX 7: <http://pubs.opengroup.org/onlinepubs/9699919799/utilities/ln.html>

Make hardlinks and symlinks

This can also be done with `cp`

Hardlink:

    ln dest name

Symlink files only:

    ln -s dest name

Symlink dir:

    ln -ds dest name

The link will be created even if the destination does not exist:

    ln -s idontexist name

If the name is in another dir, the destination is not changed by default:

    mkdir d
    ln -s a d/a
    [ `readlink d/a` = a ] || exit 1

To create relative to `dest`, use `-r`:

    mkdir d
    ln -rs a d/a
    [ `readlink d/a` = ../a ] || exit 1

If the name is in another dir, the destination is not changed by default:

Absolute link:

    ln /full/path/to/dest name
    [ `readlink name` = "/full/path/to/dest" ] || exit 1
