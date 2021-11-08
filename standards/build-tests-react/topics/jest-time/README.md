# Jest: Mocking Time

```js
// Both of these affect timers globally in all tests until reset
jest.useFakeTimers() // Needs to be called every time to reset tests
jest.useRealTimers()

jest.runAllTimers() // Waits for all timers to finish
jest.runOnlyPendingTimers() // Waits for all timers to finish, but not any new timers that get started
jest.advanceTimersByTime(1000) // Set an explicit time
jest.clearAllTimers() // Wipes the buffers
```

