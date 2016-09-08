---
layout: post
title: Minimalistic blog using Jekyll, Docker and Github
tags:
- jekyll
- docker
- github
---

At some point in the career software dev come up with idea to have blog related to software.
In the blog I can share thoughts, experiences and battle stories. 
Sharing battle stories with small group of co-workers and friends can't bit huge internet community of geeks.
So I want blog and write something in it. 
How do I want it to look like? 
How do I want to add content? 
Where do I host it?

There are ton of answers on those questions. Medium, Tumblr, Blogger, Ghost, Facebook, Google+ and etc.
My answers are simple design, adding content in the most simple way and hosting for free. All of this plus some geekness.

Probably most simple way is writting blog post in text file and host this [TXT](/index.txt) file on some free CDN like [Github Pages](https://pages.github.com/).
Reading TXT file on the web isn't so interesting, espesially in 21th century. So you will need at least some design to entertain readers with fancy text alignment, pictures, media embeddes, fonts and links to other articles.
Ok. You can host simple HTML file with all of this but again you need some design, styles. Styling articles in HTML/CSS takes time but there is simpler approach.
You can write text similar to TXT format but it will be beatifully formatted for reading. Sounds good. What is this?
This is Markdown markup plus tools that allow to format it to HTML with commands and upload it to hosting with another command.

My toolset for blogging include:
 - [Github](https://github.com) and free [Github Pages](https://pages.github.com/) hosting
 - [Git](https://git-scm.com/)
 - [Ruby](https://www.ruby-lang.org/ru/) and Ruby Gems
 - [Jekyll blogging engine](https://jekyllrb.com/)
 - [Docker](https://docker.com)

 Let's discuss in details how to setup all of this.

Sounds interesting?
Stay tuned