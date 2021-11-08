# Intro to Jest

Jest was an attempt to make an all-in-one testing tool. The problem with JS testing was that writing tests had increasingly come to rely on installing Mocha, Chai, Sinon, and a bunch of plugins. Also, the Chai `expect` grammar was difficult to learn. Jest was designed to be an all-in-one tool that could replace all of them while being familiar to existing users:

```js
describe("A group of tests", () => {
  it("is a test", () => {
    expect(1).toBe(1)
  })
  it("is another test", () => {
    const mockFunction = jest.fn(() => {})
    mockFunction()
    expect(mockFunction).toHaveBeenCalledTimes(1)
  })
})
```

## Installing

## Configuring

## `test()`

The simplest way to declare a test in Jest is to use the `test()` function:

```js
test("Name of test goes here", () => {
  // Assert something about the application here
})
```

When the tests are run, the name of the test will display with a red X or green checkmark. The name should describe the desired behavior of the system in plain language.

```js
test("adding two odd numbers")
test("adding two even numbers")
```
## `expect().toEqual`

