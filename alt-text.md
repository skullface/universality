# Alt text

## Background

#### What is alt text?

Alternative text (alt text) is a text alternative to non-text content, i.e. images, on the web. 

#### Why should I care?

1. Screen readers will announce the alt text of an image because they cannot analyze an image’s content, function, or context. Without alt text, the screen reader will announce the filename, which may be random, non-descriptive, or otherwise un-friendly.
2. Search engine robots can’t analyze images either. When they crawl your site, they will index the alt text for all images.
3. If an image file does not load (due to network error or user choice) in a browser or email client, alt text will be displayed in place of the image.

#### How do I implement it?

* HTML
  * `img`: Alt text is described within the `alt` attribute on `<img>` elements
  * `svg`: Alt text is described within the `title` tag inside an `<svg>` element
* Markdown: Alt text is described within brackets `[]` on image `![](https://)` elements

## Guidelines

Concisely describe the image’s main points. Why is it there? What does it illustrates? What does it add to the text?

> Replacing every image with the text of its `alt` attribute does not change the meaning of the page.

Alt text shouldn’t repeat information already provided in the page’s copy. 

Alt text is not a supplement to to the image.

Alt text should be able to serve as a replacement text for the image.

## Tactics

Alt text should be as long as necessary to be informative, while still being as brief as possible, preferably no more than 150-256 characters.

Use sentence-style capitalization. Lead with definite and indefinite articles like "the" and "a".  Use punctuation, including an ending period, even if the alt text is a dependent clause. Appropriate grammar leads to more natural speech in a screen reader.

When the image type (painting, photo, screenshot, graphic) is relevant to the topic, describe it at the beginning of the alt text, e.g. "A photograph of X".

Instead of adding a description longer than 256 characters, consider creating a caption, e.g. `<figcaption>` describing a media element inside a `<figure>` element. 

For UI images that aren't declared in text, describe the function of the image, not the description of the image, e.g. "Next", not "Right arrow".

Functional actions should add additional context. In the case of social icons, “Twitter” as alt text is not very helpful. Does the social icon mean “Share this page on Twitter” or “Follow GitHub on Twitter”?

Photos of people require additional consideration. A person’s age, race, gender, disability status, and other attributes depend on the context; do no over-emphasize an aspect of a person if it is not relevant to the context. Alt text should include mood or feeling to humanize photos, e.g. "Two women laughing on a couch together as they use GitHub for Mobile iPad."

## Examples

* [W3C: An alt Decision Tree](https://www.w3.org/WAI/tutorials/images/decision-tree/)
* [WebAIM: Alternative Text](https://webaim.org/techniques/alttext#example1)

## Resources

* [WCAG 1.1.1 Non-text Content](https://www.w3.org/WAI/WCAG21/Understanding/non-text-content.html)
* [W3C HTML spec: 4.7.1.1 Requirements for providing text to act as an alternative for images](https://www.w3.org/TR/2014/REC-html5-20141028/embedded-content-0.html#alt)
* [WhatWG HTML spec: 4.8.4.4 Requirements for providing text to act as an alternative for images](https://html.spec.whatwg.org/multipage/images.html#alt)
* [Alt text class by Microsoft MSCOM](https://mscomaccessibility.azurewebsites.net/training#events), free, offered several times a year
* [Shopify Polaris – Content: Alt text](https://polaris.shopify.com/content/alternative-text)
