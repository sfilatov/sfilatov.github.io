---
layout: post
title: Minimalistic blog using Jekyll, Docker and Github
tags:
- jekyll
- docker
- github
---

At some point in the career software dev comes up with idea to share his knowledge in the blog.
In the blog you can share thoughts, experiences, battle stories. 

So you want to have blog. 
How it should look like? 
How add content? 
Where to host?

There are ton of answers on those questions and ready solutions. Medium, Tumblr, Blogger, Ghost, Facebook, Google+ and etc.
My answers are simple design, adding content in the most simple way and hosting for free. All of this plus some geekness.

Probably most simple way is writting blog post in text file and host this [TXT](/index.txt) file on some free CDN like [Github Pages](https://pages.github.com/).
Reading TXT file is boring, espesially in 21th century. 
So you need at least simple design to entertain readers with fancy text alignment, pictures, media embeddes, fonts and links to other articles.
Host simple HTML file but styling articles in HTML/CSS takes time.
Write text similar to TXT format but auto-magically formatted for reading. Sounds good. What is this?
This is Markdown markup plus tools that allow to format it to HTML with commands and upload it to hosting with another command!

## Suggested toolset for blogging includes:
 * [Github](https://github.com) and [Github Pages](https://pages.github.com/)
 * [Git](https://git-scm.com/)
 * [Jekyll](https://jekyllrb.com/) static blogging engine based on [Ruby](https://www.ruby-lang.org/ru/) language
 * [Docker](https://docker.com)

## Setup instruction

1. Install fresh Git version from [https://git-scm.com/](https://git-scm.com/). 
2. You need Github account. Read short step-by-step guide on [Github Pages](https://pages.github.com/) how to create you blog repo. At the end you will have ```username.github.io``` git repo locally on disk.
3. [Download and install Docker](https://www.docker.com/products/docker).
4. Using docker start container with jekyll, install and generate blog in ```username.github.io``` folder.
``` bash
cd username.github.io
docker run --rm --label=jekyll --volume="$(pwd)":/srv/jekyll \
 -it jekyll/jekyll:pages jekyll new /srv/jekyll
chown -hR $USER:$GROUP .
```
5. Create ```docker-compose.yml``` that allow to start jekyll server in docker on ```localhost:4000``` address.
``` yml
jekyll:
    image: jekyll/jekyll:pages
    command: jekyll serve --watch --incremental
    ports:
        - 4000:4000
    volumes:
        - .:/srv/jekyll
```
6. Run using one command 
```
docker-compose up
``` 
7. Add new post file in directory ```_posts``` with markdown extension ```2016-09-16-post-title-here.md```
8. Write you post using [Markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
8. Check it in the browser ```http://localhost:4000```
9. Commit your blog to git repo 
```
git add --all . 
git commit -m "my first blog post"
```
10. Push your changes to Github Pages 
```
git push origin
```

Basically that's all. 

For advanced Jekyll usage read docs [https://jekyllrb.com/docs/home/](https://jekyllrb.com/docs/home/)
