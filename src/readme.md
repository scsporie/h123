# h①②③ – Accessibility HTML5 Outliner (forked version)

v1.2

Use this bookmarklet to quickly inspect page headings. This version is a fork of the original [H123 Bookmarklet](https://hinderlingvolkart.github.io/h123/)([Github](https://github.com/hinderlingvolkart/h123)).

## Add to your bookmarks

Install by saving one of the following links as a bookmark. The only difference between each option is the link text. 

* [Show Headings][1]
* [h①②③][1]
* [H1️⃣2️⃣3️⃣][1]
* [h❶❷❸][1]

## What does this bookmarklet do?

* Adds an iframe (titled "h123") in the top right corner listing the headings present on a page. Includes the level and text for each heading.
  * If the text for a heading could not be determined, "&#9888; empty or non-text content" will be displayed instead.
* Provides a few options for inspecting headings:
  * Show hidden: Adds any hidden heading elements to the list. Note that hidden elements are not accessible to assistive technology and would not be announced by screen readers.
  * Show tags: Shows text tags that identify different heading states: hidden, visually hidden, and incorrect level.
  * Hover-highlight: Adds a highlight to headings when you hover over the heading with your cursor.

## Changes

As mentioned, this bookmarklet is a fork of https://github.com/hinderlingvolkart/h123. The following changes have been implemented:

* The iframe that displays the bookmarklet content has been given a title of "h123".
* H123 has also been added as a level 1 heading for the bookmarklet content.
* Added some handling for empty or non-text content headings. In these cases, the heading outline will show "&#9888; empty or non-text content" for these headings.
  * "non-text" headings would include headings that contain images with alt text.
* Added text versions of the different states indicated by visual changes.

[1]: {{bookmarklet}}