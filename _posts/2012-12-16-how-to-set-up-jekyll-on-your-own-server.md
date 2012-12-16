---
layout: post
title: "How to set up Jekyll on your own server?"
description: ""
category: tech
tags: [jekyll]
---
{% include JB/setup %}

Instead of using GitHub page to serve my blog, I would like to use
the server of our department (CSE@CUHK), and serve this
blog under <http://www.cse.cuhk.edu.hk/~qliu/blog>.
The problem is that all the links in Jekyll will be namespaced by
the root `/` of the server. According to the documentation,
I modified the file `_config.yml`:

    production_url : http://www.cse.cuhk.edu.hk/~qliu/blog
    ...
    JB:
      ...
      BASE_PATH : /~qliu/blog
    ...

But it doesn't work!! I tried for hours and finally find that I need
to add `--safe` option by looking at the source code. I think it is
so non-user-friendlly...

Finally, I can build and sync my site by:

    jekyll --no-auto --safe --kramdown && rsync -avz --delete _site/ linux15:www/blog

To preview my site, I use:

    jekyll --server --base-url /~qliu/blog --safe

and access <http://localhost:4000/~qliu/blog>.

Jekyll doesn't use Pandoc... I think _kramdown_ is a good choice among
the several markdown parsers used by Jekyll. The syntax of kramdown is
here: <http://kramdown.rubyforge.org/syntax.html#fenced-code-blocks>.
