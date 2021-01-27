# Alt text

## Background

#### What is alt text?

Alternative text (alt text) is a text alternative to non-text content, i.e. images, on the web. 

#### Why should I care?

1. Screen readers will announce an image’s alt text because they cannot analyze an image’s content, function, or context. (Without alt text, the screen reader will announce the image’s filename, which is more than likely random, non-descriptive, and/or generally unfriendly.) 
2. Search engine robots can’t analyze images. When they crawl your site, they will index the alt text for all images.
3. If an image file does not load (due to network error or user choice) in a browser or email client, alt text will be displayed in place of the image.

#### How do I implement it?

* HTML
  * `img`: Alt text is described within the `alt` attribute on `<img>` elements
  * `svg`: Alt text is described within the `title` tag inside an `<svg>` element
* Markdown: Alt text is described within brackets `[]` on image `![](https://)` elements

## Guidelines

Alt text shouldn’t repeat information already provided in the page’s copy.

Alt text is not a supplement to to the image.

Alt text should be able to serve as a replacement text for the image. If every image on a page was replaced by the value of its `alt` attribute, the meaning of the page would not change.

To write approrpriate alt text, concisely describe the image’s main points and its context within the page and its nearby text content. Why is the image there? What does it illustrates? What does it add to the text?

All images must have an `alt` attribute, but not all images require alt _text_. The `alt` attribute may be blank if the context of the image does not require description; images that are purely decorative should always be blank, i.e., `alt=""`.

## Tactics

Alt text should be as long as necessary to be informative, while still being as brief as possible, preferably no more than 150-256 characters.

Use sentence-style capitalization. Lead with definite and indefinite articles like “the” and “a”.  Use punctuation, including an ending period, even if the alt text is a dependent clause. Appropriate grammar leads to more natural speech in a screen reader.

When the image type (e.g., painting, photo, screenshot, graphic) is directly relevant to the topic, describe it at the beginning of the alt text, e.g., “An oil painting of flowers in a vase by Vincent Van Vogh” situated on the same page as “A photograph by Ansel Adams of the Tetons and Snake River”.

Instead of adding a description longer than 256 characters, consider creating a caption, i.e., `<figcaption>` describing a media element inside a `<figure>` element. 

For UI images that aren't declared in text, describe the function of the image, not the description of the image, e.g. “Next”, not “Right arrow”.

Functional actions should add additional context. In the case of social icons, “Twitter” as alt text is not very helpful. Does the social icon mean “Share this page on Twitter” or “Follow us on Twitter”?

Photos of people require additional consideration. A person’s age, race, gender, disability status, and other attributes depend on the context; do no over-emphasize an aspect of a person if it is not relevant to the context. Alt text should include mood or feeling to humanize photos of people, e.g., “Two women laughing on a couch together as they use an iPad to watch videos.”

## Examples

From the [Alt text class by Microsoft MSCOM](https://mscomaccessibility.azurewebsites.net/training#events):

<table>
<thead>
  <tr>
    <th rowspan="3"><img width="431" alt="Screen Shot 2021-01-26 at 11 28 55 PM" src="https://user-images.githubusercontent.com/221550/105943480-5faf8580-602f-11eb-8736-ed2ef40ac8eb.png"></th>
    <th colspan="2">Context</th>
  </tr>
  <tr>
    <td><strong>Encyclopedia website</strong>:<br>“The Colorado River running through the steep-sided walls of the Grand Canyon.”</td>
    <td><strong>Photography website</strong>:<br>“The vivid colors and shadows of the Grand Canyon enhanced by sunset.”</td>
  </tr>
  <tr>
    <td><strong>Travel website</strong>:<br>“The view from the South Rim Visitors’ Center observation deck.”</td>
    <td><strong>Yoga website</strong>:<br>[blank]</td>
  </tr>
</thead>
</table>

#### Additional examples
* [W3C: An alt Decision Tree](https://www.w3.org/WAI/tutorials/images/decision-tree/)
* [WebAIM: Alternative Text](https://webaim.org/techniques/alttext#example1)

## Resources

* [WCAG 1.1.1 Non-text Content](https://www.w3.org/WAI/WCAG21/Understanding/non-text-content.html)
* [W3C HTML spec: 4.7.1.1 Requirements for providing text to act as an alternative for images](https://www.w3.org/TR/2014/REC-html5-20141028/embedded-content-0.html#alt)
* [WhatWG HTML spec: 4.8.4.4 Requirements for providing text to act as an alternative for images](https://html.spec.whatwg.org/multipage/images.html#alt)
* [Alt text class by Microsoft MSCOM](https://mscomaccessibility.azurewebsites.net/training#events), free, offered several times a year
* [Shopify Polaris – Content: Alt text](https://polaris.shopify.com/content/alternative-text)
