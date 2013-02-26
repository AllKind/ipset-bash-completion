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
- Show and complete services, protocols, icmp[6] types and interface names when adding elements.
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

https://http://sourceforge.net/projects/ipset-bashcompl/
