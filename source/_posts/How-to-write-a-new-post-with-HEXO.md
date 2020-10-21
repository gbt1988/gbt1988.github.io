---
title: How to write a new post with HEXO
date: 2020-10-20 16:24:27
tags:
categories:
---

First step:
1. `Hexo New` to create a new post
2. wirte the content in the .md file
3. You should put the IMG files into the corresponding file withe a same name and use `{% asset_img learn.jpg learn}` to ref the picture.
4. After editing the file ,you should save it ,and run 'hexo generate' to gererate the static files.
5. Then you can use hexo deploy to deploy your blog.

Here is some of the Hexo commands,there's still an abbrevated version of these commands.

```
Commands:
  clean     Remove generated files and cache.
  config    Get or set configurations.
  deploy    Deploy your website.
  generate  Generate static files.
  help      Get help on a command.
  init      Create a new Hexo folder.
  list      List the information of the site
  migrate   Migrate your site from other system to Hexo.
  new       Create a new post.
  publish   Moves a draft post from _drafts to _posts folder.
  render    Render files with renderer plugins.
  server    Start the server.
  version   Display version information.

Global Options:
  --config  Specify config file instead of using _config.yml
  --cwd     Specify the CWD
  --debug   Display all verbose messages in the terminal
  --draft   Display draft posts
  --safe    Disable all plugins and scripts
  --silent  Hide output on console
```
