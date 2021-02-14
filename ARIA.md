# ARIA

[ARIA (Accessible Rich Internet Applications)](https://www.w3.org/WAI/standards-guidelines/aria/) is a collection of attributes designed to enhance website semantics for enable assistive technologies (such as screen readers). The ARIA standard was created by the [Web Accessibility Initiative (WAI)](https://www.w3.org/WAI) within [W3C](https://www.w3.org). ARIA roles either override or extend original content for the Accessibility API.

Remember, _no ARIA is better than bad ARIA_.

## Labels

ARIA label attributes give an HTML element an accessible name for assistive technologies. When the element is in focus, its acessible name will be announced, providing appropriate context for screen reader users.

Labels may be defined by:

* **`aria-labelledby`** which has a value of the `id` of another element containing the desired visible text, e.g.,

  ```
  <h1 id="myBillingId">Billing</h1>
  
  <div>
    <label id="myNameId">Name</label>
    <input type="text" aria-labelledby="myBillingId myNameId"/>
  </div>
  <div>
    <label id="myAddressId">Address</div>
    <input type="text" aria-labelledby="myBillingId myAddressId"/>
  </div>
  ```

* **`aria-label`** which has a value of an accessible text string, e.g.,

  ```
  <a href="/free-shipping" aria-label="Learn more about free shipping">
    Learn more
  </a>
  ```

  `aria-label` will likely be your most frequently used ARIA label.

* **`aria-describedby`** which has a value odescription provides more information that the user might need.

`aria-labelledby` is the first in specificity. Then `aria-label`, then `aria-describedby`.

### Links

When `aria-label` is defined on an link, a screen reader will announce the label instead of the link’s visible text. Use an `aria-label` to:

* Make existing visible text in the link clearer, e.g. `<a href="" aria-label="Learn more about free shipping">Learn more</a>` so the screen reader announces “Learn more about free shipping” instead of ”Learn more”
* Add context where it doesn't otherwise exist, e.g., a dialog close button is labelled with `aria-label="Close this dialog window"` but visually, the button is simply an "x".
* Icon buttons with no live text

As a best practice, for clarity in and out of visible context, the visible text of the element should be included at the beginning of the `aria-label`.

### Landmarks

Landmark roles divide sections of a page by providing semantic meaning. 

Assistive technology users understand what each landmark is for and what type of content they can expect to find within that landmark. Screen reader users may skip to specific landmarks instead of navigating by having the entire page content announced.



#### Tactics

If more than one of the same type of landmark exists in the same page, give each landmark its own label, e.g. (`<nav aria-label="Site navigation"></nav> […] <nav aria-label="Social links"></nav>`) 

To define a landmark outside of the pre-defined landmark elements, use `role="region"` and define the region with `aria-label="<regionname>"`.

To create a custom region, use the `<section>` element and describe the landmark with an `aria-label`. 
