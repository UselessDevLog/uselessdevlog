---
layout: post
title: New Section For Style 
description: New section for style, now with cookies and milk
date:   2016-07-25 19:44:10 +0200
author: Gio-

comments: true
categories: article
image: coffee.jpg
tags: cookies, style, section, game, dev, development
---

Headers
================

Headers can be written in two different ways:


1. with "=" symbols
2. with "#" symbols

"=" ways
--

Header First Level
===============

```
Header First Level
===============

or

Header First Level

===============
```

> **Note**: No matter how many times "=" is repeated. Add a new line after "=" row.

Header Second Level
---------------

```
Header Second Level
---------------

or

Header Second Level

---------------
```

> **Note**: No matter how many times "=" is repeated. Add a new line after "=" row.
"#" ways

"#" ways
---------------

# Header First Level

```
# Header First Level
```
> **Note**: only one "#" symbol mean first level header. It's very important add a space after the "#"

## Header Second Level

```
## Header Second Level
```
> **Note**: two "#" symbols mean second level header. It's very important add a space after the "##"

### Header Third Level

```
### Header Third Level
```
> **Note**: three "#" symbols mean third level header. It's very important add a space after the "###"

#### Header Fourth Level

```
#### Header Fourth Level
```
> **Note**: four "#" symbols mean fourth level header. It's very important add a space after the "####"
>
> There are six level of header in markdown

# Paragraph
In order to add a paragraph, set a new line after and before it

Ehy! This is a new paragraph

```
bla bla bla bla

Ehy! This is a new paragraph

bla bla bla bla 
```

# Text Formatting

**Bold**

```
**Bold**
```
> **Note**: No space allowed between "**" symbols and text.

*Italic*

```
*italic*
```
> **Note**: No space allowed between "*" symbol and text.

***Bold Italic***

```
***Bold Italic***
```
> **Note**: No space allowed between "***" symbols and text.

# CodeBlocks

Code can be written with "\`" symbol or "\~". Only "\~/\`" means an inline code block. Three of these symbols on the top and the bottom of a paragraph mean a full code block with identation . After the symbols on the top, you can add a specific language name and formatting it.

- inline code: 

`This is an inline Code!`

```
`This is an inline Code!`
```

- multiple lines code:

```
This is a multiple lines code!

Such Wow!
```

```
    ``` 
    This is a multiple lines code!

    Such Wow!
    ```
```
- formatted code:

```javascript
if(this == formatted_code){
    for(var i = 0; i < MAX_WOW; i++){
        print("Such Wow!");
    }
}
    
```
```
    ```javascript
    if(this == formatted_code){
        for(var i = 0; i < MAX_WOW; i++){
            print("Such Wow!");
        }
    }
    ```
```

# Blockquotes

To add blockquotes, use ">" symbol and space beforce text.

> I am a blockquote!

```
> I am a blockquote!
```

Multiple Lines:

> I am a blockquotes in
>
> multiple
>
> lines

```
> I am a blockquotes in
>
> multiple
>
> lines
```

Blockquotes support text formatting:

> **Note**: this is true

```
> **Note**: this is true
```

# Lists

*, -, + are valid symbols for lists. Remember to add space before text.

#### Dotted Lists

* No
* Yes
* Maybe

```
* No
* Yes
* Maybe
```

* No
- Yes
+ Maybe

```
* No
- Yes
+ Maybe
```

* No
    - Yes
        + Maybe

```
* No
    - Yes
        + Maybe
```


#### Numbered Lists

1. No
2. Yes
3. Maybe

```
1. No
2. Yes
3. Maybe
```

# Table

| First Cell  | Second Cell  | Third Cell  |  Fourth Cell |
|----|----|----|----|
| A  |  B |  C |  D |
| B  |  C |  D |  E |   
| C  |  D |  E |  F |   
