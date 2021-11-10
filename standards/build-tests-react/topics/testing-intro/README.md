# Intro to Testing

Tests verify that something does what you think it does.

Some examples of tests:

* Pulling up an app, clicking a button, checking that the right screen loads
* Console logging that a function is getting called
* Checking that something runs without changing another value
* Writing code that automates any of the above

Just about every dev tests their code. It's almost impossible not to! The difference between most devs and a quality-focused engineer is that they're disciplined about their tests and use them to guide their development. They can use tools that help them write more accurate tests and run them automatically, giving them real-time feedback about their code.

## Why Write Tests?

* **Testing is a design activity**. This is admittedly counter-intuitive. By writing tests before you write you code, you are forced to define the interface for the code you want to test. This naturally leads to decoupled and modular design, which is beneficial in other ways. 
* **Tests are confidence**. Tests allow you to fearlessly change your code. You can delete files, rework implementations, and try alternatives and get instant feedback from your tests about what is no longer working.
* **Test are documentation**. Tests are executable examples of how your code works, and it's not possible for your tests and your actual code to get out of sync.
* **Tests run your code.** One of the most time-consuming parts of developing software is manually testing your code as you're writing it. Tests do this automatically.

## Levels of Test

* **High-Level Tests**: Sometimes called end-to-end (E2E) or UI tests. These simulate how a user uses an application. For web apps, this means opening a browser, going to a URL, clicking and typing, and asserting that things are visible on the string.
* **Mid-Level Tests**: Often called integration tests. These test significant pieces of your app, like features. These are generally combinations of smaller pieces of code, and are tested by isolating that part of the code and asserting that data and behavior move through them correctly.
* **Low-Level Tests**: Often called unit tests. These run the smallest parts of your code, like functions and methods, and assert that correct values are returned or state changes occur.
* **Static Tests**: These are done via types. A lot of behavior can be verified by limiting what types are allowed to be used in your code.

## Why Don't Developers Write Tests?

So why don't more people do it?

* You have to get _fast_ at testing tools. A `console.log` is always going to be right there. If installing and configuring testing tools is awkward, if the syntax requires you to look a ton of stuff up, if you're constantly fighting with the testing tools, you won't use them.
* Most books, blog posts, and advice rely too heavily on unit tests. They're a very valuable piece of the puzzle, but they're so close to the code that they can change really quickly, meaning you throw away tests nearly as quickly as you write them. This can be disheartening.
* It's hard to know what's actually valuable to test. The tests that are easiest to write often are the least useful, and TDD in particular relies on being able to predict what you'll eventually need. This takes some experience.
* There's always more features to write. It's easy to fall into the trap of thinking that testing slows down development. It absolutely does... at first. As soon as the app gets too big too hold the entire thing in your head at the same time, it's the only thing that will enable speed.
* If you're adding the tests to code that already exists, there's a decent chance the code will very difficult to write good tests for. It's difficult to write spaghetti code with tests, and all-too-easy to write it without them.

## What To Test

What would be bad if it didn't work? What steps would you go through to ensure it worked? Those are the steps of your test.

## What Not Test

Don't test implementation details. This is anything a user can't see. For some things, that's another developer consuming the component, for others that end users interacting with the component. It includes class names, stateful variables, etc.

## Qualities of Good Test Code

* Don't reimplement logic
* AHA - Avoid hasty abstractions. In test code, use as little abstraction as possible. You should be able to see everything you need to run the test at once.
* Tests should break when the app breaks.
* Tests shouldn't break when you refactor.
* Don't have arbitrary waits in tests
* Can you look at the test and figure out how it works?

Tests are a conversation with your code. Tests don't guarantee your code will work, and you might not write your test right the first time. It's one of the reasons it's usually not effective for different people to write the tests and hand them off to someone to make them pass.

## Additional Resources

| Resource | Description |
| --- | --- |
| [Test Automation Panda](https://automationpanda.com/) | Outstanding blog full of articles on testing techniques and philosophy |
| [The Testing Trophy and Testing Classifications](https://kentcdodds.com/blog/the-testing-trophy-and-testing-classifications) | Kent C. Dodd's blog post on different types of testing. |
