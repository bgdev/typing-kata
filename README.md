Requirements Summary
====================

Write a program that assists the user while learning to type at a constant rate. The program should continously measure the typing speed of the user, while rapidly updating the user's actual typing rate.


Initial State
=============

When the program is started, it enters idle mode and waits for commands. 


Printing Help
=============

If the user types "help" or something else that is not valid in this mode, the program prints some help instructions and stays in idle mode. 


Performing a Training Session
=============================

As soon as the user inputs "train DESIRED_TYPING_RATE", the program enters training mode and starts a training session, which lasts for one minute. For example, "train 3" means that the user should type three characters per second at a steady pace.

Then, the program starts measuring the typing rate of the user, while the user is typing an arbitrary text. After two seconds have passed, the program starts to continuously display the user's actual typing rate.

For example, if the target typing rate is 3 keystrokes per second and the user inputs 8 keystrokes during those two seconds of measurement, the average typing rate is 4.0 keystrokes per second, which should be presented to the user as +1.0, hinting that the user is typing too fast.

The program continues to update the user's actual typing rate and updates the display twice per second at a fixed rate. In the same time, the program keeps computing the user's actual typing rate, taking into account the keystrokes from the last two seconds.

The training session is over automatically after one minute of training has passed. When this happens, the program resets the display and enters idle mode again. 


Repeating and Quitting
======================

Now the user can type "quit" in order to quit, or another "go" in order to perform another training session.


Credits
=======

This is a code kata suggested by Anton Georgiev, who stated that it would be a nice interview assignment for software developers. I found the problem to be a good challenge, because contrary to the typical "write one function that computes some stuff" assignment, the solution of this problem requires handling of non-deterministic things. Things like user input and display updates at different rates, management of state, timing and synchronization.