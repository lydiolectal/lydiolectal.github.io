---
layout:  post
title:  "Week 2: Time Flies Like an Arrow, Fruit Flies Like a Banana"
date:  2018-04-15 23:01:11 -0500
categories: rc
---

For an explanation of what time flies are, see [this lovely blog post](https://allthingslinguistic.com/post/51834369484/structural-ambiguity-illustrations-from).

Strange but true pedagogical linguistics examples aside, this week truly has flown right by. I think this perception is in large part due to the fact that this space has begun to feel like a home. "Home" can connote a number of things; here, I mean to say that RC feels like a place where I and the identities and experiences I contain are welcome, accepted, and -- most refreshingly of all -- utterly unremarkable.

# Monday - Wednesday

Started debugging an old C tokenizer for Racket

Realized that debugging was not the way I wanted to spend the majority of my time at RC

Started writing a tokenizer in Python Racket

Learned about regular expressions and used them for the first time in my tokenizer! Regular expressions are a way of representing a pattern of characters, which can then be used to perform searches on strings. For instance, if I wanted to find all continuous (i.e., unbroken by whitespace) sequences of characters that began with a ' symbol, which is syntactic sugar for [quote](https://docs.racket-lang.org/guide/quote.html) in Racket, I could write this expression:

{% highlight python %}
\# Match: 'Iamaquotedstring!
\# Not a match: 'Iamaquoted string!
"\'\S+"
{% endhighlight %}

The initial escaped ' means the expression starts with '. The \S is shorthand for "all characters that are not whitespace"; the + symbol following \S is used to denote the fact that I want to find sequences of one more more non-whitespace characters.

I used [RegexOne](https://regexone.com/), which I recommend as a way to get started with regular expressions!

Had a new kind of pairing experience with Steven from which I came away with more questions than answers. Learned that sharpening one's questions to make them more tractable is sometimes better than having answers right away.

# Thursday - Sunday

Thursday, I became quite anxious when I considered the scope of a compiler (which was what I had been working towards) and decided it might be good to work up to larger projects by starting on a shorter term project first. Decided on a Scrabble solver / AI.

Met with Sarah to discuss our reading of Programming Language Pragmatics. Concluded that the line between interpretation and compilation is [fuzzy](https://nedbatchelder.com/blog/201803/is_python_interpreted_or_compiled_yes.html) and that the world is complicated. Were not particularly surprised by this conclusion. Decided that we will try to write a bit of code in a new programming language every week (!!) to get a taste for how different languages do things.

Paired with Casey on the beginnings of a Scrabble-playing AI. As I was prematurely optimizing, Casey told me that "premature optimization is the root of all evil." Learned how to represent all the words in the English dictionary with a data structure called a [trie](https://en.wikipedia.org/wiki/Trie)!

Learned from Brandon about this weird part of the U.S. called the [Northwest Angle](https://en.wikipedia.org/wiki/Northwest_Angle) and about Test-Driven Development. Not sure which piece of knowledge is more enriching to my life.

Added functionality to my Scrabble AI that searches the trie for all words that match a certain template. Ex: given "aba..." (where . represents any letter), it returns:

{% highlight python %}
['abated', 'abater', 'abates', 'abatis', 'abator', 'abakas', 'abacus', 'abacas', 'abased', 'abaser', 'abases', 'abasia', 'abamps']
{% endhighlight %}
