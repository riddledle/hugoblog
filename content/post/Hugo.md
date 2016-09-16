+++
date = "2016-09-10T17:28:05+08:00"
description = "Using hugo "
title = "Hugo"

+++

There're many alternatives for a blog's generator,such as wordpress,hexo,hugo...They generate static site for the user to deploy.I have typically used three types of those generators: hexo,viki,hugo.

# [Hugo](https://gohugo.io/)
Hugo is a static site generator written in Go.
Here is its repo on github:[hugo](https://github.com/spf13/hugo/)

This blog you are visiting is deployed on github pages thus if you want to deploy a blog like this, an assumption is that you are equipped with `Git`, `nodejs`,a github account,along with some knowledge of basic operations on linux.

The [tutorials](https://gohugo.io/overview/quickstart/) on hugo's official site is very detailed and easy to read.

```

.
|-- archetypes
|-- config.toml
|-- content
|-- data
|-- layouts
`-- static

5 directories, 1 file

```

>The basic file tree of a hugo directory

I built up my site through this tutorial very fluently,_the only problem i encountered was on my way to deploy it on github pages_.

Initially i created a new repo under the same account which dominates my lyrics collection site,and they conflicted!It turned out that the `pre` and `next` link on my blog would led to a wrong way to my default repo on github.

I solved this little tricky question using some kind of "brute force" strategy,i simply:

- Register a new github account
- Create a new repo for the blog
- Modified the `pagination.html` file under `themes/layouts/partials` 

    1. Reference to the official site:[Build the navigation](https://gohugo.io/extras/pagination#build-the-navigation)
  ![](http://o7o0hlenq.bkt.clouddn.com/95BE7874-0B18-438E-B093-42B24C69FE16.png)
    
    * Here i noticed:
  ![](http://o7o0hlenq.bkt.clouddn.com/9173F112-E758-4B22-BAA8-F781C6282ED5.png)
  
  * So the problem is caught!The pre and next links will locate the pages under the home directory,which caused the conflict.
  I tried:
  ![](http://o7o0hlenq.bkt.clouddn.com/D3AFC6BE-9F64-43B1-A56E-0840B3098E20.png)
  which can successfully solve the problem but seems a little ugly...
  
# Pros and cons
- The theme i'm using parently is [cactus](http://themes.gohugo.io/cactus/).The reason i abort hexo for hugo is that i used to think _hugo's theme is prettier_.

- hugo has no default theme thus you can use your first theme directly without changing the config file.
- hugo has a `live view` function so you can watch your changes without refresh the site.
- hugo doesn't have an integrated `deploy` function while hexo has the `hexo d -g` command to deploy
    the site conveniently.In hugo,you have to use the common git operations to deploy your site.

  
  
