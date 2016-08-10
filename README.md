# Life With Alacrity Blog
Migrating the blog Life With Alacrity from hosted typepad to static standalone

## Setting up
### install Hugo
The static site generator used is Hugo  - https://gohugo.io/
Install that on your system using https://github.com/spf13/hugo/releases (current site built with v0.16)
This was not built from source or modified; all the changes are to templates within this repository
### Installing
Checkout this repository and the github.io one into the same directory (that way the transformation scripts run unmodified)
You'll also need a python 2.7 install to run the legacy import scripts.

## Previewing
preview the site by running Hugo locally
```
cd blog
hugo server
```
This will generate the pages in ram and serve on http://localhost:1313/ 
It should also detect changes int he path and regenerate, but if this gets out of sync, stop and restart the process.
You can override the theme if desired with eg 
```hugo server --theme=simple-a```

## Adding a post
Put a markdown file inside ```blog/content/post/``` to create a new post. The posts need a header in yaml (or toml) to specify title, slug tags etc
eg (for one I manually added)
```
---
title: "Smarter Signatures: Experiments in Verifications"
slug: "smarter-signatures"
date: "2016-06-28T17:20:54Z"
---
```
or for one imported from the dumps (see below)
```
---
title: "Defining “Participatory Ecosystem” — Grow the Pie, Not Slice It!"
slug: "defining-participatory-ecosystem-grow-the-pie-not-slice-it"
url: "/2016/04/defining-participatory-ecosystem-grow-the-pie-not-slice-it.html"
tags:
  - "Entrepreneuring"
  - "Security"
  - "Social Software"
  - "Social Web for Social Change #SW4SX"
  - "Web/Tech"
date: "2016-04-05T23:07:58-07:00"
---
```
Then when you rebuild, this will show up on the homepage, in the tags etc.

## Generating
Once you like the new post layout, quit the preview and generate the pages 
```
cd blog
hugo
```

That will build into the github.io directory so you can see diffs in git once built
