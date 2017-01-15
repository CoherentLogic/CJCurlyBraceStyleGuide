# The Chocolate Jollis Grand Guide To The (Actual) One True Curly Brace Programming Style

This grand guide will make your curly-bracey programs look way cooler than anyone else's, because its author is an opinionated so-and-so.

## Module Headers

Module headers should follow the following format:

    /*
     *  foo.c
     *   Quick one-liner describing what foo.c does
     *
     *  Author: First M. Last <indent@thegods.com>
     *   Copyright (C) YYYY Foobler Code Snax, Inc.
     *
     *  Last modified: 7 January 1635
     *
     *  YOUR FAVORITE LICENSE BLOCK HERE
     *
     **/

## Variable Naming

Obviously, this_type_of_thing is objectively the only right way of naming variables, but the cretins who designed certain languages have adopted other, inferior conventions.

Your code will probably have to play in a world full of camelCase and PascalCase cretinism, and maybe even lpszHungarianNonsense. Stick with the dominant convention in your particular world. Especially in Javascript. I've done this_type_of_thing in JS before, because as previously mentioned, it's objectively the obvious superior choice, but then I've had to call into the code of other cretins, and get forced to mix camelCase crap with the_one_true_way. This looks worse than justDoingCamelCase.

## Indentation

Two or four *spaces* are the correct way. Tabs screw up editors, and eight spaces look looser than certain anatomical regions belonging to women of the night. Don't be a code-slut. If you do it my way, everyone will rejoice.

## Brace Placement

### For functions:

    int main(int argc, char **argv)
    {
	...
    }

### For if statements:

    if(x) {

    }
    else {

    }

We don't tolerate any of that } else { nonsense. Looks like that Star Wars scene where what's his face was about to get crushed in the trash compactor.

Also, NEVER do this:

    if(x)
        foo();


By "this", I obviously mean omitting the curly braces. You may THINK you'll never add a second line to that conditional, and you may THINK that if you do, you'll remember to add the braces then. You WILL add more lines, and you WILL forget to add the braces. Just because the designers of the language were daft enough between the ears to even *allow* such nonsense, it doesn't mean you have to fall prey to it.

You MAY, however, do one-liners like this:

    if(x) foo();

But that's it.

### For other constructs:

    for(i = 1; i < 10; i++) {
        ...
    }
    
## Overall Program Spacing

* Variable declarations fall immediately beneath the opening curly brace, and should initialize the variable right there whenever initialization is used.
* One line between the last variable declaration and the first line of real code.
* 




