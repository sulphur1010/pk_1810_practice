# CSC1810 Practice Programs

## Specifications are skimpy

The projects described and contained here are meant for fun practice. You won't find these specified to the usual degree.

## single_star

In this program, you'll animate a single asterisk causing it to bounce back and forth from column zero to some column (currently defined as 40).

You'll learn:

* how to force output to happen even before a new line character
* how to overwrite a line on the console (rather than advancing to a new line)
* how to delay your program's executation for a short while (for timing purposes)
* usage of `cinttypes` which makes the specific flavor of an integer unambiguous

### Specification for single star

Write a program that animates a single asterisk like this:

![star](./single_star.gif)

Don't worry about the program terminating - just kill it when you're done looking.

No data structure is needed for this program as everything you need to do is based on a counter.

You'll need this include files:

```c++
#include <iostream>
#include <iomanip>
#include <cinttypes>
#include <chrono>
#include <thread>
```

I used the features of `iomanip` to space out the animating asterisk.

`cinttypes` contains aliases for integer types that are unambiguous. That is, when you say `int`, how big is it? Depends. Using `cinttypes` you can declare (examples, not complete):

| type | meaning | without cinttypes |
| ---- | ------- | ----------------- |
| uint8_t | unsigned 8 bit integer | unsigned char |
| uint16_t | unsigned 16 bit integer | unsigned short |
| uint32_t | unsigned 32 bit integer | unsigned int |
| uint64_t | unsigned 64 bit integer | unsigned long |
| int8_t | signed 8 bit integer | char |
| int16_t | signed 16 bit integer | short |
| int32_t | signed 32 bit integer | int |
| int64_t | signed 64 bit integer | long |

`chrono` and `thread` are used together to implement delays in your program. Without pausing your program, it will update the screen so quickly, you won't be able to enjoy the animation.

For example:

```c++
this_thread::sleep_for(chrono::milliseconds(16));
```

will cause your program to sleep for at least 16 milliseconds but maybe a tad more. The value 16 milliseconds is chosen as it is 1/60th of a second.

### Source code

DO NOT LOOK AT [THIS](./single_star.cpp) UNTIL YOU HAVE TRIED TO WRITE THE CODE YOURSELF! With that said, don't feel bad about taking a peek and reading the comments.

### Related projects

* Multiple stars

## Multiple stars

This program is a little harder. Instead of a single asterisk animating, see if you can make a number of asterisks (in a row) animate - like a Cylon!

![multiple](./multiple_stars.gif)

as in:

![Cylon](./cylon.gif)

Use 8 stars.

### Source code

DO NOT LOOK AT [THIS](./multiple_stars.cpp) UNTIL YOU HAVE TRIED TO WRITE THE CODE YOURSELF! With that said, don't feel bad about taking a peek and reading the comments.

## Fizzle

Taking a different approach, `fizzle` produces this:

![fizzle](./fizzle.gif)

`fizzle` starts with all blanks in a long string. Whenever a position is blank, there is a 1 in 20 chance it will start animating.

The animation cycle is:

* `' '`
* `'.'`
* `'o'`
* `'0'`
* `'O'`
* `' '` (i.e. repeat)

### Source code

DO NOT LOOK AT [THIS](./fizzle.cpp) UNTIL YOU HAVE TRIED TO WRITE THE CODE YOURSELF! With that said, don't feel bad about taking a peek and reading the comments.
