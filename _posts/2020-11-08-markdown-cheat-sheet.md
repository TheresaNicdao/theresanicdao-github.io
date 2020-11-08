---
title: "Markdown Cheat Sheet"
date: "2020-11-08"
tag:
- markdown
- cheat sheet
---

## Headings[^1]

**Syntax:**
```
# Heading 1

## Heading 2

### Heading 3
```

**Rendered Output:**

# Heading 1
## Heading 2
### Heading 3

***

## Paragraphs[^1]

**Syntax:**
```
This is the first paragraph.

This is the second paragprah.
```

**Rendered Output:**

This is the first paragraph.

This is the second paragraph.

***

## Bold[^1]

**Syntax:**
```
**bolded text**

__bolded text too__
```

**Rendered Output:**

**bolded text**

__bolded text too__

***

## Italic[^1]

**Syntax:**
```
*italicized text*

_italicized text too_
```

**Rendered Output:**

*italicized text*

_italicized text too_

***

## Bold and Italic[^1]

**Syntax:**
```
***bold and italicized text***

___bold and italicized text too___
```

**Rendered Output:**

***bold and italicized text***

___bold and italicized text too___

***

## Strikethrough[^extended]

**Syntax:**
```
~~strikethough text~~
```

**Rendered Output:**

~~strikethough text~~

***

## Blockquote[^1]

**Syntax:**
```
> This is a blockquote
>> This is a nested blockquote
> **This is a blockquote with other element**
```

**Rendered Output:**

> This is a blockquote
>> This is a nested blockquote
>
> **This is a blockquote with other element**

***

## List[^1]

**Syntax:**
```
1. ordered list 1
2. ordered list 2

- unordered list 1
- unordered list 2

+ unordered list 1
+ unordered list 2

* unordered list 1
* unordered list 2

1. ordered list
  - unordered sublist
```

**Rendered Output:**

1. ordered list 1
2. ordered list 2

- unordered list 1
- unordered list 2

+ unordered list 1
+ unordered list 2

* unordered list 1
* unordered list 2

1. ordered list
  - unordered sublist

***

## Definition List[^extended]

**Syntax:**
```
References
: [Markdown Guide Basic Syntax](https://www.markdownguide.org/basic-syntax/)
: [Markdown Guide Extended Syntax](https://www.markdownguide.org/extended-syntax/)
```

**Rendered Output:**

References
: [Markdown Guide Basic Syntax](https://www.markdownguide.org/basic-syntax/)
: [Markdown Guide Extended Syntax](https://www.markdownguide.org/extended-syntax/)

***

## Code[^1]

**Syntax:**
```
`This is a code`
```

**Rendered Output:**

`This is a code`

***

## Fenced Code Block[^extended]

**Syntax:**

Wrap the code in three backticks (`) or tilde (~)

**Rendered Output:**

```
This is a code block
```

***

## Link[^1]

**Syntax:**
```
[Markdown Basic Syntax](https://www.markdownguide.org/basic-syntax/)
```

**Rendered Output:**

[Markdown Basic Syntax](https://www.markdownguide.org/basic-syntax/)

***

## URLs and Email Address[^1]

**Syntax:**
```
<mtsnicdao@gmail.com>
```

**Rendered Output:**

<mtsnicdao@gmail.com>

***

## Image[^1]

**Syntax:**
```
![Sample Image](/assets/images/cute-dog.jpg)
```

**Rendered Output:**

![Sample Image](/assets/images/cute-dog.jpg)

***

## Task List[^extended]

**Syntax:**
```
- [x] task 1
- [ ] task 2
```

**Rendered Output:**

- [x] task 1
- [ ] task 2

***

## Emoji Shortcut[^extended]

**Syntax:**
```
:joy:
```

**Rendered Output:**

:joy:

***

## Table[^extended]

**Syntax:**
```
| Column 1 | Column 2 |
| -------- | -------- |
| Row 1a   | Row 1b   |
| Row 2a   | Row 2b   |
```


**Rendered Output:**

| Column 1 | Column 2 |
| -------- | -------- |
| Row 1a   | Row 1b   |
| Row 2a   | Row 2b   |

***

## Footnote[^extended]

**Syntax:**
```
Here's a simple footnote,[^1] and here's a longer one.[^extended]

[^1]: This is a basic syntax.

[^extended]: This is an extended syntax.

    It means it might not be supported by the lightweight markup language your application is using.
```

**Rendered Output:**

Here's a simple footnote,[^1] and here's a longer one.[^extended]

[^1]: This is a basic syntax.

[^extended]: This is an extended syntax.

    It means it might not be supported by the lightweight markup language your application is using.