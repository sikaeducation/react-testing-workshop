# What To Test: React Components

* What does the component do with its props?
* What other components does this component render, and what are their props?
* What state does the component have, and under what circumstances does that change change?
* What kinds of interactions can users have with the component?
* What happens when child components invoke callbacks I give them?

## What Not To Test

* Static text
* Don't test implementation details
  * The names of functions and variables
  * The APIs of internal functions
* Don't duplicate your implementation code in the test
* Don't test React
* Don't test any third-party code
* Anything that doesn't have an effect on a consumer
* Inline styles that aren't bound to anything
* Any external styles
* Anything that isn't the concern of this component

## What To Test

Test the contract of the component, which is the public API.

* Rendering
  * Child components
  * Props
* Internal state
  * Use equivalence partitions
  * Pay attention to combinations of state
* External state
  * Props
    * Use equivalence partitions
    * Are they required or optional
  * `context`
  * Different parents or children
* User actions - Clicks, keyboard input, dragging
  * Internal state change is visible
  * Prop functions are called correctly
* Branching Logic
  * Ternanies and boolean operators in templates
  * Ifs and Switches in the function body
* Styles that are bound to something
