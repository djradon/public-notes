---
id: c837gn6flz973mbgg1g66ny
title: Rule Engine
desc: ''
updated: 1692988394122
created: 1690558566709
---

- [[p.differentFrom]] [[t.cs.workflow]]
  - https://kissflow.com/workflow/workflow-engine-business-rule-engine-difference/
- #aka [[c.Software.DecisionEngine]]

## [[c.Implementation]]

### #c-sharp

- [[prdct.rulesengine]]
- [[prdct.dmn-engine]]
- [[prdct.json-rules-engine]]

## [[c.ValueProposition]]

- Business leaders with subject matter expertise can define and manage their own logic, independent of engineering.


## [[c.Resource]]

- https://www.youtube.com/watch?v=_tUzQP3Q0rA
- https://martinfowler.com/bliki/RulesEngine.html

### https://www.reddit.com/r/dotnet/comments/vq5280/microsoft_rulesengine_feedback_from_those_that/

some important caveats with rules engines in general:

1.  Need to be able to resolve conflicting rules in the engine itself - looks like RulesEngine does not natively handle this (not surprised, that's domain-specific.) You need an input validation layer that tells the user that their rule is invalid because it will never produce a successful result.
2.  Persisting rule state - if you have long-running workflows, i.e. the type that is common with event-sourcing, you have one of two methods for executing domain events against a rules engine: 1. replay all events against the rules engine each time a new event is received or 2. persist the "completion state" of each rule each time an event is persisted, and recover that as a separate snapshot. The challenge with the second approach is how you handle updating a rules set - we were able to invalidate individual rules using a hash signature while preserving the output values of rules that were unchanged.
3.  Adding new rulesets on the fly - if you want the ability to dynamically create new campaigns, you have to decide how you want to handle historical data. In our case, since we were a high volume streaming operation, our choice was to not retroactively apply older events when new rules were added as this would create a "thundering herd" problem for us. We only applied new rules to entities that processed new events after the additional rule-based campaigns were defined.


## [[p.vs]] [[t.cs.workflow]]

| **Workflow Engine** |  **Business Engine** |
| --- | --- |
|    Based on process |    Based on rules |
| Specific to a workflow | Enterprise specific |
| A program designed to run workflow instances based on the process model | A program designed to help with complex decision-making |
| Inherent driving force in an [automated workflow](https://kissflow.com/workflow/workflow-automation/) | Works as a pluggable element that could be separated from the application code |
| Help with carrying out a business process | Help with creating business knowledge |



## [[c.Implementation]]

- [[prdct.dmn-engine]]