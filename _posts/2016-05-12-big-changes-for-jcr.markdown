---
layout: post
title:  "Big Changes for JCR in the Works"
date:   2016-05-12 16:22:06 -0400
categories: JSON JCR
published: true
comments: true
---
We published [JCR -06](https://tools.ietf.org/html/draft-newton-json-content-rules-06) back in
March and since we've received a lot of feedback. And that feedback has resulted
in some fairly significant, and unfortunately backwards incompatible, syntax changes -- all for the better.

The big thing to take away from these changes is that valid JSON is now valid
JCR. To some extent this was true with -06, but things like this were not:

{% highlight json %}
[ "a", [ 1, 2, 3 ], "b" ]
{% endhighlight %}

Well, now it is (or at least will be in -07). But in doing this, we've had to
move the repetition syntax to the end of the definitions.  Whereas we use to do this:

{% highlight json %}
[ :"a", [ 3 :integer ], :"b" ]
{% endhighlight %}

repetitions are now preceded with some syntactic sugar, the `@`, and moved to the end:

{% highlight json %}
[ "a", [ integer @3 ], "b" ]
{% endhighlight %}

For a refresher on the concept of [syntactic sugar](https://en.wikipedia.org/wiki/Syntactic_sugar):

> In computer science, syntactic sugar is syntax within a programming language t
> hat is designed to make things easier to read or to express.
> It makes the language "sweeter" for human use: things can be expressed more
> clearly, more concisely, or in an alternative style that some may prefer.

Or in other words, _the computer doesn't need it_. A JCR parser doesn't need the `@`,
but we've added it there so repetitions don't get lost and appear to have a meaning
more obvious than, "look, they forgot a comma".

Syntactic sugar is one of those eye-of-the-beholder things, as I've learned through
this process. And so... we've added more.

As you may recall, in JCR rules can be broken out and referenced by name. An example:

{% highlight json %}
[ "a", ints, "b" ]

ints [ integer @3 ]
{% endhighlight %}

To the casual reader, that might seem confusing. Is `ints` a JCR thing? To make it clearer, we've decided that rule names must be immediately preceded by the `$` character and the `=` character is to be used when naming rules. Thus:


{% highlight json %}
[ "a", $ints, "b" ]

$ints = [ integer @3 ]
{% endhighlight %}

Now those aren't all the changes we are working on, but those are the big ones. More to come...
