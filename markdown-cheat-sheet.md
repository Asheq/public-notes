<!-- This is a comment and will not be displayed in output -->

# Markdown

## Emphasis
Emphasis (italics) with *asterisks* or _underscores_

Strong emphasis (bold) with **double asterisks** or __double underscores__

Strike through with ~~double tildes~~

## Unordered list
Unordered list with leading asterisks, hyphens, or plus signs:
* Item
* Item
	- Nested Item
	- Nested Item
* Item
	+ Nested Item
		- Double Nested Item

## Ordered list
Ordered list with leading `1.`:
1. Item
1. Item
	1. Nested Item
	1. Nested Item
1. Item
	1. Nested Item
		1. Double Nested Item

## Mixed list and paragraphs
* Item
* Item

	Paragraph for list item with a blank line and leading whitespace character
	* Nested Item
* Item

	1. Nested Item
	1. Nested Item

		Paragraph 1 for nested list item with a blank line and 2 leading whitespace characters

		Paragraph 2 for nested list item. To create a line break  
		without creating a new paragraph, add two trailing spaces.

## Link
* Link with square brackets (and parentheses):
	* [In-line style](http://example.com "Title, aka text to show on hover")
	* [Reference style #1][1]
	* [Reference style #2][Arbitrary case-insensitive reference text]
	* Reference style #3: [link text itself]
	* [Some relative file](./README.md)
* Link with raw text:
	* example.com
	* http://example.com
	* <http://example.com>

[1]: http://slashdot.org "Slashdot"
[arbitrary case-insensitive reference text]: https://www.mozilla.org "Mozilla"
[link text itself]: http://www.reddit.com "Reddit"

## Image

The syntax for an image is the same as that for for a link but with a leading exclamation mark:

![In-line style](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png)

![Reference style][logo]

[logo]: https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png

Image that is a link:

[![Duck Duck Go](https://upload.wikimedia.org/wikipedia/en/8/88/DuckDuckGo_logo.svg)](https://duckduckgo.com/)

## In-line code
* In-line code with `backticks`


## Block quote
> Block quote with a leading greater-than sign. You can continue onto a new line (but a new line
> will not be displayed in the output). You can embed **Markdown** in block quotes.

## HTML

<div>
	<dt>Hello</dt>
	<dd>used as a greeting or to <b>begin</b> a conversation</dd>
	<dt>Goodbye</dt>
	<dd>used to express good wishes when parting or at the <b>end</b> of a conversation</dd>
</div>

## Line breaks

This line is displayed in its own paragraph.

This line is part of a new separate paragraph.
This line is displayed as if it is part of the previous line.

This line is part of a new separate paragraph.  
This is a new line in the same paragraph.

## Code block
```
Code block
	with triple backticks.
  Whitespace is preserved.
```

```bash
npm install
npm start
```

```javascript
// This code block will be syntax highlighted as JavaScript
function sayHello() {
	console.log('Hello')
}
```

```html
<!-- This code block will be syntax highlighted as HTML -->
<div>
	<i>Hello</i>
</div>
```

*Note:* Syntax highlighting is not supported in core Markdown spec but is supported in GitHub Flavored Markdown

## Task list

Task list with leading square brackets:

* [x] Completed task
* [x] Completed task
* [ ] Uncompleted task

*Note:* Task lists are not supported in core Markdown spec but are supported in GitHub Flavored Markdown

## Table

Table with vertical lines and dashes:

| Name     | Email              | Age | Alias
| ---      | :---:              | ---:| ---
| John Doe | john@gmail.com     | 45  | `heresjohnny`
| Jane Doe | jane.doe@gmail.com | 43  | `janeofthejungle`

<i>Notes:</i>
* Colons can be used to align columns
* Outer vertical lines are optional
* Raw Markdown does not need to line up prettily
* Can embed in-line Markdown

*Note:* Tables are not supported in core Markdown spec but are supported in GitHub Flavored Markdown


## Markdown Horizontal Rules
A horizontal rule with a series of (3+)

underscores

___

asterisks

***


Markdown Heading 1 with equal signs
===

Markdown Heading 2 with hyphens
---

# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6
