---
title: Long table of contents
order: 31
---

# Long table of contents

A long page designed to exercise the table of contents: many headings, several
nesting levels, repeated titles, inline markup, and headings long enough to wrap.

## Getting started

Start with the overview, then work through the nested sections below.

### Install the dependencies

Install the packages before running the development server.

#### Package manager options

Use pnpm, npm, or yarn. The examples in this document use pnpm.

### Create a configuration file

Create a `vited.config.ts` file in the project root.

## A very long heading that tests wrapping inside the table of contents and the document itself

This heading is intentionally long so that the table of contents has to wrap it
across several lines without breaking the layout of the sidebar.

## Heading with `inline code` and **bold text**

The table of contents should show the plain text of this heading, not the markup.

## A heading with a [link](https://example.com) inside

Links in headings are rendered as links, and the outline should still show their
text.

## Repeated heading

The first heading with this title gets the `repeated-heading` slug.

### Repeated heading

A nested heading with exactly the same text gets a numbered slug.

## Repeated heading

Another duplicate at the second level, which should get `repeated-heading-2`.

## 中文标题

Chinese headings keep their characters in the generated anchor.

### 中文子标题

A nested Chinese heading.

## Symbols and punctuation: /?#

Slugs remove characters that are not valid in a fragment.

## Section one

Content for section one. The page is long enough that the table of contents
needs to stay in view while scrolling.

### Subsection one point one

More content.

#### Detail one point one point one

Even more content.

#### Detail one point one point two

Additional content.

### Subsection one point two

More content.

## Section two

Content for section two.

### Subsection two point one

More content.

### Subsection two point two

More content.

## Section three

Content for section three.

## Section four

Content for section four.

## Section five

Content for section five.

## Section six

Content for section six.

## Section seven

Content for section seven.

## Section eight

Content for section eight.

## Section nine

Content for section nine.

## Section ten

Content for section ten.

## Section eleven

Content for section eleven.

## Section twelve

Content for section twelve.

## Summary

The end of the long sample page.
