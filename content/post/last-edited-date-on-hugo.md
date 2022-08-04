---
title: "How to Add a Last Edited Date on Hugo"
date: 2022-08-03T21:02:24-04:00
draft: false
image: ""
tags: [Hugo]
categories: [How to Hugo]
showtoc: true
---

# Introduction

I frequently start a post and edit them as I learn. As such, my posts are constantly updated but the post date stays in the past. Plus, if I learn something in the future, I want to revisit my old posts and add relevant information as needed. The thing is that I don't want to worry about manually changing the "Last Edited Date"; rather, I want it done automatically. Fortunately, there is a way to do exactly that on Hugo! Let's learn how to implement a last edited date, so that we can show how recent a post really is. 

# Hugo's Git Integration

Hugo can natively retrieve information from git, and it's very easy to enable it. To do so, you simply need to add one line in your config file.

**config.toml**

```toml
enableGitInfo = true
```

> **Hint:** if your config file is a yaml file, you can look up an online tool to easily convert from toml syntax to yaml syntax. Search "toml to yaml" on Google and pick your favorite tool.

This enables the [.GitInfo object](https://gohugo.io/variables/git/#the-gitinfo-object) on Hugo, as well as .Lastmod. For the purpose of this post, we will focus on `lastmod`. Hugo will now automatically update `lastmod` based on the last time each post was updated based on the git commit timestamp. 

# Integrating Lastmod with Hugo Theme

We now have `lastmod`, but not all themes support the variable. I use [PaperMod](https://github.com/adityatelange/hugo-PaperMod) as my theme, which does not natively support last mod. To fix this, we need to override the theme's template.

First, we will copy `layouts/partials/post_meta.html` from PaperMod to our own layouts folder. This will let Hugo know to use our own layout file instead of the theme's.

Next, we will modify the file we just copied so that we can display last modified date on each post. Please note that the codes shown below are taken and adapted from [Use Lastmod with Papermod](https://www.jacksonlucky.net/posts/use-lastmod-with-papermod/) by Jackson Lucky.

Add this code block at the top of `post_meta.html` to add variables. The variables will be used later to compare whether both dates are the same or not.
```go
{{ $date := .Date.Format "02.01.2006" }}
{{ $lastmod := .Lastmod.Format "02.01.2006" }}
```

Add this code block after `{{- if not .Date.IsZero -}}` block ends. This will show the last modified date only if the last modified date is different from the original publish date.
```go
{{- if ne $lastmod $date -}}
{{- $scratch.Add "meta" (slice (printf "<span title='%s'>Last Modified %s</span>" (.Lastmod) (.Lastmod | time.Format (default "January 2, 2006" site.Params.DateFormat)))) }}
{{- end }}
```

Now each post should automatically show the last modified date, if it differs from the original publish date. Also, if you ever need to display another post metadata, you can take similar steps to display whatever post metadata you want for your blog!

# Learning Sources

[Add a Last Edited Date to Posts](https://makewithhugo.com/add-a-last-edited-date/) by Edd Turtle

[Use Lastmod with Papermod](https://www.jacksonlucky.net/posts/use-lastmod-with-papermod/) by Jackson Lucky
