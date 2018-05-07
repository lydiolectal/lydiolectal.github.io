---
layout:  post
title:  "Week 5: Belated belated updates"
date:  2018-05-05 17:12:31 -0500
categories:
---

Much has happened since my last blog post; the weather here now veers on the side of steaming rather than bone-chillingly wet and cold, I wrote a bug that crashed my computer and gave my very first technical talk about it (!!), and have completed most of the work for a sub-optimal Scrabble-playing AI. All very exciting.

Here, dear readership, is an abbreviated account of what I've done since my last post:

# Week 3

Thought-paired with Steven, Casey on Scrabble solving algorithms. Some of our conclusions:
- Playing a word in Scrabble consists of two main steps: (1) the program must find all possible positions (here, I mean a continuous span of squares) on the board that it can play a word. (2) Given these start positions, search the Scrabble dictionary for words that can be played at that position. This search is constrained by tile availability and by the letters already on the board.
- We must consider the possibility that the word we add to the board creates other letter sequences by extending preexisting tiles in a direction perpendicular to the direction of our word. For instance (Scrabble board miniaturized for space):
{% highlight python %}
  0 1 2 3 4 5 6
0 . . . . . . .
1 . . . . . . .
2 . . . . . . .
3 . . p a r k .
4 . . i l e a .
5 . . . . . . .
6 . . . . . . .
{% endhighlight %}
- For each spot neighboring a filled square, we can construct a set of letters one could play there to create legal words. For instance, the set at (3, 5) would be {a, b, e, l, p, s, t} because {ala, alb, ale, all, alp, als, ast} are possible one-letter extensions of the word "al". The intersection of this set and the set of the player's tiles is equal to the set of letters that can be played there.

Read [The world's fastest Scrabble program](https://dl.acm.org/citation.cfm?id=42420), a 1988 paper that describes an efficient Scrabble-solving algorithm which finds the highest-scoring word. Was happy to discover that I was on the right track: the authors also suggested using a trie and limiting the search by calculating sets of possible letters that can be played on neighboring squares.

Met Kadeem, my RC project twin. Kadeem also wrote a Scrabble solver during his batch!

Implemented most of the functionality for my Scrabble solver and tested.

Wrote the most gorgeously catastrophic bug I have ever created while trying to implement the function that searches the dictionary for possible words to play. Crashed my computer several times because I exhausted Python's memory resources. (A more in-depth blog post about this bug is in the works.) Felt both proud of and horrified at my achievement.

# Week 4

Successfully removed the Bug of Doom from my Scrabble solver. Huzzah!

Refactored more than I have in my life and re-discovered the beauty of unit testing.

Collaborated with Sarah on an interpreter for Etticalculator, the calculator language that enforces politeness!

Got code review from Bryan on how to better structure my Scrabble code and make the code more readable. Applied his suggestions and found my project much, much easier to understand.

Went birding for the first time in my life. Realized that life expands when I participate in active and intentional perception.

Became very restless and spent a lot of time thinking about what I wanted to do next. Talked to too many people about the respective merits and downfalls of learning Go and Rust.

# Week 5

Continued to be restless and continued to worry about what to work on next.

Decided that, before packing away my Scrabble solver and moving on (for now), I wanted to do a deeper dive into the monstrous bug that had crashed my computer. I resolved that I would give my first technical talk on *this* bug, and that *this* talk would be a reminder to understand my mistakes, to learn from them, and to not shy away from making and/or talking about them.

Added a game loop and related logic to my Scrabble solver. Pitted two identical, not-very-intelligent AIs against one another and witnessed a full Scrabble game play out on my terminal. Felt accomplished.

Chatted with Peter about what the call stack looks like during multiple recursive calls and about different approaches to my Scrabble trie-search problem.

Drew a bunch of things on a whiteboard and eventually -- with significant help from Arun and Robert -- worked out a function that describes the growth of memory expenditure over the execution of my trie search function. Unsurprisingly, the growth is terrifying.

Gave a Thursday presentation on my big little bug, entitled "Death by Scrabble, or "how I crashed my computer with a recursive bug and you can, too!" It went (in my humble opinion) quite well and I received some really positive feedback.

Stopped being restless and settled on Rust. Watched some great introductory videos on [intorust.com](http://intorust.com/). Next goal (as I continue to add score optimization to my Scrabble solver): learn Rust and (possibly? probably?) build a compiler for [Pyth](https://pyth.readthedocs.io/en/latest/), a concise and statically-typed language based on Python. I am mostly excited and only slightly nervous about wading into the great unknown of compilers and assembly. Hooray!
