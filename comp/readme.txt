`comp
    Text based simulator based on liblc3.

commands

Execution
---------
run - Runs until it halts
step [x=1] - If x is given runs for that many instructions else steps 1 instruction
back [x=1] - If x is given back steps for that many instructions else backsteps 1 instruction
next [x=1] - If x is given steps x lines (not stepping into any subroutines / traps) else steps 1 line
prev [x=1] - If x is given goes back x lines (not stepping into any subroutines / traps) else back steps 1 line
finish - Steps out of the current subroutine.
rewind - Backsteps until undo stack empty

Debugging
---------
tempbreak addr - Puts a temporary breakpoint at addr (this is equivalent to break addr, name, 1, 1)
break addr[, cond[, times[, name]]] - Puts breakpoint at addr with condition cond, times number of hits before becoming inactive, and name name
watch target, condition[, times[, name]] - Sets a watchpoint on target with condition cond, times number of hits before becoming inactive, and name name
blackbox addr[, name[, condition]] - Marks addr as a blackbox.
undostack num - Sets the undo stack length
callstack num - Sets the call stack length
delete name/addr - Deletes the breakpoint/watchpoint/blackbox with name or address

Manipulation
set thing value - Sets register/cc/pc/address to value
fillmem value - Fills entire lc3 memory with value
input fname/cin - Sets source for console input
output fname/cout - Sets source for console output
reset - Resets the lc3 state
randomize - Randomizes the lc3 state
truetraps bool - Toggles true_traps if no param given else true sets true_traps false unsets true_traps
interrupt bool - Toggles interrupts if no param given else true sets interrupts false unsets interrupts

Display
-------
list addr[, level=1] - Displays memory addresses starting from start. If level is given affects the disassemble level (basic=0, normal=1, highlevel=2)

File
----
load filename - Reinitializes and loads filename.
reload - Reinitializes and Reloads last file if there was a file already loaded
loadover filename - Loads filename over current state
reloadover - Reloads last filename over current state
quit - quits the program


Other stuff
-----------
multiple commands may be given in a single line separated by semicolons i.e. this is valid
set R0 14; set R1 19; set CC 0

If no command is given execute the last command given.
If up is pressed then it should go through commands history



Roadmap
-----
The following features from complx
Hide Addresses?
Flip Memory?
Instruction Highlight toggling.
Show Console Output
Call Stack?

Another command to repeat the previous command.
repeat num should repeat the last command num times
