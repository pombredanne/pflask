pflask-debuild(1) -- build Debian packages inside Linux namespace containers
============================================================================

## SYNOPSIS

`pflask-debuild`

## DESCRIPTION

**pflask-debuild** is a wrapper aroung pflask that builds Debian packages
inside a Linux namespace container. It is also able to run `lintian(1)` on the
generated .changes file and sign the resulting package using `debsign(1)`.

## ENVIRONMENT

`DIST`

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
The Debian release (e.g. _"unstable"_). It will be used when searching for the
base Debian install under `/var/cache/pflask`. By default will be read from the
`debian/changelog` of the package to be built.

`ARCH`

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
The Debian architecture (e.g. _"amd64"_). It will be used when searching for
the base Debian install under `/var/cache/pflask`. If none is specified,
`dpkg-architecture(1)` is used.

`DEBUILD_DPKG_BUILDPACKAGE_OPTS`

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
Options that should be passed to `dpkg-buildpackage(1)`.

`DEBUILD_LINTIAN`

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
If set to _"yes"_ (default) `lintian(1)` will be run.

`DEBUILD_LINTIAN_OPTS`

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
Options that should be passed to `lintian(1)` (by default _"-IE --pedantic"_
will be used).

## FILES

`~/.devscripts`

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
User-specific configuration file.

`/etc/devscripts.conf`

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
System-wide configuration file.

## AUTHOR ##

Alessandro Ghedini <alessandro@ghedini.me>

## COPYRIGHT ##

Copyright (C) 2013 Alessandro Ghedini <alessandro@ghedini.me>

This program is released under the 2 clause BSD license.
