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
