# GEDCOM X

GEDCOM X is a set of open specifications for exchanging genealogical data. The proejct is sponsored by FamilySearch. The [full spec](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md) is available on GitHub.

### Table of Contents

1. Model
    1. Person
    2. Relationship
    3. Fact
    4. Events 
2. Use Cases
3. Analysis

## Model

### Person

A [Person](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#person) has four basic properties:

name  | description | data type | constraints
------|-------------|-----------|------------
private | Whether this instance of `Person` has been designated for limited distribution or display. | boolean | OPTIONAL. A description of how implementations should use private data is outside the scope of this specification.
gender | The gender of the person. | [`http://gedcomx.org/v1/Gender`](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#gender) | OPTIONAL.
names | The names of the person. | List of [`http://gedcomx.org/v1/Name`](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#name-conclusion). Order is preserved. | OPTIONAL.  If more than one name is provided, names are assumed to be given in order of preference, with the most preferred name in the first position in the list.
facts | The facts of the person. | List of [`http://gedcomx.org/v1/Fact`](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#fact-conclusion). Order is preserved. | OPTIONAL.

#### Notes

Facts are not events even though they have place and date attributes.

Names are not facts.

Gender is not a fact.

### Relationship

name  | description | data type | constraints
------|-------------|-----------|------------
type | Enumerated value identifying the type of the relationship. | [Enumerated Value](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#enumerated-value) | OPTIONAL. If provided, MUST identify a relationship type, and use of a [known relationship type](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#known-relationship-types) is RECOMMENDED.
person1 | Reference to the first person in the relationship. | [URI](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#uri) | REQUIRED. MUST resolve to an instance of [`http://gedcomx.org/v1/Person`](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#person)
person2 | Reference to the second person in the relationship. | [URI](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#uri) | REQUIRED. MUST resolve to an instance of [`http://gedcomx.org/v1/Person`](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#person)
facts | The facts about the relationship. | List of [`http://gedcomx.org/v1/Fact`](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#fact-conclusion). Order is preserved. | OPTIONAL.

#### Notes

Relationships are strictly binary (limited to only two people).

It is recommended that relationships be limited to an enumerated list of known types which at this time only includes `Couple` and `ParentChild`.

Some relationships are directional, such as `ParentChild` relationships (`person1` is the parent and `person2` is the child).

Relationships can have a list of facts associated with it. For `Couple` you would add marriage events here. But for `ParentChild` relationships you wouldn't necessarily add birth events because it would seem more fitting to have that information stored on the person and not duplicated two more times in each relationship with each parent.

### Fact

A fact represents "a data item that is presumed to be true about a specific subject".

name  | description | data type | constraints
------|-------------|-----------|------------
type | Enumerated value identifying the type of the fact. | [Enumerated Value](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#enumerated-value) | REQUIRED. MUST identify a fact type, and use of a [known fact type](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#known-fact-types) is RECOMMENDED.
date | The date of applicability of the fact. | [`http://gedcomx.org/v1/Date`](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#conclusion-date) | OPTIONAL.
place | A reference to the place applicable to this fact. | [`http://gedcomx.org/v1/PlaceReference`](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#conclusion-place-reference) | OPTIONAL.
value | The value of the fact. | string | OPTIONAL.
qualifiers | Qualifiers to add additional details about the fact. | List of [http://gedcomx.org/v1/Qualifier](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#qualifier) | OPTIONAL. If present, use of a [known fact qualifier](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#known-fact-qualifier) is RECOMMENDED.

#### Notes

Facts can only be associated with persons and relationships.

Some information that is "presumed to be true" about persons, such as names and gender, are not facts.


### Event

An event represent "a description of a historical event".

name  | description | data type | constraints
------|-------------|-----------|------------
type | Enumerated value identifying the type of the event. | [Enumerated Value](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#enumerated-value) | OPTIONAL. If provided, MUST identify an event type, and use of a [known event type](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#known-event-types) is RECOMMENDED.
date | The date of the event. | [`http://gedcomx.org/v1/Date`](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#conclusion-date) | OPTIONAL.
place | A reference to the place applicable to this event. | [`http://gedcomx.org/v1/PlaceReference`](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#conclusion-place-reference) | OPTIONAL.
roles | Information about how persons participated in the event. | List of [`http://gedcomx.org/v1/EventRole`](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#conclusion-event-role). Order is preserved. | OPTIONAL.

#### Notes

Events are very similar to facts. The first major difference is that events are top-level entities associated with one or many people via roles while facts are not top-level and are directly associated to only one person or relationship. Relationships and facts can be inferred from events but there is no direct association between them. Events and facts have the same enumerated list of types. Read more about [events and facts](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#events-vs-facts).

The concept of events appears to not be well developed. It is said that relationships can be inferred from events, but the event roles are not described well enough to make it obvious how that could happen. [Role types](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#3151-known-role-types) are currently limited to `Principal`, `Participant`, `Official`, and `Witness`. The person being born would be the `Principal`, but what about the parents? The spec gives no direction on this. It seems as though they should be modeled with the role of `Particpant` but you could also argue `Witness`. More explicit roles such as `Child`, `Parent`, `Spouse`, etc would be helpful.

View a [diagram](Data_Model.svg) of the core data model.

## Use Cases

Something in the future hear about how it handles the list of uses cases which we don't have yet.

## Analysis

Our analysis of it's strengths and weaknesses.
