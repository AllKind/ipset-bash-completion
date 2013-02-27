ipset-bash-completion
=====================

Description
===========

Programmable completion specification (compspec) for the bash shell to support the ipset program (netfilter.org).


Programmable completion allows the user, while working in an interactive shell, to retrieve and auto-complete commands,
their options, filenames, etc.
Pressing [TAB] will complete on the current word, if only one match is found.
If multiple completions are possible, they will be listed by hitting [TAB] again.


Features
========

This completion specification follows the logic of ipset and will only show commands and options, 
when they are available for the current context (combination of commands and/or options).
Providing some kind of interactive help.

- Show and complete commands and options.
- Show and complete set names.
- Show and complete the set types when using the create and help command.
- Show and complete set elements (members) when using the del command.
- Show and complete services (also named port ranges), protocols, icmp[6] types and interface names when adding elements.
- Show and complete hostnames, when adding, deleting or testing elements (using @ as prefix).
- Complete on filenames if the current option requires it.
- Complete variable names, command subtitution and globbing patterns.
- Do not complete if an invalid combination of options is used.
- Do not complete if an invalid value of an option argument is detected.


Installation
============

Put it into ~/.bash_completion or /etc/bash_completion.d/.

Tip: To make tab completion more handsome put the following into either /etc/inputrc or ~/.inputrc:

     set show-all-if-ambiguous on

This will allow single tab completion as opposed to requiring a double tab.

     set page-completions off

This turns off the use of the internal pager when returning long completion lists.


Usage
=====

Type -[TAB] to start option completion.
Sets named - (hyphen) or starting with it, are supported, excluded are option names (i.e. -exist).

Type [TAB] to complete on anything available at the current context.

To complete named port ranges, enter the hypen after the first completed service (port) name,
hit [TAB] again to start completion on the second named port (the brackets [] for service names
containing a - (hyphen) are already surrounding the name in the completion list).

Depending on the environment variable _IPSET_OPT_FORMAT, either the long, short or both forms of options are shown for completion.
By default (empty _IPSET_OPT_FORMAT) the long versions of options are displayed (_IPSET_OPT_FORMAT=long also does the same).
Setting it to 'short' will cause completion to show only the short form.
Setting it to any other value, will result in both version being displayed and completed.

When adding elements to one of the following set types:
hash:ip,port hash:ip,port,ip hash:ip,port,net hash:net,port
and completion is attempted on the port specification, the list of possible completions may become quite long.
Especially if no characters are given to match on.
This behaviour is because of the many different values such a port specification can possibly have.


Compatibility
=============

Tested with ipset v6.16.1.

Compatibility for future ipset versions cannot be promised, as new options may appear, 
which of course are currently unpredictable.

Bash 3.x and upwards are supported.

The bash_completion (v2.0+) package is highly recommended, though not mandatory.

http://bash-completion.alioth.debian.org/

Some things might not be that reliable without it.
Also the colon (if there) is removed from COMP_WORDBREAKS.
This alteration is globally, which might affect other completions,
if they do not take care of it themselves.

Availability
============

https://github.com/AllKind/ipset-bash-completion

http://sourceforge.net/projects/ipset-bashcompl/
