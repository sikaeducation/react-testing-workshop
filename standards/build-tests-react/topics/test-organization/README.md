# Test Organization with Jest

### Grouping Tests with `describe()` and `it()`

`test()` is good for small, isolated behaviors. Often, you're describing multiple characteristics of the same part of the system. In this case, you can group tests with `describe()` and write individual test cases inside `it()`.

### Setting Up Tests With `beforeEach()`

Each `describe()` function can call a `beforeEach()` function that will run before all of its tests. This is used to navigate to the correct page, initialize objects, or otherwise set up the system for testing.

```js
describe("sum", () => {
  beforeEach(() => {
  })
  it("something", () => {
  })
  it("something", () => {
  })
  it("something", () => {
  })
})
```

Organize your tests in given/when/then format to simplify their reading.

Compose test setup with functions. `beforeEach` has a place, but not as a tool for code reuse.

Keep test files small, prefer them as a unit of organization over lots of describes and nesting.

Don't rely on test sequence. No mutable state!

* AHA - Avoid hasty abstractions. In test code, use as little abstraction as possible. You should be able to see everything you need to run the test at once.

### Watch Out!

* `describe()` functions can be nested within each other to create subgroups of tests. `test()` and `it()` functions always represent individual tests and cannot be nested.
* Any one test can have as many assertions as you like, but be careful about asserting too many things in one test. Each test should represent one reason why the system could fail. If you use multiple assertions in a test, they should all fail for the same reason.
* There are `after` and `afterAll` hooks, but they should be avoided as there is no guarantee they will run. Initial conditions for the test should be ensured in `before` and `beforeAll` hooks.
* Tests should be able to run in any order. That means one test shouldn't rely on the state from another test. Use `beforeEach` to reuse setup logic.
