# Core Concepts Exploratory Group

The [directives](https://github.com/fhiso/core-concepts-eg/blob/master/DIRECTIVES.md) of the Core Concepts Exploratory Group (CCEG) state:

> The Core Concepts Exploratory Group... is tasked with carrying out [exploratory work](http://fhiso.org/tsc-opm/)... into the core genealogical concepts pertaining to persons, their intrinsic and extrinsic properties, the events in their lives, and the relationships they have with other persons.
> 
> The CCEG shall research, compare and document the approach to these concepts adopted by current applications and standards in wide-spread use. The CCEG may include other such applications, standards and research in this work as they see fit. ...
> 
> The CCEG shall draw on this research to reach a consensus on the broad manner in which these concepts are to be modelled in a future FHISO standard. Consideration shall be given to compatibility with existing data models (including GEDCOM) and the likely requirements for forwards compatibility. Areas requiring further research shall be identified, as should potential points of extensibility. Particular attention should be paid to those decisions likely to effect the work of other technical groups.

Our analysis will reside here in this repository and will be performed in two phases. First we will document and analyze the strengths and weaknesses of each model with regards to persons, events, and relationships. Then we will generate a project proposal for future work including "recommendations on major descisions" regarding the core concepts (see sections 4.1 and 4.2 of the [O&PM](http://fhiso.org/tsc-opm/)).

## Models

* [DeadEnds](deadends)
* [GEDCOM](gedcom)
* [GEDCOM X](gedcom-x)
* [GenTech](gentech)
* [GRAMPS](gramps)
* [STEMMA](stemma)

## Questions

This is a list of questions worth considering when documenting and analyzing the models listed above. It is not meant to be complete.

* Are relationships implicit from a family object (as per GEDCOM) or are the explicit links for types of relation?
* How do you cope with properties that change with time?
* Do individuals have properties directly, or can they only be expressed in events?
* Can events pertain to places instead of persons?
* Is there a difference between an "implicit" event (e.g. mention of a person implies their birth) and one explicitly described?
* If you have explicit relationship links, how (if at all) are they related to roles in events?
* What is the scope of event roles: are they defined per event type, or is a mother a mother independent of the event type?
* How are illegitimacy, adoption, same-sex marriage and polygamy handled?
* Which entities and properties are extensible?
* Should there be a way of describing the characteristics of vendor-extension properties, such as that a baptism date is often a reasonable approximation to a birth?
* Can a system make assumptions about the ordering of certain events?  If so, what happens if evidence places them out of order?
* Is there a notion of states (e.g. marriage) that are initiated and concluded by events?

## Contributing

Members of the CCEG are granted rights to modify anything in this repository. If you are not a member of the CCEG, or not even a member of [FHISO](http://fhiso.org/), you may still contribute by [forking](https://help.github.com/articles/fork-a-repo) this repository, modifying your copy, and then submitting a [pull request](https://help.github.com/articles/using-pull-requests).

Though our work will be contained here, our primary means of communication will be via the [Core Concepts](http://fhiso.org/mailman/listinfo/core-concepts_fhiso.org) mailing list.

All documents are written in the [markdown](https://help.github.com/articles/markdown-basics) format.

Modifications by CCEG members and pull requests from others should only be done with regards to the first phase of documentation and analysis. The mailing list will be the primary means of coordination during the second phase and as such all contributions should be discussed there.
