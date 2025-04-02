---
layout: post
title: Markdown Syntax Guide
description: A comprehensive guide to using markdown in your posts
tags: [markdown, tutorial, formatting]
toc: true
---

# Markdown Syntax Guide

Here's a comprehensive overview of markdown formatting options available in your posts.

<!--more-->

## Text Formatting

**Bold text** is created with double asterisks
*Italic text* uses single asterisks
~~Strikethrough~~ uses double tildes

## Lists

Unordered list:
- Item 1
- Item 2
  - Nested item
  - Another nested item
- Item 3

Ordered list:
1. First item
2. Second item
   1. Nested numbered item
   2. Another nested item
3. Third item

## Code Blocks

Inline code: `const greeting = "Hello World"`

Code block with syntax highlighting:
```typescript
function calculateSum({ a, b }: { a: number, b: number }): number {
    return a + b
}
```

## Blockquotes

> This is a blockquote
> It can span multiple lines
>> And can be nested

## Tables

| Header 1 | Header 2 | Header 3 |
|----------|----------|----------|
| Cell 1   | Cell 2   | Cell 3   |
| Cell 4   | Cell 5   | Cell 6   |

## Links and Images

[Link to external site](https://example.com)

![Alt text for image](https://via.placeholder.com/150)

## Task Lists

- [x] Completed task
- [ ] Incomplete task
- [x] Another completed task

## Extended Syntax

### Definition Lists 

Some Markdown processors allow you to create *definition lists* of terms and their corresponding definitions. To create a definition list, type the term on the first line. On the next line, type a colon followed by a space and the definition.  

```
First Term
: This is the definition of the first term.

Second Term
: This is one definition of the second term.
: This is another definition of the second term.
```

The HTML looks like this:

```html
<dl>
  <dt>First Term</dt>
  <dd>This is the definition of the first term.</dd>
  <dt>Second Term</dt>
  <dd>This is one definition of the second term. </dd>
  <dd>This is another definition of the second term.</dd>
</dl>
```

The rendered output looks like this:

First Term
: This is the definition of the first term.

Second Term
: This is one definition of the second term.
: This is another definition of the second term.

### Emoji

There are two ways to add emoji to Markdown files: copy and paste the emoji into your Markdown-formatted text, or type *emoji shortcodes*.

#### Copying and Pasting Emoji

In most cases, you can simply copy an emoji from a source like [Emojipedia](https://emojipedia.org/) and paste it into your document. Many Markdown applications will automatically display the emoji in the Markdown-formatted text. The HTML and PDF files you export from your Markdown application should display the emoji.

<div class="alert alert-success">
  <i class="fas fa-lightbulb"></i> <strong>Tip:</strong> If you're using a static site generator, make sure you <a href="https://www.w3.org/International/tutorials/tutorial-char-enc/">encode HTML pages as UTF-8</a>.
</div>

#### Using Emoji Shortcodes

Some Markdown applications allow you to insert emoji by typing emoji shortcodes. These begin and end with a colon and include the name of an emoji.

```text
Gone camping! :tent: Be back soon.

That is so funny! :joy:
```

The rendered output looks like this:

Gone camping! ⛺ Be back soon.

That is so funny! 😂

<div class="alert alert-info">
  <i class="fas fa-info-circle"></i> <strong>Note:</strong> You can use this <a href="https://gist.github.com/rxaviers/7360908">list of emoji shortcodes</a>, but keep in mind that emoji shortcodes vary from application to application. Refer to your Markdown application's documentation for more information.
</div>

### Footnotes

Footnotes allow you to add notes and references without cluttering the body of the document. When you create a footnote, a superscript number with a link appears where you added the footnote reference. Readers can click the link to jump to the content of the footnote at the bottom of the page.

To create a footnote reference, add a caret and an identifier inside brackets (`[^1]`). Identifiers can be numbers or words, but they can't contain spaces or tabs. Identifiers only correlate the footnote reference with the footnote itself — in the output, footnotes are numbered sequentially.

Add the footnote using another caret and number inside brackets with a colon and text (`[^1]: My footnote.`). You don't have to put footnotes at the end of the document. You can put them anywhere except inside other elements like lists, block quotes, and tables.

```
Here's a simple footnote,[^1] and here's a longer one.[^bignote]

[^1]: This is the first footnote.

[^bignote]: Here's one with multiple paragraphs and code.

    Indent paragraphs to include them in the footnote.

    `{ my code }`

    Add as many paragraphs as you like.
```

The rendered output looks like this:

Here's a simple footnote,[^1] and here's a longer one.[^bignote]

[^1]: This is the first footnote.

[^bignote]: Here's one with multiple paragraphs and code.

    Indent paragraphs to include them in the footnote.

    `{ my code }`

    Add as many paragraphs as you like.

### Heading IDs

Many Markdown processors support custom IDs for [headings](/basic-syntax/#headings) — some Markdown processors automatically add them. Adding custom IDs allows you to link directly to headings and modify them with CSS. To add a custom heading ID, enclose the custom ID in curly braces on the same line as the heading.

```text
### My Great Heading {#custom-id}
```

The HTML looks like this:

```html
<h3 id="custom-id">My Great Heading</h3>
```

### Linking to Heading IDs

You can link to headings with custom IDs in the file by creating a [standard link](/basic-syntax/#links) with a number sign (`#`) followed by the custom heading ID. These are commonly referred to as *anchor links*.

<table class="table table-bordered">
  <thead class="thead-light">
    <tr>
      <th>Markdown</th>
      <th>HTML</th>
      <th>Rendered Output</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code class="highlighter-rouge">[Heading IDs](#heading-ids)</code></td>
      <td><code class="highlighter-rouge"> &lt;a href="#heading-ids"&gt;Heading IDs&lt;/a&gt;</code></td>
      <td><a href="#heading-ids">Heading IDs</a></td>
    </tr>
  </tbody>
</table>

Other websites can link to the heading by adding the custom heading ID to the full URL of the webpage (e.g, `[Heading IDs](https://www.markdownguide.org/extended-syntax#heading-ids)`).

### Highlights

This isn't common, but some Markdown processors allow you to highlight text. The result looks <mark>like this</mark>. To highlight words, use two equal signs (`==`) before and after the words.

```text
I need to highlight these ==very important words==.
```

The rendered output looks like this:

I need to highlight these <mark>very important words</mark>.

Alternatively, if your Markdown application supports [HTML](/basic-syntax/#html), you can use the `mark` HTML tag.

```html
I need to highlight these <mark>very important words</mark>.
```

### Strikethrough

You can strikethrough words by putting a horizontal line through the center of them. The result looks ~~like this~~. This feature allows you to indicate that certain words are a mistake not meant for inclusion in the document. To strikethrough words, use two tilde symbols (`~~`) before and after the words.

```
~~The world is flat.~~ We now know that the world is round.
```

The rendered output looks like this:

~~The world is flat.~~ We now know that the world is round.

### Subscript

This isn't common, but some Markdown processors allow you to use *subscript* to position one or more characters slightly below the normal line of type. To create a subscript, use one tilde symbol (`~`) before and after the characters.

```text
H~2~O
```

The rendered output looks like this:

H<sub>2</sub>O

<div class="alert alert-success">
  <i class="fas fa-lightbulb"></i> <strong>Tip:</strong> Be sure to test this in your Markdown application before using it. Some Markdown applications use one tilde symbol before and after words not for subscript, but for <a href="/extended-syntax/#strikethrough">strikethrough</a>. 
</div>

Alternatively, if your Markdown application supports [HTML](/basic-syntax/#html), you can use the `sub` HTML tag.

```html
H<sub>2</sub>O
```

### Superscript

This isn't common, but some Markdown processors allow you to use *superscript* to position one or more characters slightly above the normal line of type. To create a superscript, use one caret symbol (`^`) before and after the characters.

```text
X^2^
```

The rendered output looks like this:

X<sup>2</sup>

Alternatively, if your Markdown application supports [HTML](/basic-syntax/#html), you can use the `sup` HTML tag.

```html
X<sup>2</sup>
```

### Tables

To add a table, use three or more hyphens (`---`) to create each column's header, and use pipes (`|`) to separate each column. For compatibility, you should also add a pipe on either end of the row.

```
| Syntax      | Description |
| ----------- | ----------- |
| Header      | Title       |
| Paragraph   | Text        |
```

The rendered output looks like this:

<table class="table table-bordered">
  <thead>
    <tr>
      <th>Syntax</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Header</td>
      <td>Title</td>
    </tr>
    <tr>
      <td>Paragraph</td>
      <td>Text</td>
    </tr>
  </tbody>
</table>

Cell widths can vary, as shown below. The rendered output will look the same.

```
| Syntax | Description |
| --- | ----------- |
| Header | Title |
| Paragraph | Text |
```

<div class="alert alert-success">
  <i class="fas fa-lightbulb"></i> <strong>Tip:</strong> Creating tables with hyphens and pipes can be tedious. To speed up the process, try using the <a href="https://www.tablesgenerator.com/markdown_tables">Markdown Tables Generator</a> or <a href="https://anywaydata.com">AnyWayData Markdown Export</a>. Build a table using the graphical interface, and then copy the generated Markdown-formatted text into your file.
</div>

#### Alignment

You can align text in the columns to the left, right, or center by adding a colon (`:`) to the left, right, or on both side of the hyphens within the header row.

```
| Syntax      | Description | Test Text     |
| :---        |    :----:   |          ---: |
| Header      | Title       | Here's this   |
| Paragraph   | Text        | And more      |
```

The rendered output looks like this:

<table class="table table-bordered">
  <thead>
    <tr>
      <th style="text-align: left">Syntax</th>
      <th style="text-align: center">Description</th>
      <th style="text-align: right">Test Text</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: left">Header</td>
      <td style="text-align: center">Title</td>
      <td style="text-align: right">Here’s this</td>
    </tr>
    <tr>
      <td style="text-align: left">Paragraph</td>
      <td style="text-align: center">Text</td>
      <td style="text-align: right">And more</td>
    </tr>
  </tbody>
</table>

#### Formatting Text in Tables

You can format the text within tables. For example, you can add [links](/basic-syntax/#links), [code](/basic-syntax/#code-1) (words or phrases in backticks (`` ` ``) only, not [code blocks](/basic-syntax/#code-blocks)), and [emphasis](/basic-syntax/#emphasis).

You can't use headings, blockquotes, lists, horizontal rules, images, or most HTML tags.

<div class="alert alert-success">
  <i class="fas fa-lightbulb"></i> <strong>Tip:</strong> You can use HTML to create <a href="/hacks/#line-breaks-within-table-cells">line breaks</a> and add <a href="/hacks/#lists-within-table-cells">lists</a> within table cells.
</div>

#### Escaping Pipe Characters in Tables

You can display a pipe (`|`) character in a table by using its HTML character code (`&#124;`).

Credits: [https://www.markdownguide.org/](https://www.markdownguide.org/)