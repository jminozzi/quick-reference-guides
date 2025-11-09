# Markdown Reference

**Markdown** is a way to style text on the web. You control the display of the document; formatting words as bold or italic, adding images, and creating lists are just a few of the things we can do with Markdown. Mostly, Markdown is just regular text with a few non-alphabetic characters thrown in, like # or *.


## Headers

```
# This is an <h1> tag
## This is an <h2> tag
###### This is an <h6> tag
```


## Emphasis

#### Code:
```
*This text will be italic*
_This will also be italic_

**This text will be bold**
__This will also be bold__

*You **can** combine them*
```
#### Output:
*This text will be italic*  
_This will also be italic_

**This text will be bold**  
__This will also be bold__

*You **can** combine them*


## Lists

### Unordered
#### Code:
```
* Item 1
* Item 2
  * Sub-item 2.1
  * Sub-item 2.2
```
#### Output:
* Item 1
* Item 2
  * Sub-item 2.1
  * Sub-item 2.2

### Ordered
#### Code:
```
1. Item 1
2. Item 2
3. Item 3
   1. Sub-item 3.1
   2. Sub-item 3.2
```
#### Output:
1. Item 1
2. Item 2
3. Item 3
   1. Sub-item 3.1
   2. Sub-item 3.2

## Images

```
![Alt Text](url/image.png)
```


## Links

```
[GitHub](https://github.com/)
[GitHub](https://github.com/ "Add title (hover tooltip) here.")
<https://github.com/>
```


## Blockquotes

#### Code:
```
Blockquote example:
> The quick brown fox
> jumps over the lazy dog.
```
#### Output:
Blockquote example:
> The quick brown fox
> jumps over the lazy dog.


## Backslash Escapes

Markdown allows you to use backslash escapes to generate literal characters which would otherwise have special meaning in Markdown’s formatting syntax.

#### Code:
```
\*literal asterisks\*
```
#### Output:
\*literal asterisks\*

Note: Markdown provides backslash escapes for the following characters:

```
\ backslash
` backtick
* asterisk
_ underscore
{} curly braces
[] square brackets
<> angle brackets
() parentheses
# hash mark
+ plus sign
- minus sign (hyphen)
. dot
! exclamation mark
| pipe
```


# GitHub Extended Markdown Syntax

GitHub uses its own version of the Markdown syntax that provides an additional set of useful features, many of which make it easier to work with content on GitHub.


## Task Lists

#### Code:
```
- [x] @mentions, #refs, [links](), **formatting**, and <del>tags</del> supported
- [x] list syntax required (any unordered or ordered list supported)
- [x] this is a complete item
- [ ] this is an incomplete item
```
#### Output:
- [x] @mentions, #refs, [links](), **formatting**, and <del>tags</del> supported
- [x] list syntax required (any unordered or ordered list supported)
- [x] this is a complete item
- [ ] this is an incomplete item


## Code Blocks

Markdown coverts text with four leading spaces into a code block; with GFM you can wrap your code with `` ``` `` to create a code block without the leading spaces. Add an optional language identifier and your code with get syntax highlighting.

#### Code:
`````
```javascript
function test() {
console.log("Hello, World!");
}
```
`````

#### Output:
```javascript
function test() {
console.log("Hello, World!");
}
```

## Tables

#### Code:
```
| First Header | Second Header |
| ------------ | ------------- |
| Column 1 Row 1 | Column 2 Row 1 |
| Column 1 Row 2 | Column 2 Row 2 |
| Column 1 Row 3 | Column 2 Row 3 |
| Column 1 Row 4 | Column 2 Row 4 |
```

#### Output:
| First Header | Second Header |
| ------------ | ------------- |
| Column 1 Row 1 | Column 2 Row 1 |
| Column 1 Row 2 | Column 2 Row 2 |
| Column 1 Row 3 | Column 2 Row 3 |
| Column 1 Row 4 | Column 2 Row 4 |
