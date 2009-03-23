daemontoolsctl
==============

daemontoolsctl is a wrapper around daemontools.

Example Session
---------------

I have svscan running on 3 dummy services in /tmp/procs.

On startup, daemonstoolsctl automatically runs svstat::

    /tmp/procs/app3: up (pid 23269) 23 seconds
    /tmp/procs/program2: up (pid 23234) 44 seconds
    /tmp/procs/program1: up (pid 23226) 48 seconds
    daemontoolsctl> help

    Documented commands (type help <topic>):
    ========================================
    alarm     down    interrupt  once   restart  status  terminate
    continue  hangup  kill       pause  start    stop    up       

    Undocumented commands:
    ======================
    EOF  help

    daemontoolsctl> 

All commands support tab completion and globbing::

    daemontoolsctl> stop program [TAB]
    program1  program2  
    daemontoolsctl> stop program*
    sending stop to program2
    sending stop to program1
    /tmp/procs/program2: down 0 seconds, normally up
    /tmp/procs/program1: down 0 seconds, normally up
    daemontoolsctl> 
