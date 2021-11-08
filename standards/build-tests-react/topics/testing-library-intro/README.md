## Intro to Testing Library

* `ByRole` should be your default query. Use semantic elements, don't slap ARIA roles on things that don't need them.
* Only put one assertion in a `waitFor`
* Don't do side-effecting code in `waitFor`, like `keyDown`. Only use it for assertions.
* Don't do implicit assertions with `get*`. Use `toBeInTheDocument` to communicate your intention.
* Use `@testing-library/user-event` over `fireEvent`, it models actual user actions better
* `screen` should be preferred over getting queries out of the render
* Timing
  * `await waitFor(() => somethingAsync)` waits for something to show up
  * `await waitForElementToBeRemoved(() => somethingAsync)` waits for something to go away

## Installing

```bash
npm install --save-dev @testing-library/jest-dom
```

```js
import '@testing-library/jest-dom'
```

* `eslint-plugin-jest-dom`
* `eslint-plugin-testing-library`

## Getting elements

The most important terms to understand in Testing Library are `get`, `find`, and `query`.

**`get`**: Find an element that's already in the DOM
**`find`**: Find an element that will soon be in the DOM
**`query`**: Look for an element that shouldn't be in the DOM

All the of them can be modified to find multiple matches by adding `All` to them: `getAll`, `findAll`, `queryAll`.

Suffixes:

* `ByLabelText` - By attached `<label>` or `aria-label` attribute
* `ByPlaceholderText` - By `<input />` placeholder text
* `ByText` - By containing the text
* `ByDisplayValue` - By current value for an `<input />`
* `ByAltText` - By alt text for an `<img />`
* `ByTitle` - By title attribute
* `ByRole` - By ARIA role
* `ByTestId` - By `data-testid` attribute

## `waitFor`

## Jest DOM Matchers

The built-in Jest matchers work with any of JavaScripts native values, but none of them are designed to work specifically with DOM elements. By importing the `@testing-library/jest-dom` package at the beginning of a test file, new Jest matchers are added to `expect` for DOM elements.

### Black Box Assertions

These are common assertions made from a user's perspective:

| Matcher | Purpose |
| --- | --- |
| `expect(someElement).toBeVisible()` | Asserts that something is on the page and not obstructed. |
| `expect(someElement).toBeInTheDocument()` | Commonly combined with `.not` to assert that something isn't on the page. |
| `expect(someElement).toHaveTextContent(someRegexOrString)` | Asserts that an element contains a string or matches a regex. Use `/^text goes here$/` to do a precise match. |

### White Box Assertions

These are a little more dangerous because they look at the page implementation, not its actual content.

| Matcher | Purpose |
| --- | --- |
| `expect(someElement).toHaveAttribute(attributeName, attributeValue)` | Asserts that an element has an attribute with a particulary value |
| `expect(someElement).toHaveClass(className)` | Asserts that a class is present on an element |
| `expect(someElement).toHaveStyle(someCSSPropertyValuePairs)` | Asserts that an element has any number of CSS styles applied to it |

## Form Assertions

| Matcher | Purpose |
| --- | --- |
| `expect(someFormInput).toHaveValue(someValue)` | |
| `expect(someFormInput).toHaveFocus()` | |
| `expect(someForm).toHaveFormValues(someNameValuePairs)` | |
| `expect(someFormInput).toBeChecked()` | |

## Watch Out!

* If you're waiting for an element to appear in the DOM, use `find` queries, not `waitFor`
* There's a built-in DOM event library in `js-dom` called `fireEvent`. It works like this:

```js
fireEvent.click(someElement, eventDetails)
```

This requires very low-level mocking that gets dangerously close to reimplementing browser functionality. `userEvent` should be preferred for app testing.

## Additional Resources

| Resource | Description |
| --- | --- |
| [Guiding Principles](https://testing-library.com/docs/guiding-principles/) | Official principles of Testing Library |
| [Which query should I use?](https://testing-library.com/docs/queries/about/#priority) | Official Testing Library guide to choosing a query |
| [ARIA Roles](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles) | MDN's reference on different ARIA roles |
| [User Events](https://testing-library.com/docs/ecosystem-user-event/) | Official documentation on User Events |
