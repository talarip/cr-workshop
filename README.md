# CR Workshop: PART 1

## Why?
Aviod Technical debt. 
Make sure of clean code and simple design and security

## What to make sure in CR?
All ACs are met

Code is obvious for other programmers.
Poor variable naming, bloated classes and methods, magic numbers -you name it- all of that makes code sloppy and difficult to grasp.

No duplication.
Each time you have to make a change in a duplicate code, you have to remember to make the same change to every instance. This increases the cognitive load and slows down the progress.

Minimal number of classes and other moving parts.
Code is liability, keep it short and simple.

Passes all tests.

Easier to maintain.

https://make.wordpress.org/core/handbook/best-practices/coding-standards/php/

https://github.com/jupeter/clean-code-php


# CR Workshop: PART 2

## Bloaters

Bloaters are code, methods and classes that have increased code to great proportions that they are hard to work with. Bloaters do not crop up right away, rather they accumulate over time as the program evolves (and especially when nobody makes an effort to eradicate them).

    Long Method
    Large Class
    Primitive Obsession
    Long Parameter List
    Data Clumps

## Object-Orientation Abusers

These are incomplete or incorrect application of object-oriented programming principles.

    Alternative Classes with Different Interfaces
    Refused Bequest
    Switch Statements
    Temporary Field

## Change Preventers

These mean that if you need to change something in one place in your code, you have to make many changes in other places too. Program development becomes much more complicated and expensive as a result.

    Divergent Change
    Parallel Inheritance Hierarchies
    Shotgun Surgery

## Dispensables

A dispensable is something pointless and unneeded whose absence would make the code cleaner, more efficient and easier to understand.

    Comments
    Duplicate Code
    Data Class
    Dead Code
    Lazy Class
    Speculative Generality

## Couplers

These contribute to excessive coupling between classes or show what happens if coupling is replaced by excessive delegation.

    Feature Envy
    Inappropriate Intimacy
    Incomplete Library Class
    Message Chains
    Middle Man

