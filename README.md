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
- 14 February 2018 Lab Test 2 - 10%
- 5 February 2018 Team project proposal submission
- 25 April 2018 - Team project demos - 15%
- End of Year exam - 50%

[Semester 2 Assignment Choice form](https://docs.google.com/forms/d/e/1FAIpQLSdf9Lfr2_vPN1I10efd-Jhe5kP4lg_PU0v6rVNBKDuBWBgeow/viewform)

# Week 5 - Exceptions
- [Exceptions](https://docs.oracle.com/javase/tutorial/essential/exceptions/summary.html)
- [Solution to the lab test](https://github.com/skooter500/OOP-2018-Lab-Test-2)

# Week 4 - File IO
- [File IO in Java tutorial](https://docs.oracle.com/javase/tutorial/essential/io/)
- [Javadocs](https://docs.oracle.com/javase/9/docs/api/overview-summary.html#JavaSE)
- [Big file of English words](https://github.com/dwyl/english-words/blob/master/words.txt)
- Clone the repo to get the code we worked on

## Lab Test

### Object Oriented Programming Lab Test 2 2018

For todays' lab test, you will be writing a parser for ABC music files in Java. ABC music files are plain text ascii files that store sheet music notation. ABC music files can contain the notation for multiple tunes in one file and tunes are seperated by one or more blank lines. The file you will be parsing today has 100 tunes in it. Each tune consists of headers which are the letters X, T, R etc followed by a :. The actual music notes follow the headers. The X header is called the index number of the tune and is always an integer. The T header is the tune title. Tunes always begins with an X header and there is always at least one title, though there can be optionally multiple T headers as tunes can have multiple titles. There are other headers, but we are only interested in the tites and the index numbers for the purpose of this test.

Here is an extract from the file you will be parsing today that shows the ABC notation for two tunes:

```
X:3
T:Banish Misfortune
R:jig
H:First bar also played |^fed cAG|
D:Tommy Keane & Jacqueline McCarthy: The Wind among the Reeds
D:Chieftains Live.
Z:id:hn-jig-3
M:6/8
K:Dmix
fed cAG | AGd cAG | ~F3 DED | ~F3 GFG |
~A3 cAG | AGA cde | fed cAG | Ad^c d2e :|
|: f2d d^cd | f2a agf | e2c cBc | ece gfe |
f2g agf | e2f gfe | fed cAG | Ad^c d2e :|
|: f2g e2f | ded cdc | ~A3 GAG | ~F3 ded |
c3 cAG | AGA cde | fed cAG | Ad^c d2e :|
P:variations
|: =fed cAG | A2d cAG | F2D DED | FEF ~G3 |
AGA cAG | ~A3 cde | fed cAG | Ad^c d2e :|
|: f2d d^cd | f2g agf | e2c cBc | e2f gfe |
f2g agf | e2f gfe | fed cAG | Ad^c d2e :|
|: f2g e2f | d2e c2d | ABA GAG | F2d ded |
c3 cAG | AGA cde | fed cAG | Ad^c d2e :|

X:4
T:Piper's Chair, The
T:Cathaoir an Ph\'iob\'aire
R:jig
D:Bobby Gardiner: His Master's Choice.
Z:id:hn-jig-4
M:6/8
K:G
DGG GFD|c2c cAc|ded cAG|FAG FEF|DGG GFD|c2c cAc|ded cAF|1 AGF G3:|2 AGF GBd||
|:~g3 agf|d2g gfg|GFG =fef|A2B cBA|GBd g2f|d2e fdc|Bdd cAF|1 AGF GBd:|2 AGF G3||

```
If we take the second tune, "the Pipers Chair" as an example, we can see that tune has an index number of 4 (X:4) and has two titles "Piper's Chair, The" (T:Piper's Chair, The) and "Cathaoir an Ph\'iob\'aire" (T:Cathaoir an Ph\'iob\'aire). 

Instructions:

- Create a new Java git repository on github and call it JavaTest. Make sure you specify Java as the language on github so you get a Java .gitignore file
- Clone the repository to your computer
- Create the folder structure for a java package in the project you cloned, called ```ie.dit``` and download [this abc file](https://raw.githubusercontent.com/skooter500/OOP-2017-2018/master/java/hnj0.abc) to the root of the folder structure you created.
- Create a class called ```Tune``` in the package ie.dit with private fields for ```x```, ```title```, ```altTitle``` and ```notation```. ```x``` should be of type ```int```, ```title```, ```altTitle``` and ```notation``` should be ```String```s. Create public accessor methods for these private fields.
- Write a ```toString``` method on the ```Tune``` class. This should return the fields formatted as "x, title, altTitle". If the tune does not have an ```altTitle```, then you should leave this part out. For example, the above tunes would be printed as:

```
    3, Banish Misfortune
    4, Piper's Chair, The, Cathaoir an Ph\'iob\'aire
```
- Write a class called ```TuneBook``` that has a field called ```tunes``` of type ```ArrayList``` of ```Tune``` objects. To use an ```ArrayList```, you should type ```import java.util.ArrayList;``` at the top of your Java file.
- Write a constructor for the ```TuneBook``` class that takes a single ```String``` as a parameter representing the name of the abc file to load. Write the code in this constructor that loads the file line by line and populates the tunes ```ArrayList``` from the contents of the ABC file. There should be one ```Tune``` object in the ```ArrayList``` for each tune in the file and you should set the ```x```, ```title```, ```altTitle``` and ```notation``` fields on each ```Tune``` object from the file. You can use the accessor methods for this. ```title``` should be set from the first T header in each tune and the ```altTitle``` field should be set from the second T header if one exists. If a tune has only one T header, then the ```altTitle``` field of the tune should be null. If there are more than two titles for a tune (more than two T headers), then you can ignore the third and subsequent titles. ```notation``` should contain the full tune including the headers and the music notes.

    Here is some example code that loads and prints a text file you can use to get started writing this method. Also fee free to have a look at the code from Monday's class

    ```Java
    BufferedReader inputStream = null;
    try {
        inputStream = new BufferedReader(new FileReader("words.txt"));
        
        String l;
        while ((l = inputStream.readLine()) != null) 
        {
            System.out.println(l);
        }
    }
    catch (IOException e)
    {
        e.printStackTrace();
    } 
    finally 
    {
        if (inputStream != null) {
            try
            {
                inputStream.close();
            }
            catch(Exception e)
            {
                e.printStackTrace();
            }
        }
    }    
    ```
- Write a ```toString``` method on the ```TuneBook``` class that returns a ```String``` version of the tunes ```ArrayList```, with each element of the ```ArrayList``` on a seperate line in the returned ```String```.
- Write a method ```public Tune findTune(String title)``` on the ```TuneBook``` class that returns the first matching ```Tune``` from the ArrayList that contains the parameter ```title``` in the  title of the tune.
- Create an ```interface``` called ```Player``` that has one method called ```void play()```
- Implement the interface on the ```Tune``` class. The play method should just print the notation for the tune to the console.
- Put a ```main``` method on the ```TuneBook``` class that has the following code on it to test your solution. It's best to test your code as you go along and don't wait until you have all the parts completed before compiling and running your code.

```Java
    public static void main(String[] args)
    {
        TuneBook tb = new TuneBook("hnj0.abc");
        System.out.println(tb);

        Tune t = tb.findTune("Scotsman over the Border");
        t.play();
    }
```

Below is sample of what your program should output:

```
1, Bride's Favourite, The
2, Irish Washerwoman, The
3, Banish Misfortune
4, Piper's Chair, The, Cathaoir an Ph\'iob\'aire
5, Scotsman over the Border, The
... 
(lines omitted)
...
97, O'Broin's Flightcase
98, Wheels of the World, The
99, Peter O'Byrne's Fancy, Peter Byrne's Fancy
100, Humours of Drinagh, The

X:5
T:Scotsman over the Border, The
R:jig
H:Related to The Carraroe Jig, #181
D:Music at Matt Molloy's.
D:Noel Hill & Tony Linnane.
D:Molloy, Peoples, Brady.
Z:id:hn-jig-5
M:6/8
K:D
DED FDF | AFA d2A | ~B3 BAB | dgf edB |
ADD FDF | AFA d2A | ~B3 AFA | dAF ~E3 :|
|: dfa afa | bag fef | dfa afe | def edB |
dfa afa | bag fed | B2B AFA | dAF ~E3 :|
P:variations
|: ~D3 FDF | AFA d2A | ~B3 BAB | def edB |
ADD ~F3 | AFA d2A | BdB AFA |1 dAF EFE :|2 dAF EFA ||
|: dfa afa | bag fge | dfa afe | def edB |
dfa af/g/a | bag fge | d2B AFA |1 dAF EFA :|2 dAF EFE ||
```
Commit your code whenever you get something completed. [Submit the URL to your git repository here](https://docs.google.com/forms/d/e/1FAIpQLSdOQy53BL3zvBzlY7pSxzWRqOb-J4NatLuOnEzHkFjeHZAi_Q/viewform).

## Marking Scheme

| Description | Marks |
|-------------|-------|
| Writing the ```Tune``` class, with private fields & public accessors | 15 marks |
| ```toString``` method on the ```Tune``` class | 10 marks |
| ```TuneBook``` class with an ```ArrayList``` of Tune objects | 10 marks |
| Loading tunes into the ```ArrayList``` | 25 marks |
| ```toString``` method on the TuneBook | 10 marks |
| Writing the ```findTune``` method | 10 marks |
| Writing and implementing the interface | 10 marks |
| Correct use of git | 10 marks |


# Week 3 - Matrices & the Levenshtein Distance algorithm

- [All about the Levenshtein Distance from my PhD thesis. This might be a bit complicated to read](https://github.com/skooter500/DT228-OOP-2015/blob/master/docs/EditDistance.pdf)
- A lecture I gave about the Levenshtein Distance algorithm from a few years ago:

  [![YouTube](http://img.youtube.com/vi/9-8Uj97J85c/0.jpg)](https://www.youtube.com/watch?v=9-8Uj97J85c)

## Tutorial 
- [Transformation matrices from the Khan Academy (this tutorial)](https://www.khanacademy.org/math/precalculus/precalc-matrices/matrices-as-transformations/v/transforming-position-vector)
- [Rotation matrices](https://en.wikipedia.org/wiki/Rotation_matrix)

## Lab
### Learning Outcomes
- Have fun implementing the Levenshtein Distance. Its a cool algorithm when you get it to work :-)
- See what matrices are used for
- Build a component of a music information retrieval system

Today lets implement the Levenstein Distance algorithm (also known as the Edit Distance) in Java. Of course you can Google this and you will find lots of solutions online in 5 seconds. But don't do this. Instead, try and implement it from your memory and your notes from the class on Monday. If you weren't here then try asking one of your classmates to explain it to you instead of Googling the solution, or watch the video I put up.

Here is how I suggest you do it:

- Take the Matrix Java project we were working and use it as starter code. You can clone the repo to get it. 
- Create a new branch for this weeks work:

```
cd OOP-2017-2018
git checkout -b lab3
```
- Create a new class called EditDistance.java in the same package as the other classes.
- Create a *static* method on the class called min3 that takes three float parameters and returns the minimum of these three numbers
- Create a *static* method on the class called MinimumEditDistance that takes two String parameters, needle and haystack that evaluates the minimum edit distance between needle and haystack. Implement the Levenstein Distance algorithm to calculate this. You should probably print out the matrix by calling the toString method to verify that it is set up correctly
- In the Main class, add this code:

```Java
String sa = "I love DIT";
String sb = "I love Tunepal";
System.out.println("Edit distance between: " + sa + " and: " + sb + " is " + EditDistance.MinimumEditDistance(sa, sb));

sa = "Games Fleadh";
sb = "Imagine Cup";
System.out.println("Edit distance between: " + sa + " and: " + sb + " is " + EditDistance.MinimumEditDistance(sa, sb));
```
- It should print the following:

```
$ java ie.dit.Main
0.0 1.0 2.0 3.0 4.0 5.0 6.0 7.0 8.0 9.0 10.0 11.0 12.0 13.0 14.0
1.0 0.0 1.0 2.0 3.0 4.0 5.0 6.0 7.0 8.0 9.0 10.0 11.0 12.0 13.0
2.0 1.0 0.0 1.0 2.0 3.0 4.0 5.0 6.0 7.0 8.0 9.0 10.0 11.0 12.0
3.0 2.0 1.0 0.0 1.0 2.0 3.0 4.0 5.0 6.0 7.0 8.0 9.0 10.0 11.0
4.0 3.0 2.0 1.0 0.0 1.0 2.0 3.0 4.0 5.0 6.0 7.0 8.0 9.0 10.0
5.0 4.0 3.0 2.0 1.0 0.0 1.0 2.0 3.0 4.0 5.0 6.0 7.0 8.0 9.0
6.0 5.0 4.0 3.0 2.0 1.0 0.0 1.0 2.0 3.0 4.0 5.0 6.0 7.0 8.0
7.0 6.0 5.0 4.0 3.0 2.0 1.0 0.0 1.0 2.0 3.0 4.0 5.0 6.0 7.0
8.0 7.0 6.0 5.0 4.0 3.0 2.0 1.0 1.0 3.0 3.0 5.0 5.0 7.0 7.0
9.0 8.0 7.0 6.0 5.0 4.0 3.0 2.0 2.0 2.0 3.0 6.0 6.0 6.0 7.0
10.0 9.0 8.0 7.0 6.0 5.0 4.0 3.0 2.0 3.0 3.0 7.0 7.0 7.0 7.0

Edit distance between: I love DIT and: I love Tunepal is 7.0
0.0 1.0 2.0 3.0 4.0 5.0 6.0 7.0 8.0 9.0 10.0 11.0
1.0 1.0 3.0 3.0 5.0 5.0 7.0 7.0 9.0 9.0 11.0 11.0
2.0 2.0 2.0 3.0 6.0 6.0 6.0 7.0 10.0 10.0 10.0 11.0
3.0 3.0 2.0 4.0 4.0 5.0 6.0 8.0 8.0 9.0 10.0 12.0
4.0 4.0 3.0 3.0 4.0 6.0 6.0 6.0 7.0 8.0 9.0 10.0
5.0 5.0 4.0 4.0 4.0 7.0 7.0 7.0 7.0 9.0 9.0 11.0
6.0 6.0 5.0 5.0 5.0 5.0 6.0 7.0 7.0 10.0 10.0 10.0
7.0 7.0 6.0 6.0 6.0 6.0 6.0 8.0 8.0 8.0 9.0 10.0
8.0 8.0 7.0 7.0 7.0 7.0 7.0 7.0 8.0 9.0 9.0 11.0
9.0 9.0 8.0 8.0 8.0 8.0 8.0 7.0 9.0 9.0 10.0 10.0
10.0 10.0 9.0 8.0 9.0 9.0 9.0 8.0 8.0 9.0 11.0 11.0
11.0 11.0 10.0 9.0 9.0 10.0 10.0 9.0 9.0 9.0 12.0 12.0
12.0 12.0 11.0 10.0 10.0 10.0 11.0 10.0 10.0 10.0 10.0 11.0

Edit distance between: Games Fleadh and: Imagine Cup is 11.0
```

# Week 2 - Unity
- [Unity Tutorials](https://unity3d.com/learn/tutorials)
- [Download a build of Infinite Forms](https://drive.google.com/file/d/1DOJVwyTltAHjw1dvaYhV8KLuGU-Lqu79/view?usp=sharing)
- [The Unity project we worked on in the class, with some extra stuff](Unity/UnityIdioms)

Important Unity stuff to know (there are great tutorials online for all this stuff):

- The Unity editor
- Using Unity with Visual Studio
- GameObjects, GameComponents
- Vector3, Quaternions
- Transforms & parenting
- Exposing c# properties to Unity
- Start & Update methods
- Using tags
- Using the input manager
- Instianting GameObjects from prefabs
- Colliders & triggers
- Rigidbodies, forces & torque

[This Unity project](Unity/UnityIdioms) has examples of all of these.

## Lab
## Learning Outcomes
- Learn how the most popular game engine in the world uses OO principles in the design of it's classes
- Make a simple tank game in Unity
- Use Visual Studio

Clone the repo for the course and create a branch for your work today
```
git clone https://github.com/skooter500/OOP-2017-2018
cd OOP-2017-2018
git checkout -b lab2
```

Launch Unity and open the project that's part of the course repository in the folder OOP-2017-2018/Unity/UnityIdioms. There are three scenes in this project. You can switch scene in Unity by going File | Open Scene and navigating to the Assets folder that's part of the project hierarchy.

scene1 is the player controlled tank with the 3rd person camera. This scene will also spawn enemy tanks that the player can shoot at.

sceen2 is the player controlled tank with a physicsSpawner object that has a script attached that makes a wall that the player tank can crash into or shoot at.

You can open the Visual Studio project associated with the Unity project by going to the Assets | Open C# Project and it will open Visual Studio so you can edit your code. Take a good read through the C# code associated with this project and make sure and open each scene and run it to see what it does.

You should open scene3 which just has a player controlled tank and a fixed camera. You control the tank by using wasd and space to shoot.

The aim of today's lab is to create a second player controlled tank, controlled with the ijkl and enter keys for shooting. You can make it a different colour to the first player controlled tank and have it shoot differently coloured bullets. Try and get each tank to explode when it gets hit by the opponents bullets. You can have a look at the code in EnemyTanik.cs to se how I achieved the explosion. 

# Semester 2

# Week 1 - Java
- Study [this project](processing/YASC1) for examples of encapsulation, inheritance, polymorphism, interfaces and abstract classes
- [The Java Tutorial](https://docs.oracle.com/javase/tutorial/)
- Compiling and running your first Java program:
	
	[![YouTube](http://img.youtube.com/vi/WXftKFCtPrQ/0.jpg)](https://www.youtube.com/watch?v=WXftKFCtPrQ)
- The [Matrix code](java/) we wrote in the class
- [GamesFleadh](http://gamesfleadh.ie)

# Lab
## Learning Outcomes
- Get practice writing and calling a static method on a class
- Develop your computational thinking skills by implementing methods to do matrix addition and multiplication

Today we will be adding methods to the Matrix class to allow matrix addition, and (optionally) multiplication. 

Clone the repository for the course by starting a bash shell and cd'ing to where you want to work and typing:

```
git clone https://github.com/skooter500/OOP-2017-2018
```

Create a branch for your work today:

```
cd OOP-2017-2018
git checkout -b lab1
```

Compile the code we wrote on Monday:

```
cd java
javac ie/dit/*.java
```

Run the code by typing:

```
java ie.dit.Main
```

Open the file Matrix.java in Notepad++

This class has two methods signatures for matrix addition that allows us to perform the following operations:

- A+= B - This is the *non-static* method add that takes one parameter
- A = B + C - This is the *static* method that takes two parameters.

Read [this article on static in Java](http://stackoverflow.com/questions/413898/what-does-the-static-keyword-do-in-a-class) if you missed the class.

- Write the implementation for a non-static method add(Matrix b) that adds the b parameter matrix to the *current* matrix.
- Write the implementation for static method add(Matrix a, Matrix b) that adds the a and b matrices together and returns a *new* matrix. It currently returns null. Replace this!
- Put the following test code into your Main method:

```Java
Matrix a = new Matrix(4, 4);
a.identity();
a.setElement(2, 3, 7);
a.setElement(3, 1, 2);
a.setElement(3, 0, 4);

Matrix b = new Matrix(4, 4);
b.identity();
b.setElement(2, 3, 1);
b.setElement(3, 1, 9);
b.setElement(3, 0, -7);

a.add(b); // Add b to a. This is like a+= b;

Matrix c;
// Add b to a, without changing a. Instead create a new matrix and return it
// This is like c = a + b
c = Matrix.add(a, b); // How to call a static method

System.out.println(a);
System.out.println(b);
System.out.println(c);	
```

Your program should output the following:

```
2.0     0.0     0.0     0.0
0.0     2.0     0.0     0.0
0.0     0.0     2.0     8.0
-3.0    11.0    0.0     2.0

1.0     0.0     0.0     0.0
0.0     1.0     0.0     0.0
0.0     0.0     1.0     1.0
-7.0    9.0     0.0     1.0

3.0     0.0     0.0     0.0
0.0     3.0     0.0     0.0
0.0     0.0     3.0     9.0
-10.0   20.0    0.0     3.0
```

## Advanced!

Read all about [matrix multiplication](http://www.mathsisfun.com/algebra/matrix-multiplying.html) and implement the static and non-static methods for multiplying two matrices together.

You can add this code to the end of the main method:

```Java
a.mult(b);
c = Matrix.mult(a, b);
System.out.println(a);
System.out.println(b);
System.out.println(c);	
```

And now your program should print:

```
2.0     0.0     0.0     0.0
0.0     2.0     0.0     0.0
0.0     0.0     2.0     8.0
-3.0    11.0    0.0     2.0

1.0     0.0     0.0     0.0
0.0     1.0     0.0     0.0
0.0     0.0     1.0     1.0
-7.0    9.0     0.0     1.0

3.0     0.0     0.0     0.0
0.0     3.0     0.0     0.0
0.0     0.0     3.0     9.0
-10.0   20.0    0.0     3.0

2.0     0.0     0.0     0.0
0.0     2.0     0.0     0.0
-56.0   72.0    2.0     10.0
-17.0   29.0    0.0     2.0

1.0     0.0     0.0     0.0
0.0     1.0     0.0     0.0
0.0     0.0     1.0     1.0
-7.0    9.0     0.0     1.0

2.0     0.0     0.0     0.0
0.0     2.0     0.0     0.0
-126.0  162.0   2.0     12.0
-31.0   47.0    0.0     2.0
```

You can commit your changes by typing:

```
git add .
git commit -m "My changes"
```
	
# Semester 1	

# Week 12 - Interfaces
- We made a Powerup interface and made an AmmoPowerup and a HealthPowerup implementation
- [Updated YASC code](processing/YASC1)
- [Interfaces in Processing](https://processing.org/reference/implements.html)

## Lab

Today you should check out the code we worked on in the class and you can make the following additions:

- Make the keys used to control the player ships fields in the Player class and construct two instances that use different keys so that two players can play at the same time
- Make the the powerups spawn offscreen and move onscreen. Currently they spawn at random positions
- Remove the powerups when they go off screen
- Make it possible for the bullets to collide with the player ships. A bullet collision should remove 1 health. You can do this by modifying the update method in the Player class
- When the players health gets to 0, the other player should win the game.
- You can make the bullets wrap around the screen and get removed after 5 seconds rather than get removed when they go offscreen

# Week 11 - Refactoring YASC to use inheritance, polymorphism and abstract classes
- [Updated YASC code](processing/YASC1)

[![YouTube](http://img.youtube.com/vi/Yd1yHosYkhY/0.jpg)](https://www.youtube.com/watch?v=Yd1yHosYkhY)

## Lab
### Learning Outcomes
- Learn how to use PVectors
- Learn how to implement realistic physics by implementing Newton's Laws of Motion

Modify the code we worked on on the class on Monday so that the ship moves with realistic physics. You should use PVectors in your solution. The three equations you need to implement are:

A = F / m

V = V + A * t

P = P + V * t

Where A = Acceleration, V = Velocity, P = Position, t = time

Force is measured in Newtons and is a vector quantity, so it has magnitude and direction. When you press the w and s keys, instead of moving the position vector, you should create force vector in the direction of the forward vector. To do this, take the forward vector and multiply by the newtons of force you want to apply. I used 100 Newtons of force in my solution.


After you generate the force you need to write code to implement the 3 equations above.
- Calculate the acceleration due to the force
- Calculate the new velocity
- Update the position based on the velocity and time.

I added the following fields to the Player class to do this:

- force, power, timeDelta, velocity and acceleration

If you implement this correctly, your ship will accelerate and move realistically. If you want to implement friction, so that the ship slows down, a simple way to do this is to just multiply the velocity by 0.99f each frame. This removes 1% of the velocity. Here is what my sketch looks like:

[![YouTube](http://img.youtube.com/vi/grz4niYV_bs/0.jpg)](https://www.youtube.com/watch?v=grz4niYV_bs)

Some ideas to try:
- Make the keys used to control the ship fields in the Player class, so you can instantiate several ships controlled with different keys
- Have the player ship draw a trail
- Implement gravity

## Tutorial
- We made a path following player ship

# Week 10 - Adding bullets to YASC

## Lab
- [Lab Test 1](https://github.com/skooter500/OOP_Labtest1_2017_Starter)

# Week 9 - Introduction to YASC
- [YASC Code](https://github.com/skooter500/YASC)
- [Download a build of YASC for Windows on Itch](https://skooter500.itch.io/yasc)
- [Inheritance](https://processing.org/examples/inheritance.html)

[![YouTube](http://img.youtube.com/vi/YjURgEJPbH4/0.jpg)](https://www.youtube.com/watch?v=YjURgEJPbH4)

[![YouTube](http://img.youtube.com/vi/Yd1yHosYkhY/0.jpg)](https://www.youtube.com/watch?v=Yd1yHosYkhY)



# Week 8 - Polymorphism
- [Dog, Cats & Sheep example](processing/DogsCats1)

# Week 7 - git
- All about git

[![YouTube](http://img.youtube.com/vi/p_PGUltnB6w/0.jpg)](https://www.youtube.com/watch?v=p_PGUltnB6w)

# Lab
### Learning Outcomes
- Learn how to use the main features of git via the git bash shell

This lab is all about practicing using git and github. This will work best if you for a group of 2, so that you can get experience collaborating with someone on a project through git. Firstly, make sure you know what the following bash commands do. Fire up the bash shell and try them out. There are lots more, but these are the most common ones I use. Google them and try them out!

```
pwd
ls
ls -a
cd
mkdir
mv
find
grep
```

Note, folders in the bash shell are seperated using / and in Windows explorer you should have the following options checked:

- Show file name extensions
- Hidden files

You will find these options on the View tab of any Windows Explorer window

Also from the bash shell, you can use TAB to complete commands.

Setting up git
- I recommend you install [git for Windows](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) rather than the github client. You can optionally install [SourceTree](https://www.sourcetreeapp.com/) which is a nice git gui program that allows you to *diff* commits (view the changes) amongst lots of other cool stuff.
- The first time you try and do a commit or a push you may have to run come commands to set up your email address and username. Just follow the instructions to do this.
- At some stage you should read the [first 3 chapters of the git manual](https://git-scm.com/documentation). This is pretty much all you need to know.

Note! Select the text using your mouse in the bash shell window and it will get copied to the clipboard. Press Ctrl + Ins to paste.

Basic stuff
- Create a project in Processing and save it somewhere
- Fire up the bash shell and use cd to navigate to the project folder
- Type ```git init``` in the project folder to create an empty git repo. Notice that a new hidden folder called .git will appear in the folder
- Create the project on your github account on github.com. Dont forget to create a .gitignore and a readme.
- Get the url of the new repo and type:
  - ```git remote add origin THE_URL_OF_YOUR_REPO```
- Type ```git pull origin master``` to get the changes from the server. Type ```la -a``` and you should see the new files listed.
- Type ```git add .``` to add your local changes to the staging area
- Type ```git commit -m "some message"``` to make a commit
- Type ```git push --set-upstream origin master``` This creates the connection between your master branch and the master branch on the server
- Type ```git push``` to send your changes to the server

Rolling back to a previous commit
- Make a few more commits and push them
- Type ```git log``` to see the history of your branch and see the 40 digit hexedecimal id's of your commits. It should look something like this

  ```
  commit 7ccd905733dc710ecf38b0431d1143528b5dc1c7
  Author: skooter500 <skooter500@gmail.com>
  Date:   Thu Apr 14 10:03:17 2016 +0100

      Added todays lab

  commit 4b46bea9d2ccd434076310049a5553ccc241adc6
  Author: Bryan Duggan <skooter500@gmail.com>
  Date:   Fri Mar 25 12:55:44 2016 +0000

      classes and bullets example

  commit 6e949c599f038209c9b22da99d5b014a7c47387a
  Author: Bryan Duggan <skooter500@gmail.com>
  Date:   Thu Mar 3 09:15:18 2016 +0000

      broken link

  ```


- Copy one of the 40 digit ids and type ```git checkout THE-40-DIGIT-ID``` Open up your sketch and you should see it has reverted to the old version.
- Type ```git checkout master``` and the head pointer will move to the head of the branch (the latest commit). Open up your sketch and you should see it has changed to the latest version

Rolling back to a previous commit and making a new branch
- If you want to go back to an old version of a project and make changes, you will often see articles on stack overflow etc saying that you should hard reset the head. I recommend that you don't do this as this will delete the subsequent commits on the branch and you might want to get these changes back sometime. Instead, the best thing to do is make the changes on a new branch.
- Checkout one of the old commits again. Make some changes to the sketch
- Type ```git checkout -b my_new_branch``` You can call the branch something different if you want! The -b flag means create the new branch.
- Add and commit your changes to the new branch
- Now switch back to the master branch by typing ```git checkout master```. Open your sketch and verify that you are at the latest version of the project on the master branch.
- You can switch branches at anytime by typing ```git checkout THE_BRANCH_NAME```
- If you want to send this new branch to the server, checkout the branch (no -b flag this time) and type:
  - ```git push --set-upstream origin my_new_branch```
  - ```git push```

Deleting files
- git will normally just store files that have been added or modified in a commit. Files that are deleted don't get deleted in the commit so that if you checkout that commit, the files that you deleted will reappear. If you have deleted files in a commit you should use ```git add . --all```. Try it!

Branching
- You can create multiple branches in git if you want to try new stuff without screwing up your project. In fact it is common to create a new branch every time you want to add a new feature and then merge the branch into the master branch when the feature is completed. Lets try this.
- Type ```git checkout master``` to switch to the head of the master branch
- Type ```git branch``` This shows you what branch you are currently on. You can also type ```git branch --all`` to show all the branches.
- Type ```git checkout -b test_branch``` to create a new branch and switch to it
- Make some changes to to your Processing sketch and save them
- Add and commit these changes.
- To send this new branch to the server type:
  - ```git push --set-upstream origin test_branch```
  - ```git push```
- Type ```git checkout master``` to switch to the master branch and check your Processing sketch to make sure your changes are gone.
- Type ```git checkout test_branch``` and open the Processing sketch to make sure your changes are back again
- Type ```git checkout master``` to switch to the master branch again
- Now lets merge the test_branch changes into the master branch. Type ```git merge test_branch``` to do this
- Open your sketch and see that the changes you made on the test_branch have been merged in.
- Add and commit your merged changes.


Dealing with merge conficts
- Often, git will merge edits in files automatically, but merge conflicts can occur whenever commits have edits on the same line of the same file. This can happen even when only one person is working on a project. When this happens, git will tell you what files are causing problems and mark up the files with the changes from both commits.
- Give your team mate permission to commit to the repository. To do this, go to Settings | Collaborators and add their github id. Your team mate can clone the repository by typing:
  - ```git clone THE_URL_OF_THE_REPO```
- Now both of you should make some edits to the same file. Make some edits on the same lines of the file and on different lines of the file
- Your team mate should add, commit an push their changes. You can jump onto the github website and verify that their changes have been pushed
- Now you should add commit and try and push your changes. You will get a message that looks like this:

  ```
  To https://github.com/skooter500/TestGit
   ! [rejected]        master -> master (non-fast-forward)
  error: failed to push some refs to 'https://github.com/skooter500/TestGit'
  hint: Updates were rejected because the tip of your current branch is behind
  hint: its remote counterpart. Integrate the remote changes (e.g.
  hint: 'git pull ...') before pushing again.
  hint: See the 'Note about fast-forwards' in 'git push --help' for details.
  ```
- What this is saying is that there are changes on the server that you dont have and you need to pull and merge them before you can send your commit. To do this type:
- ```git pull```
- Now the changes from the head of the master branch on the server will get merged into your local git repository. git will attempt to merge files, but in this case you should get a merge conflict. It looks like this:

  ```
  Auto-merging TestGit/TestGit.pde
  CONFLICT (content): Merge conflict in TestGit/TestGit.pde
  Automatic merge failed; fix conflicts and then commit the result.
  ```
- If you open the file in question, you will see that it has been edited to look something like this:

  ```
  <<<<<<< HEAD
  // Hello from Bryan!
  =======
  // Hello from Tara!
  >>>>>>> c365e047b35d76bf3b2d48f38980db4b68746825

  void setup()
  {
  }
  ```
- The bits between <<<<<<< HEAD and ======= are the changes from your commit and the changes between ======= and >>>>>>> c365e047b35d76bf3b2d48f38980db4b68746825 are the changes from your team mates commit. Decide which bit you want to keep and delete the unwanted bits from the file and then add, commit and push your changes.

Merge conflicts on binary files
- Git can merge text files, with source code, but it cant merge binary files such as images. Lets see how to handle this
- Add an image to your project and have your team mate, commit and push this change.
- Have your team mate pull the repo to get the image.
- Now you should both have the image. Both of you should edit the image and save the changes
- Both you and your team mate should add and commit this change, but have your team mate push first
- When you try to push, you will get a message saying that your push has been rejected and you need to do a pull first

  ```
  To https://github.com/skooter500/TestGit
   ! [rejected]        master -> master (fetch first)
  error: failed to push some refs to 'https://github.com/skooter500/TestGit'
  hint: Updates were rejected because the remote contains work that you do
  hint: not have locally. This is usually caused by another repository pushing
  hint: to the same ref. You may want to first integrate the remote changes
  hint: (e.g., 'git pull ...') before pushing again.
  hint: See the 'Note about fast-forwards' in 'git push --help' for details.
  ```

- When you do a pull, you will get a merge conflict on the image file:

  ```
  From https://github.com/skooter500/TestGit
     c365e04..43b59e5  master     -> origin/master
  warning: Cannot merge binary files: TestGit/test.JPG (HEAD vs. 43b59e5d2c53c909fb227a02b6e65681fa91e42a)
  Auto-merging TestGit/test.JPG
  CONFLICT (content): Merge conflict in TestGit/test.JPG
  Automatic merge failed; fix conflicts and then commit the result.

  ```
- git doesn't know how to deal with these edits and so to resolve this conflict, you have to decide which version of the file you want to keep, the one from the server, or your version. If you want to keep your version, you type:
  - ```git checkout --ours THE_FILE_NAME```
  - Don't forget to use / to seperate paths and use TAB to complete commands
  - If you want to keep the version from the server you can type
  - ```git checkout --theirs THE_FILE_NAME```
  - You can type these commands multiple times if you want to just swicth between the two versions to compare them.
- When you are done, add, commit and push your changes

Congratulations! I suggest you finish the lab by setting your assignment up on git

# Week 6 - Conway's Game of Life

- Stephen Hawkings on the Game of Life:

  [![YouTube](http://img.youtube.com/vi/CgOcEZinQ2I/0.jpg)](https://www.youtube.com/watch?v=CgOcEZinQ2I)

- John Conway on the Game of Life:

 	[![YouTube](http://img.youtube.com/vi/FdMzngWchDk/0.jpg)](https://www.youtube.com/watch?v=FdMzngWchDk)

- Epic Conway's Game of Life:

  [![YouTube](http://img.youtube.com/vi/C2vgICfQawE/0.jpg)](https://www.youtube.com/watch?v=C2vgICfQawE)

- My project - Infinite Forms   
  
  [![YouTube](http://img.youtube.com/vi/MrDllboNJKY/0.jpg)](https://www.youtube.com/watch?v=MrDllboNJKY)
	
- And finally, Alan Watts

  [![YouTube](http://img.youtube.com/vi/wU0PYcCsL6o/0.jpg)](https://www.youtube.com/watch?v=wU0PYcCsL6o)

- [Conway's Game of Life on Wikipedia](https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life)
- [The Game of Life Wiki](http://www.conwaylife.com/wiki/Main_Page)

## Lab
### Learning Outcomes
- Complete the game of life code
- Practice iterating over a 2D array
- Discover the amazing power of cellular automata

Try and complete the Game of Life we started in the class today. Here is the [code from the class](processing/life1).  Ive given a list of methods you could implement. If you get your basic game of life to evolve, you could try these additions:

- The method ```void mousePressed()``` gets called in your sketch whenever the mouse is pressed. The method ```mouseDragged``` gets called whenever you hold the mouse down and move it over your sketch. You can get the mouse x and y coordinates by using the built in variables ```mouseX``` and ```mouseY```. You can use these methods to implement mouse drawing. To do this you need to calculate which row and column in the 2D array the mouse is over and then set this cell to be true.

- When you press the space key, the game should pause and unmpause, in other words, not update the game board while the game is paused
- When you press the c key, the board should clear. In otherwords, you should set every element in th 2D array to be false.
- When you press the r key, you should randomly set 50% of the elements to be true. To do this, you need to iterate through the array and generate a random number between 0.0f and 1.0f. If the number is > 0.5f, you set the element to be true otherwise set it to be false.
- Here is [a modification to have colours](https://jimblackler.net/blog/?p=384)

There some interesting starting patterns you can program also. You could write code so that when you press a number key it creates the starting pattern at the mouse x and y. I used the mouse x and y to be the top left of the shape.

| Pattern | Description |
|---------|-------------|
|![Sketch](images/p13.png) | Gosper Gun |
|![Sketch](images/p14.png) | Lightweight spaceship |
|![Sketch](images/p15.png) | Tumbler |
|![Sketch](images/p16.png) | Glider |
|![Sketch](images/p17.png) | I'm not sure what this is called, but it makes amazing patterns |

# Week 5 - More on Classes & ArrayList's
- [Partial solution to the lab test from last year](processing/StarMap1). This has an example of using a class, an ArrayList and it draws the grid.
- [Our implementation of the Processing map function](processing/map)

## Videos 
[![YouTube](http://img.youtube.com/vi/nicMAoW6u1g/0.jpg)](https://www.youtube.com/watch?v=nicMAoW6u1g)

# Lab
## Learnning outcomes
- Make classes
- Use an ArrayList
- Use the Processing map function
- Get familiar with loading a CSV dataset
- Get practice for the lab test

### Part 1  
Today, try to finish off the last part of [last years lab test](https://github.com/skooter500/OOP-LabTest1-2016), which is being able to click on stars and calculate the distance in parsecs between the two stars. 

### Part 2

- Have a go at completing the [lab test from 2014](https://github.com/skooter500/OOP-2016-2017/blob/master/processing/ExpensesProcessing/Lab%20Test%201.docx?raw=true). It's not as much fun, but you can get the chance to practice a lot of the concepts we have learned in the class in the past couple of weeks:
	- Making a class with constructors
	- Loading a dataset
	- Using an ArrayList
	- Iterating over an ArrayList
	- Visualising a dataset
	- Using the map function
- Here is a link to [the dataset you need](https://raw.githubusercontent.com/skooter500/DT228-OOP/master/Processing%20Examples/Expenses/data/expenses.txt)

# Week 4 - Classes & ArrayList's
- [Last years lab test](https://github.com/skooter500/OOP-LabTest1-2016)
- [Download the star dataset](https://raw.githubusercontent.com/skooter500/OOP-LabTest1-2016/master/HabHYG15ly.csv)
- [loadTable refererence](https://processing.org/reference/loadTable_.html)
- [map reference](https://processing.org/reference/map_.html)
- [Classes in Processing](https://processing.org/reference/class.html)
- [ArrayList reference](https://processing.org/reference/ArrayList.html)

## Lab
## Learning outcomes
- Make classes
- Use an ArrayList
- Use the Processing map function
- Get familiar with loading a CSV dataset
- Get practice for the lab test

[Here is the code that we wrote in the class today](processing/StarMap1). It has:
- A star class with multiple constructors
- loadTable to load a csv file of data
- An ArrayList of Star objects

[See how far you get in completing last years lab test](https://github.com/skooter500/OOP-LabTest1-2016).
Don't be tempted to look at the solution straight away, try and code a solution yourself.

# Week 3 - Loops & Arrays
![Sketch](images/p6.png)
![Sketch](images/p23.png)

- [Loops example](processing/loops)
- [Arrays examples](processing/arrays)

## Lab 
### Learning outcomes
- Practice iterating over arrays in Java
- Practice in using the for loop and variables to generate sequences of numbers
- Understand how a line graph is made
- Practice constructing alogorithms as part of a system
- Practice presenting data visually

Here is [some starter code with examples of arrays](processing/arrays)

Here is what you can try and make today:

![Sketch](images/p7.png)

These are the steps I suggest you follow:

- Figure out how to draw a trend line graph first
- Then figure out how to leave horizontal and vertical borders around the graph. I would suggest making a variable called border to control this.
- Then figure out how to scale it so that it scales the data when drawing to the range 0-150. You could make this a variable
- Then figure out how to draw the horizontal axis. This will be a for loop obviously. You might find the following Java/Processing methods useful:
  - [The Processing map method](https://processing.org/reference/map_.html)
  - [text](https://processing.org/reference/text_.html) - Prints text to the screen at x and y coordinates
  - [textAlign](https://processing.org/reference/textAlign_.html)
  - [substring](http://www.tutorialspoint.com/java/java_string_substring.htm)
- Finally figure out how to draw the vertical axis. Another loop! This is the trickiest part I think

Try and parameterise as much of your sketch with variables, so that you could reuse the code to graph other types of data.
For example, I found it useful to write a method:

```Java
void drawAxis(float[] data, String[] horizLabels, int verticalIntervals, int maxVertical, float border)
```

to draw the horizontal and vertical axes. You might like to write seperate methods for the horizontal and vertical axis.
This took me about an hour to complete today, so it's tricky enough to get everything working, but worth it!

- [Solution](processing/data)

### Advanced!

Try and draw this pie chart:

![Sketch](images/p8.png)

You can use the Processing arc method to do this!

- [Solution](processing/data)

## Tutorial

[![YouTube](http://img.youtube.com/vi/WXftKFCtPrQ/0.jpg)](https://www.youtube.com/watch?v=WXftKFCtPrQ)

There is a bug running Processing through Java 9, so you have to run Processing with Java 8 instead
To change the version of Java to Java 8 on the Mac:

```bash
export JAVA_HOME=`/usr/libexec/java_home -v 1.8`

```

```Java
package ie.dit;
import processing.core.PApplet;

public class AudioViz extends PApplet {

	public void setup()
    {
    }

    public void settings()
    {
        size(500, 500);
    }

    public void draw()
    {
    	background(0);
    	stroke(255);
    	line(100, 100, 200, 200);
    }

    public static void main(String[] args)
    {
        String[] a = {"MAIN"};
        PApplet.runSketch( a, new AudioViz());
    }
}
```

This is how to compile and run a Processing Java program on Mac:

```bash
javac -classpath /Applications/Processing.app/Contents/Java/core.jar ie/dit/*.java
java -classpath /Applications/Processing.app/Contents/Java/core.jar:. ie.dit.ProcessingTest
```
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
