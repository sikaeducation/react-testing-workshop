# Test Naming

Test names should describe:

* What's being tested
* What behavior it should be have
* Under which conditions

Describe the behavior that's being tested, don't just repeat the contents of the assertion.

## Naming Styles

### Simple Test Naming

`{name of what's being tested} {result} {behavior}`

```js
test("add returns sum when given two positive integers", () => {
  // Test code
})
```

### RSpec-style Naming 

Static methods start with `.`, instance methods start with `#`

```ruby
describe Math do
  describe "#add" do
    it "returns sum when given two postive integers" do
      # Test code
    end
  end
end
```

### XUnit-style Naming

* Test is the method name
* Sections are separated by underscores

```java
class MathTests {
  public void Add_ReturnsSum_WhenGivenTwoPositiveIntegers(){
    // Test code
  }
}
```
