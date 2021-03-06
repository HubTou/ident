# Installation
pip install [pnu-ident](https://pypi.org/project/pnu-ident/)

# IDENT(1)

## NAME
ident — identify RCS keyword strings in files

## SYNOPSIS
**ident**
\[-q\]
\[--debug\]
\[--help|-?\]
\[-V|--version\]
\[--\]
\[file ...\]

## DESCRIPTION
The **ident** utility searches for all instances of the pattern ‘$keyword: text $’ in *file*(s).

*keyword* must only be composed of alphanumeric values in the C locale, followed by ‘:’ and a space.

If no arguments are passed, then **ident** parses the standard input.

The pattern normally requires a colon and a space immediately after the keyword and a space immediately before the terminating $,
but for [Subversion](https://en.wikipedia.org/wiki/Apache_Subversion) 1.2 (and later) compatibility, **ident** will also recognize the pattern ‘$keyword:: text $’ (i.e., two colons and a space)
and the pattern ‘$keyword:: text #$’ (likewise, with a hash before the terminating $).
These are the fixed-width keyword syntax.

To summarize, the three recognized patterns are:
* $keyword: text $
* $keyword:: text $
* $keyword:: text #$

### OPTIONS
These options are supported:

Options | Use
------- | ---
-q|Quiet mode: suppress warnings if no pattern found
--debug|Enable debug mode
--help\|-?|Print usage and a short help message and exit
-V\|--version|Print version and exit
--|Options processing terminator

## ENVIRONMENT
The *IDENT_DEBUG* environment variable can be set to any value to enable debug mode.

The *FLAVOUR* or *IDENT_FLAVOUR* environment variables can be set to one of the following values, to implement only the corresponding options and behaviours.
* bsd | bsd:freebsd : FreeBSD [ident(1)](https://www.freebsd.org/cgi/man.cgi?query=ident)
* gnu | gnu:linux | linux : GNU/Linux [ident(1)](https://man.cx/ident(1))

## EXIT STATUS
The **ident** utility exits 0 on success, and >0 if an error occurs.

## SEE ALSO
[what(1)](https://github.com/HubTou/what/blob/main/README.md),
[strings(1)](https://github.com/HubTou/strings/blob/main/STRINGS.1.md)

## STANDARDS
The **ident** utility is not a standard UNIX command, though a usual one on Unix-like systems.

This re-implementation tries to follow the [PEP 8](https://www.python.org/dev/peps/pep-0008/) style guide for [Python](https://www.python.org/) code.

## PORTABILITY
Tested OK under Windows.

## HISTORY
The **ident** command appeared with the [Revision Control System (RCS)](https://en.wikipedia.org/wiki/Revision_Control_System) in 1982,
and was written by [Walter F. Tichy](https://en.wikipedia.org/wiki/Walter_F._Tichy) at [Purdue University](https://en.wikipedia.org/wiki/Purdue_University).
[RCS](http://www.gnu.org/software/rcs/manual/rcs.html#ident) is now maintained by the [GNU Project](https://en.wikipedia.org/wiki/GNU_Project).

This re-implementation was made for the [PNU project](https://github.com/HubTou/PNU).

## LICENSE
It is available under the [3-clause BSD license](https://opensource.org/licenses/BSD-3-Clause).

## AUTHORS
[Hubert Tournier](https://github.com/HubTou)

This manual page is based on the one written for [FreeBSD](https://www.freebsd.org/) by Baptiste Daroussin <bapt@FreeBSD.org>.

## CAVEATS
In the original RCS ident command, option *-V* printed RCS version number.
Our re-implementation prints its own version.

