+++
image = "img/hugo/hugo.jpg"
showonlyimage = true
draft = false
date = 2017-10-14T13:07:01+11:00
title = "How to build hugo static blog on github with custom domain"
weight = 0
tags = [ "Development", "Blogging" ]
categories = [ "Development" ]
series = [ "devops" ]
slug = "build_hugo_blog"
+++

Tools:
    github, git, hugo, amazon route 53, buy your domain via amazon $12 dollar, markdown, vscode

I'v built this blog with hugo + theme called 'hugo-creative-portfolio-theme'
There are heaps of theme you can download. So hugo has features:
1. markdown to html
2. local watch to see changes
3. community support for themes etc.
4. written in go not node.js


The process is:
* write blog in markdown format
* generate static change
* add CNAME file for custom domain
* buy domain from amazon, or somewhere, setup there (see image below)
* deploy to github as your 'git page' (setup as imgage below)
* test dns record in yoru local

for future:
you can update any theme, then push to git, git use amazon as dns lookup as to replace
[username].github.io as your default one.

Downside:
---------
git is not good for SEO... I disagree with than, hugo has a boost to generate sitemap.xml and every bit you can control.

once in the deploy folder. You can add anything you like. Hugo won't delete them !!! Thanks

The development circle is slim and quick. I manage to see update in seconds.

Having amazon route 53 as dns has advantage:
1. you can play with s3 static page solution
2. play with cloudfront, get used to aws
3. provide dns alias [powerful] and easy to see changes (<1 mins to propagate)
4. cache dns records with time you decide.

Things need to care:
--------------------
I use `public` folder in version control to push to github. I'v put CNAME file in the root (i'll show your structure below). In my case i rename `public` to `docs` to match github convention. 

[My CNAME file](https://github.com/ilovejs/blog/blob/master/docs/CNAME)

AWS:
----
![](/img/hugo/aws_v2.png)
==> notice I use `ilovejs.github.io` not appending `\blog` !!!

Github repo:
------------
![](/img/hugo/github.png)

Git repo setting for git page:
------------------------------
![](/img/hugo/git_page_setups.png)

Hugo folder structure:
----------------------
![](/img/hugo/hugo.png)

Command to debug network:
-------------------------
Shows type of records (A, SOA, CNAME):
dig www.hurryduckling.com +nostats +nocomments +nocmd
dig blog.hurryduckling.com +nostats +nocomments +nocmd
dig ilovejs.github.io +noall +answer

These can be exercise for you to dig around :)

Also my nice tricks to automate (once you manage to manually publish a page):
`hugo && git add . && git commit -m 'fixes' && git push -u origin master`


Links that helps me:
--------------------
[(very cool to read) Setting Up SSL on AWS CloudFront and S3]

https://bryce.fisher-fleig.org/blog/setting-up-ssl-on-aws-cloudfront-and-s3/


[(CI) Hugo, S3, Travis CI, oh boy!]

http://continuousfailure.com/post/s3_blog/

[Github Official guidline for custom domain]
https://help.github.com/articles/quick-start-setting-up-a-custom-domain/

[(CNAME) Setting up custom domain with Github Pages]
(this is wrong, you should not use A record, otherwise github will send email to you for fixing)
http://abhipandey.com/2015/10/setting-up-custom-domain-with-github-pages/


[Hugo Forum](https://discourse.gohugo.io/t/howto-deploying-hugo-on-s3-and-cloudfront/2800)




