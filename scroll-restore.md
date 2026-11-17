---
title: Scroll restore
order: 33
---

# Scroll restore

This page exercises scroll restoration when navigating between documentation
pages. It is deliberately long, so you can scroll far down before moving to
another page.

## How to test

1. Scroll to the bottom of this page, then open another sample page from the
   sidebar. The next page starts at the top instead of keeping this page's
   scroll position.
2. Open another page with a hash, for example
   [`toc-long#repeated-heading`](../toc-long.md#repeated-heading), from this
   page or a new browser tab. The target heading opens just below the sticky
   header instead of at the top of the page.
3. Click an in-page link such as [Anchor offsets](#anchor-offsets). The target
   heading stops below the sticky header instead of hiding behind it.

## Scroll containers

Themes attach scroll restoration to the nearest scrollable container. Most
documentation sites scroll the document itself, while a theme with a fixed
layout may scroll an inner panel.

### The document scroller

When no ancestor scrolls, the document scrolling element receives the scroll
position. Pages without a hash start at the very top of the document.

### Custom scroll containers

If the page content sits inside a panel with `overflow-y: auto`, that panel is
scrolled instead. The page header and sidebar stay in place because they are
not part of the scrolling element.

## Navigation without a hash

Client-side routing replaces the page content without a full browser
navigation. Without scroll restoration, the browser keeps the previous offset
and the next page can open halfway down or at the bottom.

Themes solve this by placing a scroll restore boundary inside the rendered
page. Every navigation mounts a new boundary, which scrolls the container back
to the top before the reader sees the page.

To observe it, scroll down and follow one of these links to a sibling sample
page:

- [Long table of contents](../toc-long.md)
- [Short table of contents](../toc-short.md)
- [Tables](../table.md)

## Navigation with a hash

A URL that ends in a fragment such as `#anchor-offsets` points to a heading on
the page. Opening it directly should scroll to that heading, even though the
page content is rendered by JavaScript after the initial HTML shell.

Open [`toc-long#repeated-heading`](../toc-long.md#repeated-heading) to navigate
to another page and land on its target heading. To stay on this page instead,
follow [Jump to final checks](#final-checks).

The restore routine keeps looking for the target while the page renders. It
gives up after a bounded number of animation frames, so a missing anchor never
leaves a polling loop behind.

## Anchor offsets

Sticky headers cover the top of the viewport. A plain fragment jump would put
the heading underneath the header, which makes the section title unreadable.

Themes reserve space with `scroll-margin-top` on headings or
`scroll-padding-top` on the scroll container, matching native fragment
navigation. The heading then stops just below the sticky header.

Follow this link to verify the offset from anywhere on the page:
[Jump to how to test](#how-to-test).

## Long pages

Long pages make the difference between a restored and a retained scroll
position obvious. The table of contents on the right tracks the heading that is
currently in view, and its links navigate to sections on this page.

The outline also gives the reader a way to return to an earlier section after
scrolling through the page. Both directions rely on the same hash navigation
behavior described [above](#navigation-with-a-hash).

### Content section one

Documentation pages mix prose, lists, tables, and code blocks. Scrolling
through such content moves the viewport far away from the first heading.

Paragraphs continue for several lines so that the page has a realistic length.
Readers usually jump between sections instead of reading everything in order.

### Content section two

A page that is shorter than the viewport cannot scroll, so scroll restoration
has nothing to restore. This page intentionally contains enough sections to
exceed the height of a typical desktop and laptop screen.

Opening another page from the middle of this content should still land at the
top, because the restore boundary runs when the next page mounts.

### Content section three

The restore boundary is tied to the rendered page rather than to the whole
application. Global rendering would only run once and would miss every later
navigation, which is why themes mount the boundary inside the page area.

This distinction is what makes both the initial load and later client-side
navigations behave predictably.

### Content section four

Back and forward navigation through the browser history remounts the page
content as well. Each history entry mounts the page again, so the scroll
position resets to the top unless the entry carries a fragment.

Fragments in history entries are preserved, so returning to `#final-checks`
scrolls back to that heading.

## Testing checklist

Use the following checklist when a theme updates its layout or routing:

- [ ] A page without a hash opens at the top after a client-side navigation.
- [ ] A page with a hash opens at the target heading.
- [ ] The target heading is not hidden behind the sticky header.
- [ ] In-page anchor links scroll smoothly on the current page.
- [ ] Navigating from a long page to a short page does not keep the old offset.
- [ ] Navigating from a short page to a long page still starts at the top.

## Final checks

This heading is a stable anchor target. Link to `#final-checks` to return here
directly, or scroll back to the top and try the
[navigation without a hash](#navigation-without-a-hash) links.

## References

- [Vited Core](https://github.com/vitedjs/core)
- [react-scroll-restore](https://github.com/guoyunhe/react-scroll-restore)
