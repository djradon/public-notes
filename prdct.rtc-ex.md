---
id: jc8fv59is3vyq5uo1e42efi
title: RTC.ex
desc: 'provides an API for working with ontogen-based compounds/virtual graphs'
updated: 1723653909895
created: 1723653436786
---

- written-in: [[prdct.elixir]]

## Example

```elixir
# create a new compound with a couple triples
virtual_graph =  
  [  
    {EX.Employee38, EX.firstName(), "John"},  
    {EX.Employee38, EX.familyName(), "Smith"},  
    {EX.Employee38, EX.jobTitle(), "Assistant Designer"},  
  ] 
  |> RTC.Compound.new(EX.Compound, prefixes: [ex: EX])  

# add some triples to the compound
virtual_graph =  
  RTC.Compound.add(virtual_graph,   
    EX.Employee39  
    |> EX.firstName("Jane")  
    |> EX.familyName("Doe")  
    |> EX.jobTitle("HR Manager")  
  )  

# add some statements about the compound itself
virtual_graph =  
  RTC.Compound.add_annotations(virtual_graph,  
    %{EX.dataSource() => EX.DataSource}  
  )
```

- With the RTC.Compound.graph(virtual_graph) function, the pure set of statements can be produced as an RDF.Graph at any time, which in this case generates this graph:

```turtle
@prefix ex: <http://example.com/> .

ex:Employee38
    ex:familyName "Smith" ;
    ex:firstName "John" ;
    ex:jobTitle "Assistant Designer" .

ex:Employee39
    ex:familyName "Doe" ;
    ex:firstName "Jane" ;
    ex:jobTitle "HR Manager" .
```

Whereas RTC.Compound.to_rdf(virtual_graph) provides the complete RDF-star graph with the RTC annotations for the compounds.

```turtle
@prefix ex: <http://example.com/> .
@prefix rtc: <https://w3id.org/rtc#> .

ex:Compound
    ex:dataSource ex:DataSource .

ex:Employee38
    ex:familyName "Smith" {| rtc:elementOf ex:Compound |} ;
    ex:firstName "John" {| rtc:elementOf ex:Compound |} ;
    ex:jobTitle "Assistant Designer" {| rtc:elementOf ex:Compound |} .

ex:Employee39
    ex:familyName "Doe" {| rtc:elementOf ex:Compound |} ;
    ex:firstName "Jane" {| rtc:elementOf ex:Compound |} ;
    ex:jobTitle "HR Manager" {| rtc:elementOf ex:Compound |} .
```


## References

- [[ar.ontogen.introducing-ontogen]]