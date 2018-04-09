---
layout:  post
title:  "Week 1: The Teaspoon Under the Waterfall"
date:  2018-04-09 03:42:29 -0500
categories: rc
---

Back in college, I went on a summer research trip to Micronesia to study a language there. A professor on the program commented that being a field linguist is like "holding a spoon under a waterfall." This analogy applies to RC as well; there is so much knowledge that I feel as though I'm furiously scooping up as much as I can. All in all, it's a good problem to have.

# Monday - Wednesday
Met multiple smart and generous RCers in my batch (Spring 2) and the Spring 1 batch that overlaps with the first half of mine.

Spent a lot of time listing the things I want to work on while at RC.

Added code to a Python script that scrapes data from recipe sites.

Learned from Marianne about best practices for virtual environment management. I had been naming all my virtual environments `venv` (very descriptive, I know)! Here's is what you *should* maybe consider doing if you are in a similar position. I'm using venv, Python 3's built-in and lightweight virtual environment module.
{% highlight bash %}
cd
mkdir .virtualenv
{% endhighlight %}
Navigate to your Home directory and create a hidden folder called .virtualenv (the dot makes it hidden!).
{% highlight bash %}
venv -m ~/.virtualenv/souper-duper
{% endhighlight %}
Create a virtual environment with the same name as your project inside .virtualenv. My project is called souper-duper, so I follow the same naming convention for the corresponding virtual environment.
{% highlight bash %}
source ~/.virtualenv/souper-duper/bin/activate
{% endhighlight %}
This makes it easy to remember how to activate (above), because the virtual environment has the same name as your project!

Paired with Casey on writing a Python script to automate testing of my Racket-to-C interpreter. Learned about stdin/stdout/stderr, remapped my Caps Lock key to behave as Ctrl so that commands are easier, and learned that my tokenizer needs some tweaking before it'll work!

Was generally overwhelmed by the number of people and amount of knowledge in my vicinity.

# Thursday - Sunday
Spent most of Thursday onwards getting a cold, being quite tired, and taking full advantage of the various nap spots around RC.

Paired with Sarah on revisiting C code that I had written for my interpreter's tokenizer. Having to explain how things like memory allocation and token labeling worked really helped me solidify my knowledge.

Began to debug the tokenizer.

Wrote yet another Python script, this time for this blog (!) that takes the post name for your new post, creates a new Markdown file with the date and post included in the filename, and populates the YAML with some date and post name metadata. I'm enjoying making these little things that are fun and mildly useful; isn't that part of the joy of programming?
