# Fact

A fact represents "a data item that is presumed to be true about a specific subject".

name  | description | data type | constraints
------|-------------|-----------|------------
type | Enumerated value identifying the type of the fact. | [Enumerated Value](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#enumerated-value) | REQUIRED. MUST identify a fact type, and use of a [known fact type](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#known-fact-types) is RECOMMENDED.
date | The date of applicability of the fact. | [`http://gedcomx.org/v1/Date`](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#conclusion-date) | OPTIONAL.
place | A reference to the place applicable to this fact. | [`http://gedcomx.org/v1/PlaceReference`](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#conclusion-place-reference) | OPTIONAL.
value | The value of the fact. | string | OPTIONAL.
qualifiers | Qualifiers to add additional details about the fact. | List of [http://gedcomx.org/v1/Qualifier](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#qualifier) | OPTIONAL. If present, use of a [known fact qualifier](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#known-fact-qualifier) is RECOMMENDED.

## Notes

Facts can only be associated with persons and relationships.

Some information that is "presumed to be true" about persons, such as names and gender, are not facts.