---
title: Blog Launch!
tags:
  - meta
  - github
  - structure
---
> It's alive!

This is the very first post of this blog. And since I got nothing else to talk about right now, I'm gonna talk about how it's built.

## Jekyll and GitHub Pages

I didn't want to put much thoughts into the building and infrastructure of the blog, I just wanted to focus on what I write, not really how my content is processed.

Since I already was a GitHub user, I figured I'd try hosting something on [GitHub Pages](https://pages.github.com/), since it was free.

Turns out Pages uses [Jekyll](https://jekyllrb.com) to build your static sites.

For a simple blog like this one, a simple generator like Jekyll works really fine. In fact, Jekyll can handle a more complicated structure, with single collections, so this weblog may get feature updates here and now if needed.

So I got a Jekyll site, but I really didn't want to do all the layouting and styling myself just for a blog. So I looked, and found [Beautiful Jekyll](http://deanattali.com/beautiful-jekyll/), which is an easy-to-setup template for jekyll blogs.

Forking the repo, changing what needed change (like branding images, author info, etc), and I was ready to blog.

But I needed a little tweak.

## Separation of concerns

### What?

The commit that added this post to the blog is not a commit on `facelesspanda/facelesspanda.github.io`, but a commit on `facelesspanda/blog-posts`.

### Why?

I like separation of concerns and separation of contexts. When I work on a blog post, I want to work on a blog post, not on a file inside a blog site. When I want to work on the site, I want to work on the site, without touching my posts.

So I actually separated those concerns, in two separated repositories. `blog-posts` contains only markdown files, with a bit of YAML front-matter, which is compatible with many generators. So whenever I want to change how my blog is generated, I don't have to modify my content.

But how did I tell the blog repo where and how to get the content?

### How?

[Git Submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules).

A way to manage repositories inside repositories.

Here's my (ideal) blogging workflow:
1.  Creating a new topical branch in `blog-posts` to work on the post.
2.  Write the post, correct any typos, restructure until I'm satisfied. All while committing as often as I can (if it takes more than one session, push too, so that I can go back at it from anywhere).
3.  Merge to `blog-posts/master`.
4.  Update the submodule ref in the blog repo.

The only downside of this whole thing is the fourth point: *"Update the submodule ref in the blog repo"*. I said I wanted to separate the concerns, right? Well, I separated the concerns, so when working on my blog posts, I work **only** on my blog posts, and not on my site.

The way git submodules work, is when you add a submodule to a repo, you add a reference to a commit of another repo. Notice that I said "commit" and not "branch": submodules are designed to avoid any unwanted breaking changes. If you add a third-party library dependency as a submodule, and their master updates with breaking changes, well you don't want an automatic update that would break your whole software, would you? (Don't you agree, [Windows 10](http://www.howtogeek.com/223068/what-you-need-to-know-about-windows-update-on-windows-10/)?)

So it's a consistency necessity to, if I want to separate concerns, separate them completely. First I work on my blog posts, and when one is finished, it ends up on the `master` branch, so I can safely switch concerns, and "update the blog posts" from the blog itself.

So even if it's not automatic (for now. Maybe I'll find a way to automatically update the ref when there's a new commit to the posts's `master`), it's a workflow that is consistent in its separation of concerns. The extra step is not that big of a deal.

When working on a simple blog like that, it may be overkill to setup a submodule. But if I ever get collaborators, co-bloggers, or something like that, I would be able to just scale the repo to fetch more blog posts from more submodules.

---
Note: I'm writing directly on `blog-posts/master` right now. Hell, I might do that often, for simple posts that are not tutorials or other complex articles. The idea is : **`master` is always stable**. As long as that's true, I don't really care how disciplined I am with how I manage my own blog.
