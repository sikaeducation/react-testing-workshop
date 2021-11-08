# Mocking Objects with Jest

### Write tests that mock modules

1. Import the module in the test file
2. `jest.mock(module)` the module
3. `module.someFunction.mockResolvedValue(response)

### Write tests that mock built-in modules

```js
global.fetch = jest.fn(() => (
  Promise.resolve({
    json: () => Promise.resolve({ someKey: "some value" })
  })
))

beforeEach(() => {
  fetch.mockClear()
})

fetch.mockImplementationOnce(() => Promise.reject("Problem"))
```

* [Blog: Mock Fetch in Jest](https://www.leighhalliday.com/mock-fetch-jest)

