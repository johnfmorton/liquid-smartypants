If you have a blog that is built using Jekyll, then it is possible to turn on
smart quotation marks for the *content* of your posts; but doing so will not
turn on smart quotation marks for their *titles*.

This plugin fixes that.

(By the way, this document also explains how to turn on smart quotes for the
*content* of your posts, even though that's not what my plugin does.)

Installation
============

1. `gem install redcarpet`
2. In your Jekyll blog, create a `_plugins` subdirectory, and copy
   `liquid-smartypants.rb` into it.

Usage
=====

Everywhere in your Jekyll site that you had this before:

    {{ page.title }}

Change it to say this instead:

    {{ page.title | smart }}

Obviously it works for any text that is enclosed in `{{ ... | smart }}`, not
just `page.title`.

What about GitHub Pages?
========================

If you are hosted on GitHub Pages, this plugin will be hard to use, because
GitHub Pages runs Jekyll in "safe" mode, which does not allow the use of custom
plugins.  But the following blog post does a good job of explaining a workflow
you could follow.  It involves running Jekyll locally on your own system, and
then pushing the resulting HTML files up to GitHub Pages, rather than the
standard workflow of pushing the Jekyll source files to GitHub Pages and
letting it run Jekyll on the server:

<http://ixti.net/software/2013/01/28/using-jekyll-plugins-on-github-pages.html>

But wait, how do I turn on smart quotes in the *content* of my posts?
=====================================================================

This is built into the `redcarpet` markdown processor.  Put this in your
`_config.yml`:

    markdown: redcarpet
    redcarpet:
      extension: ["smart"]
