# iterator
Self-contained, Python-based general-purpose iterator experiment. 

This script iterates a list of "things" and runs one or more arbitrary system commands on each.

That's pretty mundane, but here's the fun part: It provides an interface to configure it, and stores this configuration inside itself! 
Yeah pretty crazy huh? :)

# Example run

# Demonstration of "iterator.py" sample script
# A self-contained general-purpose "Thing Doer"
# See script source for details.
# Gary Arthur Douglas Jr | unhacker@gmail.com

[garyd@dizzymouse iterator]$ ./iterator typohere
./iterator: Invalid mode Typohere

# iterator: Run a command on a list of things
# Usage:
#   iterator show    - Show config
#   iterator things  - Edit list of things
#   iterator command - Edit command
#   iterator run     - Execute current config
#   iterator help    - You are reading it

[garyd@dizzymouse iterator]$ ./iterator show

Mode	: Show
Command	: /tmp/brawl _THINGS_
Things	: 21 63 20 34 85 

[garyd@dizzymouse iterator]$ ./iterator things

Mode	: Things

Number	Thing
-------	------------
  0 	21
  1 	63
  2 	20
  3 	34
  4 	85

[A]dd, [D]elete, or [S]ave/quit : d
Enter number to delete, or nothing (to cancel): 0
Thing # 0 deleted!

Number	Thing
-------	------------
  0 	63
  1 	20
  2 	34
  3 	85

[A]dd, [D]elete, or [S]ave/quit : d
Enter number to delete, or nothing (to cancel): 3
Thing # 3 deleted!

Number	Thing
-------	------------
  0 	63
  1 	20
  2 	34

[A]dd, [D]elete, or [S]ave/quit : d
Enter number to delete, or nothing (to cancel): 1
Thing # 1 deleted!

Number	Thing
-------	------------
  0 	63
  1 	34

[A]dd, [D]elete, or [S]ave/quit : a

Enter new Thing, or nothing (to cancel):
/tmp/somefile.txt
Thing added.

Number	Thing
-------	------------
  0 	63
  1 	34
  2 	/tmp/somefile.txt

[A]dd, [D]elete, or [S]ave/quit : a

Enter new Thing, or nothing (to cancel):
internalsite.corp.com
Thing added.

Number	Thing
-------	------------
  0 	63
  1 	34
  2 	/tmp/somefile.txt
  3 	internalsite.corp.com

[A]dd, [D]elete, or [S]ave/quit : s
Things updated! Exiting.

[garyd@dizzymouse iterator]$ ./iterator command

Mode	: Command
Command	: /tmp/brawl _THINGS_
Things	: 63 34 /tmp/somefile.txt internalsite.corp.com 

On run, each thing replaces _THINGS_. 
Examples:
  ping -c 1 _THINGS_
  cp _THINGS_ /tmp; ls -l /tmp/_THINGS_

New command: echo "Doing _THINGS_..."

Save? [Y]es, [N]o, or <enter> for next preview.

New command:	echo "Doing _THINGS_..."
Preview:	echo "Doing 63..."		
Preview:	echo "Doing 34..."		
Preview:	echo "Doing /tmp/somefile.txt..."		y

Configuration updated! Exiting.

[garyd@dizzymouse iterator]$ ./iterator show

Mode	: Show
Command	: echo "Doing _THINGS_..."
Things	: 63 34 /tmp/somefile.txt internalsite.corp.com 

[garyd@dizzymouse iterator]$ ./iterator run

Mode	: Run
Command : echo "Doing _THINGS_..."

Doing 63...
Doing 34...
Doing /tmp/somefile.txt...
Doing internalsite.corp.com...

Run complete. Exiting.

[garyd@dizzymouse iterator]$
