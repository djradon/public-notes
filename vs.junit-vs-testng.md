---
id: 16sx7raudyttz69hx018hpl
title: Junit Vs Testng
desc: ''
updated: 1706407764924
created: 1706407053999
---

- Comparing TestNG Vs JUnit, TestNG annotations are easier to use and understand than JUnit. 
- "TestNG allows us to create parallel tests, whereas JUnit does not support running parallel tests."
  - but https://www.baeldung.com/junit-5-parallel-tests
-  In TestNG, Test cases can be grouped together, while in JUnit, Grouping tests together is not possible.
- "the declaration of @BeforeClass and @AfterClass method has to be static in JUnit. By comparison, TestNG method declaration doesn’t have these constraints."
- junit5's "@MethodSource – passes external methods generating streams:" seems awesome. could it take parameter streams from the network?