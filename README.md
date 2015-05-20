# Refactoring Code

I recently got the opportunity to prepare a technical mile stone presentation for my program in Electrical and Computer Engineering. The topic of my presentation was on refactoring code, but seeing as i was limited to 15 minutes, I found this to be a nice opportunity to expand my thoughts on how to write great, readable code.

# Intro

**Code is read more than it is written**, I have no idea who actually said this; but it seems they were onto something. I believe that there is great value in changing the way we think about code. We all get so obsessed with having some brilliant new feature and performance improvement that how readable that code is takes a back seat.

Writing good, refactored and readable code has the following benefits 

1. Makes it more enjoyable for your co workers to work with your code
2. Makes it easier for other people to change code in the future
3. Saves a lot of money by not wasting peoples time with trying to decipher code
4. Makes you feel good inside, kinda like cleaning your room 
5. Allows you to discover places for hidden performance improvements
6. It makes you a better programmer overall 
7. Its something that extends all languages and levels of expertise

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

1. [AngularJS](https://github.com/johnpapa/angular-styleguide)
1. [Javascript](https://github.com/airbnb/javascript)
1. [Ruby](https://github.com/airbnb/ruby)
1. [C++/C](https://google-styleguide.googlecode.com/svn/trunk/cppguide.html)

## Remove Redundant Redundancy

This is something that you should always be looking out for. Never do more than what is needed for you. This can apply to entire feature implementations or it could be something as simple as not including a `return`, if it is not needed

One of the common things that i see happen, is that someone will be tyring to implement a new feature, and to do so, they will create all the needed code them selves. Now there is a likely chance that there was some existing code in the app that did the same thing, and you have just now duplicated functionality. If your lucky this will be just something that makes the code look ugly, however there is a likely chance that you are now doing the same thing twice. This can sometimes have very negative affects; for example, imagine making multiple uneeded http requests to the server, for the same data because you were unaware of the existing ones

For examples

- You dont need the ternary operater in an example like this

```javascript
(object.hasPermission != 0) ? true : false
```

- You dont need the return statement in this example (only applicable to some langauges)

```javascript
function add(x, y) {
	return x + y;
};
```

- If your having a hard time with naming a variable, there is likey chance that you dont need it

```javascript
var boolean = subject.hasPermission;

if (boolean) {
	//do something
} else {
	//do something else
}
```

**Other Tips**

- Always check your logs to ensure that you are not doing the samething twice
- Make sure you get a code review, so that other coworkers can make you aware of code that already exists

## DRY 

- Dont repeat yourself
- Apply this when ever you can, from test cases to front end code

## Lines Of Code

Line count is not a good way to measure how readable or good your code is, in fact its quite the oposite. Now this goes against another great rule, which is _the best code is no code_, and this may give you the incentive to try and reduce the number of lines in your code. However, going out of your way to create super compact code, will make the code much harder to understand in the future for yourself and others.


```javascript
function add(x, y) {
	x + y;
};
```

- No one actually ever uses an add function, I mean why would you? All that happens is that you increase the lines of code, and you dont acheive anymore readability 

- However, imagine that you were adding currency; and up until this time you were adding the same currency. But what if in the next month, the project now asked for adding diffferent currency. With a pre-existing add function, you only have to update the function and the changes are seen every where 

- Always make descicions with the future in mind. Have the worst case scenerio in mind.

## Dont Comment

- Write code so that you dont need to comment 

- Dont write comments to explain the basic features of a language

## Small Methods

- A method/function should do one thing and one thing only, this is more likely to be true if your methods are smaller.
- Try as much as you can to reduct the number of conditionals
- Try and reduce the number of arguments that your method requires to function
- Name your methods accordignly, If the purpose of a function is to get a file name, the method should be defined as `getFileName`
- Keep to language specific naming conventions
- Use semi-colons when ever needed (Javascript)

## Objects Vs Procedures

##### Procedures

Pros:

- Easy to read
- Everything you need is all in one place

Cons:

- Hard to change
- Hard to test
- They can grow, eventually negating the _Easy to read_ point

##### Objects

Pros:

- Easy to change
- Easy to test
- Requires less reading of code

Cons:

- You never fully get the whole picture of what your code does, only little peices
- Feels like extra work to write code in this pattern

## Code Review

- Make sure you get someone else to approve your code before merging
- When doing a code review look for more than just passing tests and functionality; Look for things like abstractability, better use of data structures or algorithms, naming conventions etc
- Always look out for existing functionality and code
- Try and keep up to date with your own reviews, If you give feed back try and confirm the resulting changes

## Decoupling

In Progress

