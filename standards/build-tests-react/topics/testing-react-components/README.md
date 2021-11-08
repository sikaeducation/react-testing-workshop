# Testing React Components with Jest

## Installation and Configuration

### Create React App

If you're using Create React App, `jest`, `@testing-library/react`, `@testing-library/jest-dom`, and `@testing-library/user-event` are already installed and configured.

Any file in any level of the `/src` directory that ends in `.test.js` will be run when `npm test` is run.

### Existing React Apps

To set up testing for an existing React project, install the following dependencies:

```bash
npm i -D jest @testing-library/react @testing-library/jest-dom @testing-library/user-event
```

Then define a testing script in the project's `package.json`:

```json
{
  "scripts": {
    "test": "jest src/**/*.test.js"
  }
}
```

## Creating Tests

To create a test, add a file ending in `.test.js` to the `src` directory. By convention, it's common to have one test file per component file, and they should both be named the same as the component. For example, a component called `LoginForm` should be in a file called `LoginForm.js` and have a test file called `LoginForm.test.js`. There are no requirements for where any of these files live in the folder hierarchy, but it's conventional to put the component file and its test file in the same place.

A simple test file imports the component being tested, as well as testing functions as needed:

```jsx
import SomeComponent from "./SomeComponent"
import { render, screen } from "@testing-library/react"

test("Test name goes here", () => {
  render(<SomeComponent>)

  const someElement = screen.getByRole("header")

  expect(someElement).toBeInTheDocument()
})
```

It's not necessary to import `jest`, `test`, `describe`, `it`, `beforeAll`, or `expect`. They will added to the environment by Jest when running the tests.

## Basic Parts of React Component Test

### `render`

Components are added to the test DOM with with the `render` method:

```jsx
render(<p>Hi!</p>)
render(<SomeComponent someProp="Some Value" />
```

Note that you can pass elements, components, and even entire hierarchies into `render`:

```jsx
render(
  <SomeContext.Provider value="Hi!">
    <div>
      <SomeComponent someProp="Aloha!" />
    </div>
  </SomeContext.Provider>
)
```

### `screen`

DOM elements are retrieved by querying `screen`:

```jsx
const element = screen.findByRole("Heading")
```

This element is a regular DOM element rather than a component instance. Rather than running assertions on parts of the element, it's common to use the Jest matchers that are added by `@testing-library/jest-dom`.

### `waitFor`

When a component responds to a change and rerenders, it does this asynchronously. This should be handled by wrapping a query in the `waitFor` function exported by `@testing-library/react` library and awaiting it:

```jsx
import { render, screen, waitFor } from "@testing-library/react"
import { click } from "@testing-library/user-event"
import SomeComponent from "./SomeComponent"

test("loads and displays greeting", async () => {
  render(<SomeComponent url="/greeting" />)

  const greetingButton = screen.getByText('Load Greeting')
  click(greetingButton)

  await waitFor(() => screen.getByRole('heading'))

  expect(screen.getByRole('heading')).toHaveTextContent('hello there')
  expect(screen.getByRole('button')).toBeDisabled()
})
```

Within tests, always use `async`/`await` rather than `.then`/`.catch`. The enhanced readability of error handling in `.then`/`.catch` chains isn't useful in tests since all errors are automatically handled by the testing framework.

## Rerendering

Occasionally, it may be useful to test how a component re-renders. To do this, destructure the `rerender` function out of the original call to `render`. This accepts a new JSX element.

```jsx
import { render, screen, waitFor } from "@testing-library/react"
import { click } from "@testing-library/user-event"
import SomeComponent from "./SomeComponent"

test("loads and displays greeting", async () => {
  const { rerender } = render(<SomeComponent url="/greeting" />)

  expect(screen.getByRole('heading')).toHaveTextContent('hello there')

  rerender(<SomeComponent url="/greeting" />)

  expect(screen.getByRole('heading')).toHaveTextContent('hello there')
})
```

## Running Tests

To run tests, run `npm test`. The `jest` test runner will automatically keep running and wait for changes and rerun the tests in response.

## Testing Async Code

Async code in tests can either use `async`/`await` or return a promise (but shouldn't do both)

## Watch Out!

* `@testing-library/jest-dom` (which adds DOM matchers to Jest) is automatically imported into each test with Create React App, but must be added if you're configuring testing manually.
* `render` is a function, `screen` is an object
* You only need to `waitFor` one query, even if you're waiting for multiple changes to render.

## Additional Resources

| Resource | Description |
| --- | --- |
| [CRA: Running Tests](https://create-react-app.dev/docs/running-tests/) | Create React App's guide to testing |
| [Configuring Jest](https://jestjs.io/docs/configuration) | Guide to configuring Jest |
