---
id: mlzjkg65ixezzrsyaf4a81z
title: There Is No Such Thing as a Unit Test
desc: ''
updated: 1730842568301
created: 1730840698421
---

- https://dev.to/awwsmm/there-is-no-such-thing-as-a-unit-test-50j3

## Highlights

- "Rather than thinking of tests along the traditional unit / integration / end-to-end spectrum, I think it's helpful to think along a few other dimensions

    is this test fast or slow?
    is this a black-box test or a white-box test?
    is this test informed by development or does it inform development?

### Fast and Slow Tests

#### Fast

- entirely in-memory. They do no disk IO and they make no network calls
- can be run every single time a code change is made without being a roadblock to development speed
- should therefore be run as part of the developer's [inner loop](https://www.awwsmm.com/blog/drop-everything-and-review). Every time you compile, you can run these tests

#### Slow

- take more than 2-5 seconds
- [Contract tests](https://testsigma.com/blog/api-contract-testing/) (which often spin up Docker containers) and performance tests (which may run gigabytes of data or thousands of requests through the system) are examples of slow tests
- before each commit to main is probably fine for tests shorter than a few minutes, daily or weekly might be a good cadence for tests much longer than that


### Black-Box and White-Box Tests

#### Black-box

- make no assumptions about the internals of the thing they are testing.
- provide inputs and assert on observable outputs, and that's it
- observable output is usually a return value from a method, but a black-box test might instead assert that a side effect has occurred, like that a log line has been written, or that a metric has been recorded, or that some state has been mutated
- opt for black-box tests as a default

#### White-box 

- *introspective*: test the internals, how something should happen
- Tests which have assertions like "when 'x' happens, function a() should call function b()"
- Tests which rely heavily on mocking frameworks are often white-box tests, asserting that such-and-such a method has (or hasn't) been called in response to some inputs

### Development-Informed Tests and Development-Informing Tests

#### Development-Informed Tests 

- written reactively, in that the production code is written first, and the tests are written afterward
- codify the behaviour of the system as-is
- traditional "unit tests" are almost exclusively development-informed tests ^6non5ssw9g7o
- Development-informed tests are often written by rote and offer little value.


#### Development-Informing Tests

- written proactively
- Test-Driven Development (TDD) is a software development methodology which encourages writing only development-informing tests, ensuring that 100% of the system's behaviour is always codified in tests. ^t22wchtkcs1o
- Development-informing tests can also provide confidence that some tricky piece of logic has been implemented correctly. For example, you might write a regex to parse U.S. phone numbers, and -- at the same time -- add a handful of tests to ensure that you catch things like

    area codes surrounded by parentheses
    spaces vs. no spaces vs. hyphens
    the presence or absence of a +1 country code
- always write bug fix tests in a development-informing way

### Most Unit Tests are Development-Informed

- most tests are not written to catch bugs, and they are not written to help a developer think through some difficult implementation

### Most Unit Tests do not test "Externally-Visible System Behaviours"

- the twin practices of (1) breaking large functions up into smaller ones and (2) writing tests for each function rather than for each externally-visible system behaviour leads to a proliferation of tests tightly-coupled to the production implementation
- In the worst-case scenario, developers will sometimes copy-and-paste the production implementation directly into the test, asserting that the "expected" result from the test implementation equals the "actual" result from the production code

### A New Test Pyramid

![](/assets/images/2024-11-05-13-20-51.png)

- base: Where external dependencies are required, prefer fake implementations rather than mocks (and add corresponding contract tests to ensure that external dependency behaves as you think it does). This keeps the entire test in-memory
- middle: Prefer slow black-box tests over fast white-box tests

## Comments

- 