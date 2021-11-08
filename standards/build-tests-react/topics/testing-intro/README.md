# Intro to Testing

Tests verify that something does what you think it does.

Some examples of tests:

* Pulling up an app, clicking a button, checking that the right screen loads
* Console logging that a function is getting called
* Checking that something runs without changing another value
* Writing code that automates any of the above

Just about every dev tests their code. It's almost impossible not to! The difference between most devs and a quality-focused engineer is that they're disciplined about their tests and use them to guide their development. They can use tools that help them write more accurate tests and run them automatically, giving them real-time feedback about their code. So why don't more people do it?

* You have to get _fast_ at testing tools. A `console.log` is always going to be right there. If installing and configuring testing tools is awkward, if the syntax requires you to look a ton of stuff up, if you're constantly fighting with the testing tools, you won't use them. Period.
* Most books, blog posts, and advice rely too heavily on unit tests. They're a very valuable piece of the puzzle, but they're so close to the code that they can change really quickly, meaning you throw away tests nearly as quickly as you write them. This can be disheartening.
* It's hard to know what's actually valuable to test. The tests that are easiest to write often are the least useful, and TDD in particular relies on being able to predict what you'll eventually need. This takes some experience.
* There's always more features to write. It's easy to fall into the trap of thinking that testing slows down development. It absolutely does... at first. As soon as the app gets too big too hold the entire thing in your head at the same time, it's the only thing that will enable speed.
* If you're adding the tests to code that already exists, there's a decent chance the code will very difficult to write good tests for. It's difficult to write spaghetti code with tests, and all-too-easy to write it without them.

Tests are design

Tests are confidence

Test are documentation - Can you look at the test and figure out how it works? Use real examples, not foo/bar/baz. This helps with documentation.

AHA - Avoid hasty abstractions. In test code, use as little abstraction as possible. You should be able to see everything you need to run the test at once.

Don't test implementation details. This is anything a user can't see. For some things, that's another developer consuming the component, for others that end users interacting with the component. It includes class names, stateful variables, etc. Tests shouldn't break when you refactor.

Tests should break when the app breaks.

What would be bad if it didn't work? What steps would you go through to ensure it worked? Those are the steps of your test.

Don't have arbitrary waits in tests

Don't reimplement logic

Tests are a conversation with your code. Tests don't guarantee your code will work, and you might not write your test right the first time. It's one of the reasons it's usually not effective for different people to write the tests and hand them off to someone to make them pass.

Try to avoid running your code by hand

Testing leads to better design by encouraging decoupling. Coupled apps are difficult to test.

Specification by example
