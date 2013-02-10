ipset-bash-completion
=====================


Description
===========

Programmable completion code for the bash shell to support the ipset program (netfilter.org).


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
- Show and complete hostnames, when adding, deleting or testing elements (using @ as prefix).
- Complete on filenames if the current option requires it.
- Complete variable names, command subtitution and globbing patterns
- Don't complete if an invalid combination of options is used.


Installation
============

Put it into ~/.bash_completion or /etc/bash_completion.d/.


Compatibility
=============

Tested with ipset v6.16.1.
Should support versions from 6.0 upwards.
Compatibility for future ipset versions cannot be promised, as new options may appear, 
which of course are currently unpredictable.

For bash, it should work from at least 3.x upwards.


Availability
============

https://github.com/AllKind/ipset-bash-completion

https://sourceforge.net/projects/ipset-bashcompl/
