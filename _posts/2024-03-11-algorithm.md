---
layout: post
title: Algorithm
tags: cpp coding project
categories: demo
---

## Algorithm

**This part of the blog will focus on the algorithm I used for printing the digital rain to the console**

Starting out I first wanted to print a basic letter to the console. For the digital rain I wanted each letter printed to the console to be random. To do this `cstdlib` library must be included. Once that is done the `rand()` function can be called. 

<img src="https://raw.githubusercontent.com/conorkeane01/digital-rain-cpp-ck/main/docs/assets/images/randomLetter.png" width="600" height="100">

I used the code above to get my random letter. This is done by doing the following. `rand() % 26 + 'a'` uses the ascii value of `a`, and selects a random integer within the range of 0 to 25. This means the random letter can be any lowercase letter between a to z. The `static_cast<char>` changes the random letter from an integer to a char value. This is needed as my vector will print characters.

I did not want to have my random characters for my digital rain to be limited to just the 26 characters of the alphabet, and be lowercase. To extend this random function I took a look at the ascii table `[4]`.

<img src="https://raw.githubusercontent.com/conorkeane01/digital-rain-cpp-ck/main/docs/assets/images/ascii1.png" width="600" height="400">

From this image I saw the `!` syboml was the first single symbol. I did not want any symbols that had more than two characters, for example `sp` had two symbols and is described as a space. I did not want to pick this one as it could cause problems in my algorithm.

<img src="https://raw.githubusercontent.com/conorkeane01/digital-rain-cpp-ck/main/docs/assets/images/ascii2.png" width="600" height="400">

I then scrolled to the bottom of the ascii table and saw after `~` the next symbol was delete and I did not want this symbol incase it messed with my algorithm. So i chose the range to be between 0 and 126

<img src="https://raw.githubusercontent.com/conorkeane01/digital-rain-cpp-ck/main/docs/assets/images/RandomSymbol.png" width="600" height="100">

With this random sybmol code I could now print random symbols to the console like so

<img src="https://raw.githubusercontent.com/conorkeane01/digital-rain-cpp-ck/main/docs/assets/images/randomSymbol2.png" width="600" height="400">

To print these random sybmols and characters like the screenshot above I used this algorithm

<img src="https://raw.githubusercontent.com/conorkeane01/digital-rain-cpp-ck/main/docs/assets/images/algorthm2.png" width="600" height="400"> 

To get these random sybmols onto the console i used the `operator<<` overload. I found this the easiest way to print straight to the console.
I then created a for loop to go through the rows I had declared earlier in the code.
As explained before I use the `rand()` function to get a random symbol
I print the first symbol to the console. I now have to step below this character and print the next character. 
For the `std::this_thread::sleep_for(std::chrono::second(1));` I included the `<chrono>` library and the `<thread>` library to use this standard library call. It works by pausing the operator for a second so the symbols print to the screen every second.


Once I had a row of random symbols, I again wanted to change it up and create a better "rain affect". I was going to do this by changing the spaces between the random symbols.
For example:

e 

f


c

a

s

and so on. I wanted to create this affect so when I added more columns there would not be symbols beside eachother and look like a falling sentences and not rain drops.

<img src="https://raw.githubusercontent.com/conorkeane01/digital-rain-cpp-ck/main/docs/assets/images/algorithm3.png" width="600" height="400"> 

I added a variable called `spaceLength`. This uses the `rand()` to get a number between 1 and 3. Depending on this number an `if` statement is used so that depending on this number a gap of 1 2 or 3 is made. This is done by printing mulitple `std::endl`

<img src="https://raw.githubusercontent.com/conorkeane01/digital-rain-cpp-ck/main/docs/assets/images/symbolGaps.png" width="600" height="400"> 

Now that I had one row printing perfectly the way I wanted. I was looking at recreating this loop but this time in new columns. This would create the digital rain.
My first idea was to place my row loop into a column loop. This would make it so it would print the first row and then move into the next column. However I ran into problems that it would print the first row, finsih printing the first row and then move into the next column.

I first decided to add a nested for loop like below. I hoped this would step through the columns and rows so that it gave me the digital rain affect I was looking for

<img src="https://raw.githubusercontent.com/conorkeane01/digital-rain-cpp-ck/main/docs/assets/images/nestedLoop.png" width="600" height="100"> 

This loop created a bug in my earlier `if` statement, becuase I was using `std::endl;` this would not let the digital rain run into more columns and would just create a new line. I removed the `std::endl` and added `" "` instead so that it would still created random spacing.
With this complete I had made my algorithm.

### Final Algorithm
In the algorithm I 
- Use the `operater<<` overload
- Have a nested for loop
   - `for(auto i = 0; i < m.GetRows(); ++i` steps through the rows of the matrix
   - `for(auto j = 0; j < m.GetCols(); ++j` steps through the columns of the matrix
- `std::vector<char> rowChars;` creates a vector of the standard library to recieve in characters
- `char randomChar = static_cast<char>(rand() % 126 + '!');` adds a random character to value like explained earlier
- `rowChars.push_back(randomChar);` Adds the random character to the back of the vector
- `for (auto const& ch : rowChars) ` this range loop is used to print out the vector to the console
- The `spaceLength` `if` statement is used to add random spaces to the console to space out characters and give a better digital rain affect
- `output << std::endl;` the random characters and symbols are printed to the console
- `std::this_thread::sleep_for(std::chrono::milliseconds(150));` This delays the characters and symbols being printed to the cnsole like before.
- `return output` the `operator <<` must return a value  
<img src="https://raw.githubusercontent.com/conorkeane01/digital-rain-cpp-ck/main/docs/assets/images/algorithm4.png" width="600" height="400">

This would be my alogrithm for printing Digital Rain to the console.
The digital rain would look like below

<img src="https://raw.githubusercontent.com/conorkeane01/digital-rain-cpp-ck/main/docs/assets/images/rain.png" width="600" height="400">

[Problem Solving](https://conorkeane01.github.io/digital-rain-cpp-ck/demo/2024/03/11/Problem-Solving.html)
