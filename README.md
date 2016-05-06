# GravitySim
My first coding project, just for fun! It's written in Python, and uses the standard Tkinter graphics module. It's an interactive gravitational 3-body simulator, oringinally intended to be a simple calculation of trajectories and demonstration of chaotic systems for a computational physics class.

It uses the Euler-Cromer method to calculate the velocity and position of 3 different bodies based on the forces acting on each body due to the other 2 bodies. The Euler-Cromer method conserves the total momentum of the system regardless of how large the timestep is, it's also not very computationally expensive (looking at you, Runge-Kutta) and thus it's a great choice for a program that must calculate the trajectories in real time, on the fly.

# Instructions
Left-click on a circle and drag it to where ever you'd like. Right click and drag to set the velocity. Enter desired mass in the upper right text box. Click start to view the trajectories, stop to pause, and reset to return to default. The speed up and slow down buttons control viewing speed. 

## Screenshot

![screenshot](https://cloud.githubusercontent.com/assets/18639528/14873539/75ba35c0-0cbd-11e6-85a2-75c36d3a1668.png)

# Program flow
- Tests speed of user's cpu with speedtest(), which sets the global variable 'refreshscale' to give 120 Hz display
- speedtest() finishes, then triggers car(), which is the interactivity environment without gravity turned on
- car() runs until start button is clicked, which triggers gameon() 
- gameon() triggers Euler-Cromer calculations and runs until stop button is clicked

- updatescreen() draws the bodies to the screen based on where the physics calculations say they should be. Runs at 120 Hz.
