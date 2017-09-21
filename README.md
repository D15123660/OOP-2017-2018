# DT228/DT282 Object Oriented Programming 2017-2018

Resources
---------
* [Webcourses](http://dit.ie/webcourses) - Course code: CMPU2016
* [Processing](http://processing.org)
* [The Processing language reference](http://processing.org/reference/)
* [Learning Processing: A Beginner's Guide to Programming Images, Animation, and Interaction (Morgan Kaufmann Series in Computer Graphics)](http://http://www.learningprocessing.com/)
* [The Nature of Code](http://natureofcode.com/)
* [Eclipse](http://eclipse.org)
* [The git manual - read the first three chapters](http://git-scm.com/documentation)
* [A video tutorial all about git/github](https://www.youtube.com/watch?v=p_PGUltnB6w)
* [The Java Tutorial from Oracle](http://docs.oracle.com/javase/tutorial/)
* [Games Fleadh](http://www.gamesfleadh.ie/)
* [The Imagine Cup](https://www.imaginecup.com/)

## Contact the lecturer
* Email: bryan.duggan@dit.ie
* Twitter: [@skooter500](http://twitter.com/skooter500)

Some assignments from previous years:

[![YouTube](http://img.youtube.com/vi/IJ4TzwCRns8/0.jpg)](https://www.youtube.com/watch?v=IJ4TzwCRns8)

[![YouTube](http://img.youtube.com/vi/tqGtfsXNPng/0.jpg)](https://www.youtube.com/watch?v=tqGtfsXNPng)

[![YouTube](http://img.youtube.com/vi/uykz5mCjV0w/0.jpg)](https://www.youtube.com/watch?v=uykz5mCjV0w)

# Assessments

- [Assignments](assignments.md)

- 14 November 2017 Lab Test 10%
- 12 December 2017 Assignment 1 submission 15%
- 30 January 2018  Lab Test 2 - 10%
- Assignment 3 - 15%
- End of Year MCQ - 50%

# Week 2 - Variables & conditions
- [Variables example](processing/variables)
- [The amanita sketch (the mushroom that moves with the mouse)](processing/amanita)


## Videos
[![YouTube](http://img.youtube.com/vi/B-ycSR3ntik/0.jpg)](https://www.youtube.com/watch?v=B-ycSR3ntik)

[![YouTube](http://img.youtube.com/vi/rZ36BzXFT6Q/0.jpg)](https://www.youtube.com/watch?v=rZ36BzXFT6Q)

[![YouTube](http://img.youtube.com/vi/wsI6N9hfW7E/0.jpg)](https://www.youtube.com/watch?v=wsI6N9hfW7E)

[![YouTube](http://img.youtube.com/vi/mVq7Ms01RjA/0.jpg)](https://www.youtube.com/watch?v=mVq7Ms01RjA)

## Lab 

## Learning Outcomes
- Use what you learned in class to build a complete game system in Processing
- Practice drawing stuff and working out relative co-ordinates
- Practice using variables and compound if statements
- Gain experience thinking computationally
- Learn how to use random numbers
- Learn how to get input from the keyboard
- Learn how to import libraries into Processing

This is a video of a game called Bugzap that you can try and make in Processing today. There is a fair bit to it, so don't worry if you don't manage to complete everything.

[![YouTube](http://img.youtube.com/vi/s6PA8jtWneQ/0.jpg)](https://www.youtube.com/watch?v=s6PA8jtWneQ)

How you should do it:
- Get the main game working first and then if you have time, add fonts, sound, the splash screen and the game over screen.
- Write some code to draw the bug. You can write a method to do this if you like (but it's not essential). Here is [an article on using methods in processing](https://processing.org/examples/functions.html). Also make global variables for the bug position and size.
- Get the bug moving. The bug moves a random amount either to the left or the right and it also moves down the screen. Use the random method in Processing to generate random numbers. Also the bug can't move off the screen. You can use the % operator to make something happen on an interval. For example:

  ```Java
  if (frameCount % 60 == 0)
  {
    // Code in here will happen once per second
  }
  ```
- Write some code to draw the player. Use variables to control the player position and size. A method is good here too!
- Write code to move the player in response to a key presses. This is one way to do keyboard handling in Processing:

```Java
if (keyPressed)
{
  if (keyCode == LEFT)
  {
    // This will happen if the left key is pressed
  }
}
```
- Now add the player lazer. I used to UP key for this. I just drew a line for the lazer.
- Make a variable for score and check for collisions between the lazer and the bug. Add a variable for score. You can print stuff to the screen using the text method in Processing. In my version, I actually used [this processing library](http://www.foobarquarium.de/blog/processing/MovingLetters/) which makes wireframe text.
- Make some sound effects and add them to the game. I used [BFXR](http://www.bfxr.net/) to make the sounds and the Minim library to play them, but you might prefer to use the [built-in audio methods in Processing](https://processing.org/tutorials/sound/).
- Add the splash screen and game over screen

- [Solution](http://github.com/skooter500/BugZap)

## Tutorial
- Clone the repository for the course by typing:
    ```bash
    git clone https://github.com/skooter500/OOP-2017-2018
    ```
- If you already have the course cloned, you can pull the latest changes by cd'ing to the folder where you cloned the course and typing:
	```bash
	git pull
	```
- Open the rick_n_morty.pde sketch. This sketch loads the background image and sound. Complete the sketch so that it does this:

[![YouTube](http://img.youtube.com/vi/BR1p2Dl6ELE/0.jpg)](https://www.youtube.com/watch?v=BR1p2Dl6ELE)
	
# Week 1 - Introduction to Processing and the course

## Lecture
* [Introduction slides](https://1drv.ms/p/s!Ak7y2552PWCrhONjAgskv4PATGqdpw)
* [The contract for this course](https://1drv.ms/w/s!Ak7y2552PWCrjPYXt8HlWl1T1cg5Og)

## Lab

### Learning Outcomes
- Enroll on Webcourses
- Become familiar with the syntax of Processing
- Become familiar with writing and running sketches in Processing
- Clone a git repository!
- Install Processing libraries

### Part 1 - Drawing
- Log onto Webcourses and enroll on the module CMPU2016.
- Check out [the Processing reference](https://processing.org/reference/)
- Check out [Daniel Shiffman's awesome YouTube channel](https://www.youtube.com/user/shiffman)
- Check out [these Sci-Fi user interfaces made by last years OOP students](https://www.youtube.com/playlist?list=PL1n0B6z4e_E5RZYrubD2pcxq0qzGy-3vr)
- Check out [these music visualisers made in Processing by last years game programming students](https://www.youtube.com/watch?v=cW8s5i9dmqA&list=PL1n0B6z4e_E6jErrS0ScSCaVrN7KV729x)
- If you are curious, check out [some of my creature videos](https://www.youtube.com/watch?v=cW8s5i9dmqA&list=PL1n0B6z4e_E6jErrS0ScSCaVrN7KV729x)

- Look up the following methods in the [Processing language reference](http://processing.org/reference/ ) to make sure you are clear about the syntax and parameters:

    * noStroke
    * noFill
    * line
    * ellipse
    * rect
    * background
    * stroke
    * fill
    * size
    * arc
    * triangle

Write a processing sketch to draw the following shapes:

![Sketch](images/p1.png)

![Sketch](images/p1.1.png)

![Sketch](images/p1.2.png)

I prefer to draw the shapes on paper first before I try and work out the coordinates. Try experimenting with different colours! 

### Part 1 - Cloning git repositories

Clone the course website:

- [Install git](https://www.atlassian.com/git/tutorials/install-git) if you need to. It should be installed on the lab computers already
- Start git bash
- Type ```pwd``` to print the current working directory
- Type ```cd ˜``` to cd to your home directory
- Type ```cd Documents``` Also you can start typing the path and then press TAB and bash will autocomplete the command
- You can use the command mkdir to make a directory if you want to make a subdirectory
- Type ```git clone https://github.com/skooter500/OOP-2017-2018``` to clone the course website
- Now navigate to the OOP-2017-2018 folder in windows explorer and have a look at the files that were cloned

Clone NILL, a game I programmed in Processing and get it running:

- Type ```git clone https://github.com/skooter500/NILL``` This will clone the repository
- Find the NILL folder that was created and double click on the file NILL.pde. It should open in Processing
- You need to install the Minim library and the Game control libraries to make NILL work. Go to Sketch | IMport Library | Add library to do this
- See if you can collect all the pods
- Have a look through the source code for NILL and see if you can figure out the following
    - What are the Java datatypes?
    - What classes are in the project?
    - How is the landscape drawn?
    - How does the game keep track of all the objects on screen?

## Tutorial

Clone the repository for NILL and get the game working as described above. Create a new branch by typing:

```git checkout -b tutorial```

Now make the following changes to the game:

- Change the colour of the Ship
- Change the movement speed of the ship
- Change how fast the ship rotates
- Change the force of gravity on the ship
- Increase the amount of fuel the ship starts with
- Make the powerups spawn twice as fast
- Make the game spawn fuel twice as frequently as asteroids
- Change the bumpiness of the terrain
- Add more pods
- Draw the fuel pods as octogons instead of pentagons
- Increase the number of stars in the background
- Change the keys used to control the ship to be A, D and W instead of left, right and up
- Disable collisions between the ship and the terrain

Commit your changes to the new branch by typing:

```bash
git add . -- all
git commit -m "tutorial changes"
```