# Lab 2 — Make Your Page Do Something

**Monday, August 17** · Covers Class 1 (the DOM) · Learning Outcome 1

## Objective

Your page from Lab 1 is a document. This lab turns it into an interface: it responds to what the
person using it types and clicks, without ever reloading.

## What you are building

Three features, on the page you already have:

1. **An interactive collection.** One new section of your page, listing things you can describe —
   projects, books, courses. It is built from data, it can be filtered, and items can be added to it
   while the page is open.
2. **A contact form that answers back.** The form from Lab 1, validated in the browser.
3. **A change of state.** One control that switches something about the page.

**All three are required, and so is every requirement listed under them.** When a requirement offers
alternatives — "a text field, category controls, or both" — you are choosing *how* to satisfy it, not
*whether* to. Requirements 1, 7 and 8 apply to everything you write today.

Nothing here replaces your Lab 1 page. You are adding to a page that is already finished.

## Before you start

- Your Lab 1 page, published and reachable.
- A browser with DevTools. You will spend this lab with the console open.

## The deliverable

You keep working in the **same repository as Lab 1**, `webtech-lab-01`, and the site stays at the
same URL. Do not create a second repository and do not publish a second site.

Added to the repository:

| File | What it is |
|---|---|
| At least one `.js` file | Your script. The name is up to you. |
| `README.md` | Extended — see below. |

Your `README.md` gains a section that lists the interactive features you built and, for each one, the
one sentence a reader needs to try it: where on the page it is, and what to do. A feature nobody can
find is a feature you did not build.

**Canvas.** Submit **the URL of your repository**. Not the published site: the repository, which is
where your code is and where the `README.md` points at the published site.

This lab is **individual**. One submission per student.

---

## Requirements

Eight requirements, every one of them marked. Requirements 2, 3 and 4 are three things the **same**
section has to do — not three sections.

### 1. The script

Your JavaScript lives in an **external file** loaded by your HTML. Code written inside a `<script>`
tag in the document does not count.

Your script runs at a moment when the elements it looks for already exist. A `querySelector` that
returns `null` is the most common failure in this lab, and it is yours to prevent — Class 1 showed
you where a script goes and why it matters.

When the page loads and while every feature below is used, the **console shows no errors**.

### 2. The collection: built from data

Add a new section to your page holding a **collection of items**: projects, courses, books,
repositories, films — anything you can describe. It must contain at least **six** items, and each
item has at least **three** fields, one of which sorts it into a category.

The items are declared as an **array of objects in your JavaScript**, and the section is built by
walking that array and **creating nodes**. Assembling a string of HTML by concatenation and dropping
it into the document does not meet this requirement, whatever the result looks like.

### 3. The collection: filtering, as it happens

The visitor can narrow the collection down, using a text field, a set of category controls, or both.

- The page responds **while typing** or **on click** — never on a page reload, and never behind a
  "search" button that reloads anything.
- When no item matches, the page **says so**. An empty region with no explanation is a bug, not a
  result.
- Clearing the filter brings every item back.

### 4. The collection: adding items, without breaking anything

A form of its own — not the contact form from requirement 5 — adds a new item to the collection. The
item that appears must be indistinguishable from the ones that were there when the page loaded:

- It is built through **the same code path** as the original items. One function produces an item,
  whether it is called while the page loads or long after.
- It obeys the filter from requirement 3 exactly like the rest.
- Each item offers an action of its own — remove it, mark it, expand it — and the item you just added
  responds to that action **without a listener of its own having been registered on it**. A single
  listener on the container handles the whole collection, however many items it holds and whenever
  they arrived. This is the hardest line in the lab, and the one worth your time.

Nothing the visitor types is inserted into the document as HTML. Text from a form field enters the
page as text.

### 5. The contact form

The contact form from Lab 1 is validated when it is submitted, not before.

- Submitting an invalid form **does not reload the page**.
- Every invalid field shows its own message, **next to the field**, and that message is associated
  with the control so a screen reader reaches it. `alert` is not an error message.
- The message goes away once the problem is fixed.
- A valid submission is confirmed on the page. There is still no server — that is Class 8.

You may not delegate this to the browser's built-in validation. The rules and the messages are yours.

### 6. The toggle

One control on your page toggles a state: a light and dark theme, sections that open and close, a
panel that shows and hides. The toggle changes **classes**, not inline styles, and it updates the
ARIA attribute that describes its state so that the change is announced and not only seen.

### 7. What you may not use

- **No libraries and no frameworks.** No jQuery, no React, nothing loaded from a CDN.
- **No `fetch` and no asynchronous requests.** Talking to a server is Class 11.
- **No `on*` attributes in your HTML.** No `onclick`, no `onsubmit`. Listeners are registered from
  JavaScript.
- **No CSS framework**, same as Lab 1. Bootstrap arrives in Lab 4.

### 8. It still has to be a good page

- Everything clickable is a real control, reachable with the Tab key, operable with the keyboard, and
  visibly focused. A `div` with a click listener is not a button.
- Your page **still satisfies Lab 1 with JavaScript turned off**. Everything Lab 1 required lives in
  the HTML; what you built today is added on top of a page that was already complete. Disable
  JavaScript in DevTools and check.

---

## Documentation

Work from the reference, not from tutorials:

- MDN — [Document](https://developer.mozilla.org/en-US/docs/Web/API/Document) and
  [Element](https://developer.mozilla.org/en-US/docs/Web/API/Element)
- MDN — [EventTarget.addEventListener](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)
  and [Event bubbling](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events)
- MDN — [Element.classList](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList)
- WAI-ARIA — [aria-expanded](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-expanded)
  and [aria-pressed](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-pressed)

## Deadline

**Tuesday, August 18, 20:00**, on Canvas.
