---
redirect_from:
  /blog/2008/03/today-i-attended-barcamp-nyc3-at.html
---

Today I attended BarCamp NYC3 at Polytechnic University. It was a lot of fun and there were some interesting presentations.

[![BarCamp3 Logo](/images/BarCampNYC3.jpg)](http://barcamp.org/w/page/401246/BarCampNYC3)

I gave a presentation on Website Security. The following attacks were covered:

* SQL Injection
* Shell Expansion
* Cross-site scripting (XSS) attacks
* Persistent XSS
* Non-persistent XSS (reflective)
* DOM based XSS

We spoke about in which scenarios these can happen and how you would prevent them. The main point is that you should always validate input from untrusted sources.
When working with database queries, SQL placeholders should be used if it is at all possible (this generally also increases database efficiency).
In addition, input validation needs to be done on the client side if variables are parsed and processed by Javascript that can be under control of a different website. This would include Javascript that parses the current URL, the referer or the location. If this isn't done, the webpage can be susceptible to a DOM XSS attack. Check this page out for more details.

##As for the sessions that I attended:

[Aviary](https://www.aviary.com/) has a really cool web app for image editing(Phoenix). It is reminiscent of Gimp, although perhaps it looks more like PhotoShop?
Then they have another app, called Peacock which they call a "Pattern Maker". You can create images by linking functional blocks together that generate and modify the image as it passes through each block. It really looks unique and I have never seen something like it that used for image generation. I think that this will be a great hit.

In a presentation given by Justin from [http://www.justinday.com/](http://www.justinday.com/), he demonstrated a program that he had written that implements a genetic algorithm. His basic program was modeled after the Soda Constructor. He has these little autonoma or robots that attempt to walk across the screen. They get mutated and selected for the most efficient walker. There is a link on the blog to this page where you can download an see the source code.
