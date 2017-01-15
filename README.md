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

We don't tolerate any of that `} else {` nonsense. Looks like that Star Wars scene where what's his face was about to get crushed in the trash compactor.

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

## Nested Stuff

When nesting blocks of code more than one level deep, put a C-style comment after each terminating curly brace giving a hint as to what that curly brace is terminating. Only do this when you feel generous and disciplined enough to do it, but always complain about code that doesn't do it. This will lend you the cranky air that is one element of reputational currency in most development communities. Note that the comment repeats the conditional here. If you feel like it, just put the type of construct. This will make your program more maintainable but less readable. Programming can be a pain.

    if(x) {
        if(y) {
            if(z) {
                ...
            } /* if(z) */
        } /* if(y) */
    } /* if(x) */

In the same vein, functions should have a C-style comment one space following their terminating right curly brace:

    my_function()
    {

    } /* my_function() */

This terminating comment *must not* repeat the function's signature, but *must* include the parens to denote that it's a function. Why *must* and *must not*, you ask? Because I said so, and I'm an opinionated bastard. 
    
## Overall Program Spacing

* Variable declarations fall immediately beneath the opening curly brace, and should initialize the variable right there whenever initialization is used.
* One line between the last variable declaration and the first line of real code.
* The `return` statement of a function (when used as the last line of a function) should have one blank line above it and none below it.
* Never put unnecessary spaces, such as `if (x)`. Obviously, `if(x)` is correct.
* The `return` statement shouldn't really have parens around its expression. I used to think otherwise, but I've changed my mind on that. It's not a function.

Here's an example of some good stuff:


    int my_function(int x, int y)
    {
        int i = 1;
        int foo = 2;
        
        if(x) {
            if(y) {
                foo(i);
            } /* if(y) */
        } /* if(x) */    
        
        
        return x + y;
    } /* my_function() */


Write code like that, and you can show it off at geek-parties, nerd-fests, etc.


## The *switch()* Statement

Really, `switch` constructs that fall through are stupid. Each case ought to be able to accept a proper list of expressions, instead of falling through. But, we don't live in a world like that. So this is the way you're going to do it, *or else*:

    switch(foo) {
        case some_const:
            foo();

            break;
	case some_other_const:
            bar();

            break;	    
        default:
            exit(1);

            break;
    } /* switch() */	    

Note how each `case` is indented beneath the `switch`. This is because we're pretending that curly-brace languages' `switch` constructs are more than just labels to which the compiler will generate a jump instruction, and instead a proper high-level construct. Being the former is fine for C/C++, I suppose, since those languages are really intended for low-level work. But Javascript? Hell no. Brendan Eich was a moron for carrying this forward. It should have looked like this:

    switch(foo) {
        case(some_const) {
            foo();			
        }
        case(some_other_const) {
            bar();
        }	
	else {
            exit(1);
	}
    }

But, alas, it doesn't.