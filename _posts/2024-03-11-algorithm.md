---
layout: post
title: Algorithm
tags: cpp coding project
categories: demo
---

##Algorithm

This part of the blog will focus on the algorithm I used for printing the digital rain to the console 

Starting out I first wanted to print a basic letter to the console. For the digital rain I wanted each letter printed to the console to be random. To do this `cstdlib` library must be included. Once that is done the rand() function can be called. 

<img src="https://raw.githubusercontent.com/conorkeane01/digital-rain-cpp-ck/main/docs/assets/images/randomLetter.png" width="600" height="100">

I used the code above to get my random letter. This is done by doing the following. rand() % 26 + 'a' uses the ascii value of 'a', and selects a random integer within the range of 0 to 25. This means the random letter can be any lowercase letter between a to z. The static_cast<char> changes the random letter from an integer to a char value. This is needed as my vecture will print characters.

I did not want to have my random characters for my digital rain to be limited to just the 26 characters of the alphabet, and be lowercase. To extend this random function I took a look at the ascii table.

<img src="https://raw.githubusercontent.com/conorkeane01/digital-rain-cpp-ck/main/docs/assets/images/ascii1.png" width="600" height="400">

From this image I saw the `!` syboml was the first single symbol. I did not want any symbols that had more than two characters, for example `sp` had two symbols and is described as a space. I did not want to pick this one as it could cause problems in my algorithm.

<img src="https://raw.githubusercontent.com/conorkeane01/digital-rain-cpp-ck/main/docs/assets/images/ascii2.png" width="600" height="400">

I then scrolled to the bottom of the ascii table and saw after `~` the next symbol was delete and I did not want this symbol incase it messed with my algorithm. So i chose the range to be between 0 and 126

<img src="https://raw.githubusercontent.com/conorkeane01/digital-rain-cpp-ck/main/docs/assets/images/RandomSymbol.png" width="600" height="100">

With this random sybmol code I could now print random symbols to the console like so

<img src="https://raw.githubusercontent.com/conorkeane01/digital-rain-cpp-ck/main/docs/assets/images/randomSymbol2.png" width="600" height="400">

To print these random sybmols and characters like the screenshot above I used this algorithm

<img src="https://raw.githubusercontent.com/conorkeane01/digital-rain-cpp-ck/main/docs/assets/images/firstAlgorithm.png" width="600" height="400">

To get these random sybmols onto the console i used the `operator<<` overload. I found this the easiest way to print straight to the console.
I then created a for loop to go through the rows I had declared earlier in the code.
As explained before I use the `rand()` function to get a random symbol
I print the first symbol to the console. I now have to step below this character and print the next character. To do this I use a nested for loop
Inside the nester for loop I redeclare the random symbol. I need to do this or the same symobl will be printed down the rows.
For the `std::this_thread::sleep_for(std::chrono::second(1));` I included the `<chrono>` library and the `<thread>` library to use this standard library call. It works by pausing the operator for a second so the symbols print to the screen every second.


Once I had a row of random symbols, I again wanted to change it up and create a better "rain affect". I was going to do this by changing the spaces between the random symbols.
For example:
e 

f


c

a

s

and so on. I wanted to create this affect so when I added more columns there would not be symbols beside eachother and look like a falling sentences and not rain drops.












[Problem Solving](https://conorkeane01.github.io/digital-rain-cpp-ck/demo/2024/03/11/Problem-Solving.html)
