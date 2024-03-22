---
layout: post
title: Design & Test
tags: cpp coding project
categories: demo
---
## Design and Test

This part of the blog will focus on how I designed and tested my code.

I wanted my digital rain to be like rain and fall from the sceen row by row. For example the first 4 or 5 characters in row 1 would print, then row 2 would start and so on and so forth. Something like this:
a l a j
f q f y
c x h i
h o n 
f w 
b r 
g
v

and so on until all the characters would fill the rows and columns

I based my algorithm around this so I beileved once I got the first row printing, I could repeat the code and have get it working the way I wanted. Due to lack of time and other projects I had to submit, I ran out of time to persue this idea

As I did not have the time I would have to work on a different design and used a nested for loop. This made it so the characters were being printed column by column like how you would write left to right.
c q p d a r f a q f ->
d w r g s q l y ->
d r y u b h ->

This did not give the "rain" affect I wanted.

I designed my code also using `system("Color 09)`. This changed the colour of the characters being printed to the console. I changed this colour to blue to make it look like rain, compared to the usual matrix affect, which is popular with digital rain, that uses the colour green.

My code used Object Oriented programming. This meant I could use constructors and deconstructors. To take advantage of this I used a default constructor to set the value for rows and columns 

<img src="https://raw.githubusercontent.com/conorkeane01/digital-rain-cpp-ck/main/docs/assets/images/settingValues.png" width="600" height="400">

I also used a deconstructors then to deconstruct the matrix after it had been printed. I also left a design in the deconstructor too as a way of signalling that the digital rain had finished.

<img src="https://raw.githubusercontent.com/conorkeane01/digital-rain-cpp-ck/main/docs/assets/images/deconstructor.png" width="600" height="400">

There is also a copy constructor created when the code starts. I have this commented out so it does not affect the digital rain affect.
<img src="https://raw.githubusercontent.com/conorkeane01/digital-rain-cpp-ck/main/docs/assets/images/copyCon.png" width="600" height="400">

In my `Matrix.h` headerfile I declare these constructors and deconstructors

<img src="https://raw.githubusercontent.com/conorkeane01/digital-rain-cpp-ck/main/docs/assets/images/matrixH.png" width="600" height="400">

In my `TestMatrix.h` headerfile I am declaring the functions I will use. This is how I run and test my code

<img src="https://raw.githubusercontent.com/conorkeane01/digital-rain-cpp-ck/main/docs/assets/images/TestMatrixH.png" width="600" height="400">

In my `main.cpp` file I have a try and catch around the `RunTests()` function so if any errors occur. Other than that all main does is run this function that is located in my `TestMatrix.cpp` file

<img src="https://raw.githubusercontent.com/conorkeane01/digital-rain-cpp-ck/main/docs/assets/images/mainCpp.png" width="600" height="400">

In `TestMatrix.cpp` the `RunTests()` function is ran, it passes Matrix m into the `TestDefaultCstr` function which runs the constructors, deconstructors and prints the digital rain to the console.

<img src="https://raw.githubusercontent.com/conorkeane01/digital-rain-cpp-ck/main/docs/assets/images/TestMatrixCpp.png" width="600" height="400">


[More About This Project](https://conorkeane01.github.io/digital-rain-cpp-ck/posts/2024-03-11-digital-rain-cpp.html)









