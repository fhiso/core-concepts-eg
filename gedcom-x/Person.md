# Person

A [Person](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#person) has four basic properties:

name  | description | data type | constraints
------|-------------|-----------|------------
private | Whether this instance of `Person` has been designated for limited distribution or display. | boolean | OPTIONAL. A description of how implementations should use private data is outside the scope of this specification.
gender | The gender of the person. | [`http://gedcomx.org/v1/Gender`](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#gender) | OPTIONAL.
names | The names of the person. | List of [`http://gedcomx.org/v1/Name`](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#name-conclusion). Order is preserved. | OPTIONAL.  If more than one name is provided, names are assumed to be given in order of preference, with the most preferred name in the first position in the list.
facts | The facts of the person. | List of [`http://gedcomx.org/v1/Fact`](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#fact-conclusion). Order is preserved. | OPTIONAL.

## Notes

Facts are not events even though they have place and date attributes.

Names are not facts.

Gender is not a fact.