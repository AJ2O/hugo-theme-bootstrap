+++
# type = "docs"
title = "Performance"
date = 2022-07-23T18:30:48+08:00
# description = "" # Used by description meta tag, summary will be used instead if not set or empty.
featured = false
draft = false
comment = true
toc = true
reward = true
pinned = false
carousel = false
categories = ["Performance"]
tags = ["minify", "gzip"]
series = ["Docs"]
images = []
+++

In this article we are going to talk about how to improve the performance of your sites.

<!--more-->

The easiest way to improve performance is to reduce the file size for transferring faster.

## Environment

The theme relies on the `production` environment to minify the JavaScript and CSS assets.

| Default environment | Value |
|---|---|
| `hugo` | `production` |
| `hugo server` | `development` |

In general, you don't need to make any changes unless you plan to use the `hugo server` in a `production` environment.
You can change the default environment with `-e` flag.

## HTML Minification

You should use `hugo --minify` to minify the final HTML in production environment.

## Compression

Compression is not the same thing of minification, it compresses files with some algorithm (such as `gzip`), and then transfer to clients, the clients then decompress before parsing those files.
This is the configuration of the web server. Please refer to the relevant documents according to your own situation.