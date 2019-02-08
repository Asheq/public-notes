<!-- This is a comment and will not be displayed in output -->

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

		Paragraph 1 for nested list item with a blank like and 2 leading whitespace characters

		Paragraph 2 for nested list item. To create a line break  
		without creating a new paragraph, add two trailing spaces.

## Link
* Link with square brackets (and parentheses):
	* [Inline style](http://example.com "Title, aka text to show on hover")
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

![Inline style](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png)

![Reference style][logo]

[logo]: https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png

Image that is a link:

[![4K VIDEO](http://img.youtube.com/vi/Bey4XXJAqS8/0.jpg)](http://www.youtube.com/watch?feature=player_embedded&v=Bey4XXJAqS8)

## Inline code
* Inline code with `backticks`

## Code block
```
Code block
	with triple backticks
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

*Note:* Syntax highlighting is not supported in core Markdown spec but is supported in Github Flavored Markdown


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
<div>
    <a href="http://www.youtube.com/watch?feature=player_embedded&v=Bey4XXJAqS8" target="_blank">
        <img src="http://img.youtube.com/vi/Bey4XXJAqS8/0.jpg" alt="IMAGE ALT TEXT HERE" width="240" height="180" border="10" />
    </a>
</div>

## Line Breaks

This line is displayed in its own paragraph.

This line is part of a new separate paragraph.
This line is displayed as if it is part of the previous line.

This line is part of a new separate paragraph.  
This is a new line in the same paragraph.

## Task list

Task list with leading square brackets:

* [x] Completed task
* [x] Completed task
* [ ] Uncompleted task

*Note:* Task lists are not supported in core Markdown spec but are supported in Github Flavored Markdown

## Table

Table with vertical lines and dashes:

| Name     | Email              | Age | Alias
| ---      | :---:              | ---:| ---
| John Doe | john@gmail.com     | 45  | `heresjohnny`
| Jane Doe | jane.doe@gmail.com | 43  | `janeofthejungle`

<i>Notes:</i>
* Colons can be used to align columns
* Outer pipes are optional
* Raw Markdown does not need to line up prettily
* Can embed inline Markdown
* Tables are not supported in core Markdown spec but are supported in Github Flavored Markdown*

## Headings
Headings with leading number signs:
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6

Heading 1 with Equal Signs
===

Heading 2 with Hyphens
---

## Horizontal Rule
A horizontal rule with a series of (3+)

hyphens

---

underscores

___

asterisks

***
