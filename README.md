# Refactoring Code

I recently got the opportunity to prepare a technical mile stone presentation for my program in Electrical and Computer Engineering. The topic of my presentation was on refactoring code, but seeing as i was limited to 15 minutes, I found this to be a nice opportunity to expand my thoughts on how to write great, readable code.

# Intro

**Code is read more than it is written**, I have no idea who actually said this; but it seems they were onto something. I believe that there is great value in changing the way we think about code. We all get so obsessed with having some brilliant new feature and performance improvement that how readable that code is takes a back seat.

Writing good, refactored and readable code has the following benefits 

Makes it more enjoyable for your co workers to work with your code
Makes it easier for other people to change code in the future
Saves a lot of money by not wasting peoples time with trying to decipher code
Makes you feel good inside, kinda like cleaning your room 
Allows you to discover places for hidden performance improvements
It makes you a better programmer overall 
Its something that extends all languages and levels of expertise

The rest of this guide will be a list of all the things that you can do to improve your code. They are structured in a way so that the earlier items are ones that just about anyone can do, while the later ones are bigger structural changes 

_Note:_ Some of these tips you may not agree with, and that’s fine. There are a lot of things that are subjective and can differ between the team that you work with and the technology that you use.

## Table of contents

1. [Tests](#tests)
1. [Style Guides](#style-guides)
1. [Remove Redundant Redundancy](#remove-redundant-redundancy)
1. [DRY](#dry)
1. [Lines Of Code](#lines-of-code)
1. [Dont Comment](#dont-comment)
1. [Small Methods](#small-methods)
1. [Objects Vs Procedures](#objects-vs-procedures)
1. [Code Review](#code-review)
1. [Decoupling](#decoupling)

## Tests

The number one rule of refactoring has nothing to do with refactoring.

- Dont try to refactor unless you have tests cases
- Make sure all your tests are passing before the refactoring and more importantly after
- Remeber the process of refactoring code has nothing to do with improving performance or adding new features

## Style Guides

Probobly the easiest thing that you can do, is to consult a style guide. They cover some very important topics such as

- How to name your functions
- How to handle overly large if-statments
- When to use certain types
- How to properly format code depending on the language
- The gotcha's of the language 
- Sometimes they will contain use full hints about file structure
- They contain info on what kind of associated technologies you should use

Some of the great ones I have found are 

(links)

## Remove Redundant Redundancy

This is something that you should always be looking out for. Never do more than what is needed for you. This can apply to entire feature implementations or it could be something as simple as not including an `if-statment`, if it is not needed

One of the common things that i see happen, is that someone will be tyring to implement a new feature, and to do so, they will create all the needed code them selves. Now there is a likely chance that there was some existing code in the app that did the same thing, and you have just now duplicated functionality. If your lucky this will be just something that makes the code look ugly, however there is a likely chance that you are now doing the same thing twice. This can sometimes have very negative affects; for example, imagine making multiple uneeded http requests to the server, for the same data because you were unaware of the existing ones
 