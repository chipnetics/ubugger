# ubugger - A Basic Unicon Debugger
'ubugger' is a unicon/icon debugger which edits *.icn and creates associated *_dbg.icn files. It provides functionality for *Continue* and *Stepping*. However there is currently no functionality for stepping in and out of of procedures.

# Building ubugger
`unicon ubugger.icn`

# Running ubugger
`./ubugger foo.icn bar.icn beef.icn`, would generate `foo_dbg.icn`, `bar_dbg.icn` and `beef_dbg.icn`.
 
Naturally you can chain execution as one command with 
`./ubugger foo.icn bar.icn beef.icn & unicon foo_dbg.icn -x` if you wanted to immediately pass the _dbg.icn to unicon and execute your debug session.

# Setting Breakpoints
Breakpoints can be added in you .icn files by adding `#xxx` as a comment, wherever you want to break.
this allows you to still compile your original .icn in unicon without having to manually edit anything first.

# Contributions
Very welcome, Unicon is in desperate need of some better debugger facilities other than just `trace`.