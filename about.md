---
layout: about
title: About
permalink: /about/
---

Welcome to **_morethanabitoff_**. (That's "More Than A Bit Off") My name is Andrew Newton, but my friends, my family,
my boss, his boss, and just about anybody who knows me just call me "Andy".

I work in the tech sector, much of my experience being in the niche of Internet infrastructure. I'm not a router geek or a DNS nerd (though I know a good bit about both), but a software development / applications guy dealing with those services at the "core of the Internet" that keep everything glued together.

## JSON Content Rules

[Pete Cordell](https://github.com/codalogic) and I are working on Data Definition Language (DDL) for JSON: [JSON Content Rules](http://codalogic.github.io/jcr/) (JCR). It has a syntax similar to JSON, but takes a lot of cues from ABNF and Relax NG:

{% highlight json %}
{ image }

 image = "Image" {
     width,
     height,
     "Title" : string,
     thumbnail,
     "IDs" [ * : integer ]
 }

 width = "Width" width_v
 height = "Height" height_v

 width_v = : 0..1280
 height_v = : 0..1024

 thumbnail = "Thumbnail" {
     width, height, "Url" : uri
 }
{% endhighlight %}

Our Internet Drafts are here:

* [JSON Content Rules](https://tools.ietf.org/html/draft-newton-json-content-rules-06)
* [JCR Coconstraints](https://tools.ietf.org/html/draft-cordell-jcr-co-constraints-00)

And, of course, there is code! I've got an open source [JCR validator](https://github.com/arineng/jcrvalidator) on GitHub.

## Registration Data Access Protocol

The Registration Data Access Protocol (RDAP) is the IETF's replacement for Whois. It is a JSON-based, RESTful protocol. Along with Scott Hollenbeck from Verisign, I am one of the original authors of the specifications.

I have a short article on the Team ARIN blog about it (["Registry Data Access Protocol (RDAP): A Common Whois System"](http://teamarin.net/2015/06/22/registry-data-access-protocol-rdap-a-common-whois-system/)) and another article discussing RDAP bootstrapping (["How I Learned to Stop Worrying and Love the New Whois: RDAP"](http://teamarin.net/2016/02/11/how-i-learned-to-stop-worrying-and-love-the-new-whois-rdap/))

Even better than articles, there is code! [NicInfo](https://github.com/arineng/nicinfo) is a command-line, RDAP client with built-in caching, etc... And the [RDAP Bootstrap Server](https://github.com/arineng/rdap_bootstrap_server) is a small, no-database, Java-based RDAP server designed to help RDAP clients side-step the bootstrapping process with a simple RDAP query.

## Other

And I've done other stuff... from playing with LDAP to having it out with billing systems. Once upon a time I was a Windows programmer, and chances are good if you live in North America you have been in a building with an automation system running some of my code.

Outside of tech, I'm into strength training and power lifting, self-defense and martial arts (I hold a black belt rank in Judo). I love searching out new music (check out [a music blog](https://tuneodaday.wordpress.com/) I run with a friend of mine), and I am a _very_ amateur [photographer](http://anewton.smugmug.com).
