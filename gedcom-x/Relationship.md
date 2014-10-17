# Relationship

name  | description | data type | constraints
------|-------------|-----------|------------
type | Enumerated value identifying the type of the relationship. | [Enumerated Value](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#enumerated-value) | OPTIONAL. If provided, MUST identify a relationship type, and use of a [known relationship type](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#known-relationship-types) is RECOMMENDED.
person1 | Reference to the first person in the relationship. | [URI](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#uri) | REQUIRED. MUST resolve to an instance of [`http://gedcomx.org/v1/Person`](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#person)
person2 | Reference to the second person in the relationship. | [URI](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#uri) | REQUIRED. MUST resolve to an instance of [`http://gedcomx.org/v1/Person`](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#person)
facts | The facts about the relationship. | List of [`http://gedcomx.org/v1/Fact`](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#fact-conclusion). Order is preserved. | OPTIONAL.

## Notes

Relationships are strictly binary (limited to only two people).

It is recommended that relationships be limited to an enumerated list of known types which at this time only includes `Couple` and `ParentChild`.

Some relationships are directional, such as `ParentChild` relationships (`person1` is the parent and `person2` is the child).

Relationships can have a list of facts associated with it. For `Couple` you would add marriage events here. But for `ParentChild` relationships you wouldn't necessarily add birth events because it would seem more fitting to have that information stored on the person and not duplicated two more times in each relationship with each parent.