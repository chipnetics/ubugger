# ubugger - A Basic Unicon Debugger
'ubugger' is a unicon/icon debugger which edits *.icn and creates associated *_dbg.icn files. 

It provides functionality for *Continue* and *Stepping*. However there is currently no functionality for stepping in and out of procedures; nor for watching variables.

It also shows the current line of code being executed with the line number, and state of all the locals/globals.  Long lists/tables are truncated for pretty printing.

# Building ubugger
`unicon ubugger.icn`

# Running ubugger
`./ubugger foo.icn bar.icn beef.icn`, would generate `foo_dbg.icn`, `bar_dbg.icn` and `beef_dbg.icn`.
 
Naturally you can chain execution as one command with 
`./ubugger foo.icn bar.icn beef.icn & unicon foo_dbg.icn -x` if you wanted to immediately pass the _dbg.icn to unicon and execute your debug session.

# Setting Breakpoints
Breakpoints can be added in you .icn files by adding `#xxx` as a comment, wherever you want to break.
This allows you to still compile your original .icn in unicon without having to manually edit anything first.

# Example Output 

```
=====================================================pathgui.icn=====================================================
>> every task := !result_path do put(results_list,[g_tbl_tasks_id[task].task_code,g_tbl_tasks_id[task].task_name])  |
L----58         sel_task_code-------"FO10005"                                                                       |
L----58         rel_task_id---------"94133"                                                                         |
L----58         selected------------8                                                                               |
L----58         local_s-------------&null                                                                           |
L----58         debug_c_s-----------&null                                                                           |
L----58         local_v-------------"local_v"                                                                       |
L----58         debug_c_l-----------&null                                                                           |
L----58         ch------------------"s"                                                                             |
L----58         result_sols---------[]                                                                              |
L----58         results_list--------[["FO10005","DECREASE GENERATOR LOAD TO 100 MW"],<3>["FO10007","DECREASE GEN LOA|
L----58         index---------------1                                                                               |
L----58         result_path---------["94133","94135","94136","94139","94138","94141","94142","94143","94144","94114"|
L----58         task----------------"94218"                                                                         |
[S] Step, [C] Continue
```

# Contributions
Very welcome, Unicon is in desperate need of some better debugger facilities other than just `trace`.