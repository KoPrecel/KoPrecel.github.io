---
title: "Learning How To Make Hugo Posts with Markdown"
date: 2022-07-13T18:06:02-04:00
draft: false
image: ""
tags: [Hugo, Markdown]
categories: [How to Hugo]
showtoc: true
---

# Introduction

I created this blog to start journaling my programming experiences and keep a record of what I learn along the way. After a few hours of struggling with GitHub Pages and Hugo, this blog successfully went live! That being said, there is still a lot of work to do. The very first thing I need to work on is to learn how to make a post, so that I can write about things I learn in the future. At the same time, I want to start generating contents for this blog as well. This post is about hitting two birds with one stone: I'm learning Markdown by making this post, and I'm also making a guide out of it.

This guide is specific to Hugo and Goldmark Markdown processor, so you might find some inaccuracies if you're not using these technologies.

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

## Strikethrough

You can strikethrough a text by wrapping it with \~\~ around the text. Here is an example:
| Markdown                                 | Output                               |
| ---------------------------------------- | ------------------------------------ |
| I can't believe it's not \~\~butter\~\~! | I can't believe it's not ~~butter~~! |

## Code

You can denote a text as code by wrapping it with \` around the text. If the text contains \` within, you can use `` instead to denote the text as code. Here is an example:

| Markdown                     | Output                  |
| ---------------------------- | ----------------------- |
| \`print("Hello World!")\`    | `print("Hello World!")` |
| \`\`denote code with \`!\`\` | ``denote code with `!`` |

## Link

You can hyperlink a text by wrapping the text in square brackets followed by the link wrapped in parentheses. Here is an example:

| Markdown                                           | Output                                            |
| -------------------------------------------------- | ------------------------------------------------- |
| \[Min's Learning Den](https://koprecel.github.io/) | [Min's Learning Den](https://koprecel.github.io/) |

---

# Blockquotes

Did you notice how the hint looks different than regular paragraph in the previous section? It's called a blockquote and it's created by adding a \> at the beginning of a text.

**Markdown:**

`> Just like this!`

**Rendition:**

> Just like this!

## Multiline Blockquotes

You can also use blockquote with multiple lines by adding \> on the blank lines.

**Markdown:**
```markdown
> Blockquotes are
>
> really cool!
```

**Rendition:**
> Blockquotes are
>
> really cool!

## Nesting Blockquotes

You can also nest blockquotes by adding another \>.

**Markdown:**
```markdown
> blockquote level 1
> 
>> blockquote level 2
>
> back to level 1!
```

**Rendition:**
> blockquote level 1
> 
>> blockquote level 2
>
> back to level 1!

---

# Lists

## Ordered List

You can make an ordered list by adding a number and a period at the beginning of the line. You can also nest another list by indenting!

**Markdown:**
```markdown
1. one step to the left
2. one step to the back
3. one hop
4. stomp
    1. right foot
    2. left foot
5. cha cha real smooth
```

**Rendition:**
1. one step to the left
2. one step to the back
3. one hop
4. stomp
    1. right foot
    2. left foot
5. cha cha real smooth

## Unordered List

You can make an unordered list by adding one of the following symbols to the beginning of the line: -, *, +

**Markdown:**
```markdown
* apple
- banana
+ peach
```

**Rendition:**
* apple
- banana
+ peach

---

# Fenced Code Block

When you want to have more than one line of text as code, you can use fenced code block by starting a paragraph with ```.

You can also denote which language you are using next to the ``` to highlight the syntax accordingly.

**Markdown:**
~~~markdown
```py
if bank_balance >= tuition:
    student.attend = true
else:
    student.attend = false
    student.work()
```
~~~

**Rendition:**
```py
if money >= tuition:
    student.attend = true
else:
    student.attend = false
    student.work()
```

---

# Table

You can use pipes (|) and three or more hyphens (---) in a tabular shape to create a table.

You can align the text in each column by adding a colon (:) to left, right, or on both sides of the header hyphens.

**Markdown:**
```markdown
| Normal | Left Align | Center Align | Right Align |
| ------ | :--------- | :----------: | ----------: |
| one    | two        | three        | four        |
| five   | six        | seven        | eight       |
```

**Rendition:**
| Normal | Left Align | Center Align | Right Align |
| ------ | :--------- | :----------: | ----------: |
| one    | two        | three        | four        |
| five   | six        | seven        | eight       |

You can also [stylize text](#stylizing-text) within table!

# Images

You can insert an image by using a similar syntax to [link](#link), but with an exclamation mark at the very front. To be more explicit, you can insert an image by starting with an exclamation point, then wrapping the alternative text in square brackets, followed by the link to image wrapped in parentheses.

**Markdown:**
```markdown
![Say hi to my feline son, Babo :)](/images/babo.png)
```

**Rendition:**
![Say hi to my feline son, Babo :)](/images/babo.png)

# Learning Sources

[Hugo Markdown Reference](https://www.markdownguide.org/tools/hugo/)
