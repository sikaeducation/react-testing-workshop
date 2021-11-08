# Testing User Actions with Jest

To take actions on an app, use the `userEvent` library:

## Installation

```bash
npm install --save-dev @testing-library/user-event
```

## Events

```js
import {
  click,
  dblClick,
  type,
  keyboard,
  upload,
  clear,
  tab,
  selectOptions,
  deselectOptions,
} from "@testing-library/user-event"
```

```js
click(someElement)
dblClick(someElement)
keyboard(contents, { delay: delayInMilliseconds }) // Used for keyboard events outside of text inputs
tab({shift: shouldHoldShift, focusTrap: elementToRestrictTabbingTo })

// Forms
type(someInputOrTextArea, contents, { delay: delayInMilliseconds }) // Using delay will make it async, has many special character options
clear(someElement) // Clears a form input
selectOptions(someElement, values) // Selects `<option>`s from a `<select>`
```

[List of special characters for typing](https://testing-library.com/docs/ecosystem-user-event/#specialchars)
