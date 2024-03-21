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

<img src="https://raw.githubusercontent.com/conorkeane01/digital-rain-cpp-ck/main/docs/assets/images/randomSymbol.png" width="600" height="100">





[Problem Solving](https://conorkeane01.github.io/digital-rain-cpp-ck/demo/2024/03/11/Problem-Solving.html)
