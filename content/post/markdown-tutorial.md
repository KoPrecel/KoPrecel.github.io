---
title: "Learning How To Make Hugo Posts with Markdown"
date: 2022-07-13T18:06:02-04:00
draft: false
image: ""
tags: [hugo, markdown]
categories: [learning]
---

# Introduction

I created this blog to start journaling my programming experiences and keep a record of what I learn along the way. After a few hours of struggling with GitHub Pages and Hugo, this blog successfully went live! That being said, there is still a lot of work to do. The very first thing I need to work on is to learn how to make a post, so that I can write about things I learn in the future. At the same time, I want to start generating contents for this blog as well. This post is about hitting two birds with one stone: I'm learning Markdown by making this post, and I'm also making a guide out of it.

This guide is specific to Hugo and Goldmark Markdown processor, so you might find some inaccuracies if you're not using these technologies.

I learned Markdown and created this post by reading [Hugo Markdown Reference](https://www.markdownguide.org/tools/hugo/) and I encourage you to check it out as well!

---

# Headings

Headings can be created by using \#. The number of \#'s determine the Heading's level. Here is an example:

| Markdown            | Output                   |
| ------------------- | ------------------------ |
| # Heading level 1   | <h1>Heading level 1</h1> |
| ## Heading level 2  | <h2>Heading level 2</h2> |
| ### Heading level 3 | <h3>Heading level 3</h3> |

Best practices for Headings is to have blank lines before and after.

---

# Stylizing Text

## Bold

You can bolden a text by wrapping it with either ** or __ around the text. Here is an example:

| Markdown                       | Output                     |
| ------------------------------ | -------------------------- |
| Wow, what a \*\*bold\*\* move! | Wow, what a **bold** move! |
| Wow, what a \_\_bold\_\_ move! | Wow, what a __bold__ move! |

## Italic

You can italicize a text by wrapping it with either * or _ around the text. Here is an example:

| Markdown                                 | Output                                 |
| ---------------------------------------- | -------------------------------------- |
| A \*duck\* walked up to a lemonade stand | A *duck* walked up to a lemonade stand |
| A \_duck\_ walked up to a lemonade stand | A _duck_ walked up to a lemonade stand |

> **Hint:** You can bolden and italicize at the same time by using \*\*\* or \_\_\_

Some Markdown applications don't handle underscores the same way, so it is the best to use asterisks for bold and italic.

---

# Blockquotes

Did you notice how the hint looks different than regular paragraph in the previous section? It's called a blockquote and it's created by adding a \> at the beginning of a text.


`> Just like this!`
> Just like this!

## Multiline Blockquotes

You can also use blockquote with multiple lines by adding \> on the blank lines.

```markdown
> Blockquotes are
>
> really cool!
```

> Blockquotes are
>
> really cool!

## Nesting Blockquotes

You can also nest blockquotes by adding another \>.

```markdown
> blockquote level 1
> 
>> blockquote level 2
>
> back to level 1!
```

> blockquote level 1
> 
>> blockquote level 2
>
> back to level 1!
