# Alt text

## Background

### What is alt text?

Alternative text (alt text) is a _text alternative_ to non-text content — i.e., images — on the web. 

### Why should I care?

1. **Making experiences accessible for people who use assistive devices**<br>Screen readers will announce an image’s alt text because they cannot analyze an image’s content, function, or context. (Without alt text, the screen reader will announce the image’s filename, which is more than likely random, non-descriptive, and/or generally unfriendly.) 
2. **SEO**<br>Search engine robots can’t analyze images. When they crawl your site, they will index the alt text for all images.
3. **Fallbacks**<br>If an image file does not load (due to network error or user choice) in a browser or email client, alt text will be displayed in place of the image.

## Technical implementation

### `<img>`
Alt text is described within the value of the `alt` attribute on `<img>` elements
```html
<img src="image.png" alt="alt text">
```

Purely decorative images must contain _blank_ alt text (`alt=""`).

### CSS `background-image` property

Generally, images that are displayed via CSS should only be decorative. 

If an image is meaningful, HTML elements with a CSS background image may be made readable in the accessibility API by describing the element as an image with `role="img"` and adding its alt text via `aria-label`. These HTML elements should serve no other purpose their `role` attribute is accurate.

```HTML
<div style="background-image: url('image.png')" role="img" aria-label="alt text">
</div>
```

### Inline `<svg>`
Alt text is described within the `<title>` tag inside an `<svg>` element. The `<title>` is then associated with the `<svg>` via `aria-labelledby`.

Additionally, inline `<svg>`s must have their role set with `role="img"`.

```html
<svg aria-labelledby="image-inline-svg" role="img">
  <title id="image-inline-svg">alt text</title>
</svg>
```

→ **Read more**: [CSS Tricks | Accessible SVGs](https://css-tricks.com/accessible-svgs/#2-inline-svg)

### `<canvas>`
Unless an accessible fallback exists, alt text is described within the `aria-label` attribute on `<canvas>` elements. If a `<canvas>` displays a graphic, it should be sementically set as an image with `role="img"`. 

```html
<canvas aria-label="alt text" role="img"></canvas>
```
  
→ **Read more**: [Paul J Adam | Canvas](https://pauljadam.com/demos/canvas.html)

### Media group

A grouping of non-text content that should be consumed as a single image (which could include any media, code snippets, emojis, or other content) should be semantically identified as an image with `role="img"`. 

If the image is not contextually described in the page’s copy, use `aria-label` to provide overall descriptive alt text for the media group.

```html
<div role="img" aria-label="alt text">
  <img src="image-1.png" alt="">
  <img src="image-2.png" alt="">
</div>
```

If the image is described elsewhere in the page, identify that location with `aria-labelledby`.

```html
<div role="img" aria-labelledby="image-group">
  <img src="image-1.png" alt="">
  <img src="image-2.png" alt="">

  <p id="image-group">
    Text describing the group of images, viewable and accessible to all.
  </p>
</div>
```


→ **Read more**: [MDN | ARIA: img role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/Role_Img)

### Other non-text elements

In the spirit of providing contextual descriptions for non-text content, video and audio on the web should always include captions and/or a transcript.

Other non-text or media elements should be described by `aria-label` or `aria-labelledby`. If they are purely decorative elements, they should be should be hidden from accessibility APIs via `aria-hidden="true"`. Elements can still be exposed to assistive technology while being programatically set as having no semantic role with `role="none presentation"`.

→ **Read more**: [MDN | Using the `aria-hidden` attribute](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-hidden_attribute)

### Markdown
Alt text is described within brackets `[]` on image elements.
```markdown
![alt text](image.png)
```

## Content guidelines

### Do
* Alt text should be able to serve as a replacement text for the image. If every image on a page was replaced by the value of its `alt` attribute, the meaning of the page would not change.
* To write approrpriate alt text, concisely describe the image’s main points and its context within the page and its nearby text content. Why is the image there? What does it illustrates? What does it add to the text?

### Don’t
* Alt text shouldn’t repeat information already provided in the page’s copy.
* Alt text is not a supplement to to the image.
* Purely decorative images should not have descriptive alt text.

### Tactics
* Alt text should be as long as necessary to be informative, while still being as brief as possible. Aim for under 250 characters. 
  * If the alt text is longer than ~250 characters, consider captioning the image element or providing its context in the copy itself. Aim for clarity for all users.
* Use appropriate grammar so a screen reader annouces speach naturally.
  * Use sentence-style capitalization.
  * Use punctuation, including an ending period, even if the alt text is a dependent clause. This helps the screen reader pause before continuing to announce the following text on the page.
* When the image type (e.g., painting, photo, screenshot, graphic) is directly relevant to the topic, describe it at the beginning of the alt text, e.g., “An oil painting of flowers in a vase by Vincent Van Vogh” situated on the same page as “A photograph by Ansel Adams of the Tetons and Snake River”.
* For UI images that aren’t otherwise declared in text, describe the function of the image, not the description of the image, e.g. “Next”, not “Right arrow”.
* Functional actions should provide additional context.
  * In the case of social icons, “Twitter” as alt text is not very helpful. Does the social icon mean “Share this page on Twitter” or “Follow us on Twitter”?
* Photos of people require additional consideration. 
  * A person’s age, race, gender, disability status, and other attributes depend on the context; do no over-emphasize an aspect of a person if it is not relevant to the context. 
  * Alt text should include mood or feeling to humanize photos of people, e.g., “Two women laughing on a couch together as they use an iPad to watch videos.”

## Content examples

From the [alt text training by Microsoft MSCOM](https://mscomaccessibility.azurewebsites.net/training#events):

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

### Additional examples
* [W3C | An alt Decision Tree](https://www.w3.org/WAI/tutorials/images/decision-tree/)

## Resources

### Specifications
* [WCAG spec | 1.1.1 Non-text Content](https://www.w3.org/WAI/WCAG21/Understanding/non-text-content.html)
* [W3C HTML spec | 4.7.1.1 Requirements for providing text to act as an alternative for images](https://www.w3.org/TR/2014/REC-html5-20141028/embedded-content-0.html#alt)
* [WhatWG HTML spec | 4.8.4.4 Requirements for providing text to act as an alternative for images](https://html.spec.whatwg.org/multipage/images.html#alt)

### Articles/Guides
* [WebAIM | Alternative Text](https://webaim.org/techniques/alttext)

### Content style guides within design systems
* [Shopify Polaris | Content: Alt text](https://polaris.shopify.com/content/alternative-text)
* [web.dev Content handbook | Markup: Images and video](https://web.dev/handbook/markup-media/#alt-vs-figcaption)

### Classes/Workshops
* [Alt text class by Microsoft MSCOM](https://mscomaccessibility.azurewebsites.net/training#events), free, offered several times a year
