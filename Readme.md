# Website Accessibility

---

> Web Accesibility means that people with disabilities can use the Web.

When people talk about web accesibility, they talk about making the app accesible for people with disabilties.

### Types of disabilities

---

- Mobility and physical
- Cognitive and neurological
- Visual
- Hearing

> The web is already accessible, even if your website is not

### Reasons developers should learn accessibility

---

- It is fun
- We are the ones making it inaccessible
- Human Rights
- Legal Issue
- Reach a larger audience
- Impactful
- Makes you a specialist

### Ways people use the Web

---

- Keyboard only
- Head wand
- Mouth stick
- Single switch
- Screen reader

### Accesibility Standards

---

Web Content Accesibility Guidelines (WCAG)

WCAG specifies three different conformance levels:

- A (lowest)
- AA (mid range)
- AAA (highest)

> Level A sets a minimum level of accessiblity and does not achieve broad accessibility for many situations. For this reason, University of California recommends AA conformance for all web based information

> WebAIM provides a handy [checklist](https://webaim.org/standards/wcag/checklist "WebAIM Checklist") with their recommendations.

### Screen Readers

---

How they work?

> Screen Readers convert digital text into synthesized speech. They empower users to hear content and navigate with the keyboard.

Related to the alternative text, if a screen reader encounters an image and if it can't find the alt text, it will read the file's name.

### Accessible HTML

---

#### Semantic Elements

Some elements have semantic meaning but no special functionality (e.g. aside, footer, header)

Other's provide a lot of built in functionality such as: button, input, textarea.

#### HTML Labels

A better option is to use HTML label tag which will allow screen readers to recite the label when the field is focused.

#### Limitations with label tag

The label tag can only work with "labelable" elements. Those include:

- button
- input
- keygen
- meter
- output
- progress
- select
- textarea

If you ever need to label an element not on that list, use **aria-label** instead.

#### Buttons

If we are in the situation of using a div instead of a button, we can give it an ARIA role, this will let screen readers know the element can be clicked (role="button")
We can give also a tabindex, this will allow keyboard only users to tab to it.

`<div role="button" tabindex="0" onclick="alert("hello")">Click me!</div`

> Don't forget about keyboard only users!

`<div aria-label="Alert the word hello" role="button" tabindex="0" onclick="alert("hello")" onkeyup="alert("hello again")">Click me!</div`

### ARIA

---

ARIA is a set of attributes that define ways to make web content accessible for people with disabilities.
[ARIA: Roles, states and properties](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques "ARIA: Roles, states and description")

#### Live Regions

Applications can become very dynamic. For cases where important information could be coming in at any time, the ARIA spec provides the ability to mark an element as containing live data so that screen readers can read out updates as they come.

Think of using the Uber app to hail a ride. At first your status will be "waiting for a ride" but at an undetermined time it will change to "drive en route". We could:

`<div aria-live="assertive">Waiting for a ride</div>`

Then all we have to do is update the content of the div and any assistive technology will let the user know.

The value that you pass in the aria-live is a politeness setting. You can pass:

- assertive - will interrupt whatever it's doing to announce
- polite - will announce the live region update when it next idles
- off - will not read the update

### Focus Management

---

#### Keyboard only users

Using of shortcuts for almost any action which are great for both keyboard users and power users.

#### Skip links

Skip links help users skip over large headers and navigation and jump right into the main content of your site.

#### Tab navigation

You can use the tab key to navigate to the next tabbable item and shift+tab to navigate to the previous item.

Tabbable elements include:

- `<a>`
- `<button>`
- `<input>`
- `<select>`
- `<textarea>`
- `<iframe>`

These are only a part of them.

To make an element tabbable, you can add the tabindex attribute to any element like this:

`<div tabindex="0">I'm focusable</div>`

Tabindex values:

- a negative value means that the element should be focusable, but should not be reachable via sequential keyboard navigation
- 0 means that the element should be focusable and reachable via sequantial keyboard navigation, but its relative order is defined by the platform convention
- a positive value means should be focusable and reachable via sequential keyboard navigation. If several elements share the same tabindex, their relative order follows their relative position in the document

### Visual Considerations

---

To check color contrast online, use the [WebAIM contrast checker](https://webaim.org/resources/contrastchecker/ "WebAIM contrast checker")

#### Colors and forms

An important consideration for colorblind users is making sure that color isn't the only way users can tell if there is an error with the form. For instance, a red ring is not enough. Considering adding an icon or an error label.

#### Visual impairments

To simulate a number of visual impairments on any website, you can check out NoCoffee for Firefox.

#### Setting Language & Fixing Markup

Set the lang attribute both on the top level html tag as well as any sections where the language deviates from it

It is important to fix markup errors, it is recommended that you find and fix the validation or parsing errors in HTML.

For checking markup issues: [HTML Validator](https://validator.w3.org/feed/ "HTML Validator")

#### Neurocognitive - Reduced Motion

Users can set a "prefers reduced motion" setting in their operating system and we can read that setting from the CSS and swap out animations with more subtle effects

An amazing API is one that allows us to detect if the user prefers a light or dark colorscheme.

HTML

`<div class="wrapper">... </div>`

CSS

`@media(prefers-color-scheme: dark) {
    .wrapper {
        background: black;
    }
}`

`@media(prefers-color-scheme: light) {
    .wrapper {
        background: white;
    }
}`

### Tooling

---

#### Accesibility Linters & Dev Tools

- Google's Lighthouse
- Google's Material Design
- Adobe's React Spectrum
- Deque's Axe DevTools
