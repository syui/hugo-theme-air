# AIR theme for hugo

Air is a single-column theme for [Hugo](http://gohugo.io/).
Ported from [Casper theme for Ghost ](https://github.com/TryGhost/Casper), [vjeantet/hugo-theme-casper](https://github.com/vjeantet/hugo-theme-casper)

- github actions

- blog demo : http://syui.github.io/hugo-theme-air

- blog source : https://github.com/syui/hugo-theme-air

![Hugo Air Theme screenshot](https://raw.githubusercontent.com/syui/hugo-theme-air/master/images/screen.gif)

```bash
$ git clone https://github.com/syui/hugo-theme-air

$ cd hugo-theme-air

$ hugo

$ hugo server
---------------------------------
$ curl 127.0.0.1:1313/hugo-theme-air 
```
## Background Image

[https://github.com/syui/hugo-theme-air/blob/master/static/css/screen.css#L1995](https://github.com/syui/hugo-theme-air/blob/master/static/css/screen.css#L1995)

...`slow`

## Features

* [VincentGarreau/particles.js](https://github.com/VincentGarreau/particles.js/)
* Google Analytics (optional)
* Disqus ( can disable comments by content)
* Share buttons on Facebook, Twitter, Google (can disable share by content)
* Big cover image (optional)
* Custom cover by content (optional)
* Tagging
* Pagination
* Menu

# Theme usage and asumptions
* All blog posts are in the ```post``` folder (```content/post```)
* The homepage displays a paginated list of contents from the post Section (other contents may be added to main menu, see bellow)

# Installation

## Installing this theme

    mkdir themes
    cd themes
    git clone https://github.com/syui/hugo-theme-air

## Build your website with this theme

    hugo server -t hugo-theme-air

# Configuration

**config.toml**

``` bash
$ cat config.toml.backup

$ cp config.toml.backup config.toml
```

Example : [config.toml](https://github.com/syui/hugo-theme-air/blob/master/config.toml.backup)

## Multiple authors configuration

In addition to providing data for a single author as shown in the example above, multiple authors
can be configured via data/authors/\*.(yml, toml, json) entries. If the key provided in
.Site.Params.author matched a data/authors/\* entry, it will be used as the default. Overrides
per page can be done by a simple author = other_author_key entry in the front matter. For those
pages where you want to omit the author block completely, a .Params.noauthor entry is also
available.

``` bash
$ hugo new post/foo.md

$ cat content/post/foo.md
```

Example author definition file:


``` yml
name: John Doe
bio: The most uninteresting man in the world.
location: Normal, IL
website: http://example.com

```

Example override author per page file:
``` toml
+++
author = ""
date = "2014-07-11T10:54:24+02:00"
title = ""
...
+++

Contents here

```

## Metadata on each content file, example

``` toml
+++
author = ""
date = "2014-07-11T10:54:24+02:00"
draft = false
title = "dotScale 2014 as a sketch"
slug = "dotscale-2014-as-a-sketch"
tags = ["event","dotScale","sketchnote"]
image = "images/2014/Jul/titledotscale.png"
comments = true     # set false to hide Disqus comments
share = true        # set false to share buttons
menu = ""           # set "main" to add this content to the main menu
+++

Contents here
```

## Create new content based with default metadata from this theme
You can easyly create a new content with all metadatas used by this theme, using this command 
```
hugo new -t hugo-theme-air post/my-post.md
```
## Hosting for GitHub Pages

```bash
# build
$ hugo 

$ cd public

# preview
$ jekyll server
$ rm -rf _site

# make repository
$ git init
$ git remote add origin $url
$ git add .
$ git commit -m "first commit"
$ git push -u origin master

# push branch:gh-pages
$ git checkout -b gh-pages
$ git commit -m "open pages"
$ git push -u origin gh-pages

# open
$ curl user.github.io/repository
```

## change logo

Replace `static/images/user.png` with myfile.

Please close the browser and rerun hugo server.

point :`BaseUrl`, `authorwebsite` last slash `/`

```toml
BaseUrl= "https://localhost/"

[params]
  authorwebsite = "https://localhost"
  logo = "images/user.png"
```

## content title sort

rewrite `layout/index.html`

```html
{{ range $index, $page := $paginator.Pages }}
  {{ .Render "li" }}
{{ end }}
```

```html
{{ range .Site.RegularPages.ByTitle }}
  {{ .Render "li"}}
{{ end }}
```

# Contact me

:beetle: open an issue in github

:bird: [https://twitter.com/syui__](https://twitter.com/syui__)

