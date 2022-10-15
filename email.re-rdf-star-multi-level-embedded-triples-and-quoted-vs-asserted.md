---
id: bfgmv8cqozs5xu5j0kzw1zt
title: Re Rdf Star Multi Level Embedded Triples and Quoted Vs Asserted
desc: ''
updated: 1655098083169
created: 1655014406555
---



On 6/10/2022 6:05 AM, llSouripriya Das wrote:
> What would be the best ways to represent the two cases of the following sentence in RDF-star:
>       Alice heard that Bob knew that Cindy read, from email and in paper, that Dan adores Eve
> i.e.,
>       Alice heard []
>                           |
>                          Bob knew []
>                                            |
>                                            Cindy read {from email; in paper} []
>                                                                                                  |
>                                                                                                 Dan Adores Eve
>
> Case 1: The only asserted triple should be: Alice heard <something>. All the remaining triples (i.e., those that make up the <something> portion) should be quoted triples only (i.e., not asserted triples).
>
> Case 2: Every triple used to represent this sentence should be an asserted (i.e., not just quoted) triple.
>
> Thanks,
> Souri.
>

