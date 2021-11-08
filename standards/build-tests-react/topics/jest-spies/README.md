# Jest: Spies

## Spies

```js
const someSpy = jest.fn()
```

## Stubbing

With a stubbed implementation:

```js
const someSpy = jest.fn(() => "Hi")
```

With a mocked implementation:

```js
const someSpy = jest.fn((parameter1, parameter2) => {
  return parameter1 + parameter2
})
```

Returing different values on different calls:

```js
const someSpy = jest.fn(() => 0) // Fourth call and onward
  .mockReturnValueOnce(1) // First call
  .mockReturnValueOnce(2) // Second call
  .mockReturnValueOnce(3) // Third call
```

Wrapping the spy in a promise:

```js
const someSpy = jest.fn().mockResolvedValue({ result: "success" })
const someSpy = jest.fn()
  .mockResolvedValueOnce({ result: "1" }) // First call
  .mockResolvedValueOnce({ result: "2" }) // Second call
  .mockResolvedValueOnce({ result: "3" }) // Third call

const someSpy = jest.fn().mockRejectedValue({ error: "Uh oh" })
const someSpy = jest.fn()
  .mockRejectedValueOnce({ error: "1" }) // First call
  .mockRejectedValueOnce({ error: "2" }) // Second call
  .mockRejectedValueOnce({ error: "3" }) // Third call
```

You can inspect call and return values directly with `someSpy.mock`:

* **`someSpy.mock.calls`**: An array of arrays with all arguments the spy has been called with
* **`someSpy.mock.results`**: An array with all return values the spy has been called with

```js
const additionSpy = jest.fn((numberOne, numberTwo) => numberOne + numberTwo)
additionSpy(1, 2)
additionSpy(3, 4)
additionSpy(5, 6)
console.log(addSpy.mock.calls) // [[1, 2], [3, 4], [5, 6]]
console.log(addSpy.mock.results) // [3, 7, 11]
```

## Spy Matchers

| Matcher | Purpose |
| --- | --- |
| `expect(someSpy).toHaveBeenCalled()` | |
| `expect(someSpy).toHaveBeenCalledWith(firstArgument, secondArgument, thirdArgument)` | |
| `expect(someSpy).toHaveBeenCalledTimes(invocationCount)` | |
| `expect(someSpy).toHaveBeenNthCalledWith(invocationNumber, firstArgument, secondArgument)` | |

## Watch Out

* Don't make assertions on the `.calls` or `.result`, use the appropriate matcher

## Additional Resources

| Resource | Description |
| --- | --- |
| [Jest `expect` API](https://jestjs.io/docs/en/expect) | Official reference for Jest matchers. |
