# Event

An event represent "a description of a historical event".

name  | description | data type | constraints
------|-------------|-----------|------------
type | Enumerated value identifying the type of the event. | [Enumerated Value](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#enumerated-value) | OPTIONAL. If provided, MUST identify an event type, and use of a [known event type](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#known-event-types) is RECOMMENDED.
date | The date of the event. | [`http://gedcomx.org/v1/Date`](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#conclusion-date) | OPTIONAL.
place | A reference to the place applicable to this event. | [`http://gedcomx.org/v1/PlaceReference`](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#conclusion-place-reference) | OPTIONAL.
roles | Information about how persons participated in the event. | List of [`http://gedcomx.org/v1/EventRole`](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#conclusion-event-role). Order is preserved. | OPTIONAL.

## Notes

Events are very similar to facts. The first major difference is that events are top-level entities associated with one or many people via roles while facts are not top-level and are directly associated to only one person or relationship. Relationships and facts can be inferred from events but there is no direct association between them. Events and facts have the same enumerated list of types. Read more about [events and facts](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#events-vs-facts).

The concept of events appears to not be well developed. It is said that relationships can be inferred from events, but the event roles are not described well enough to make it obvious how that could happen. [Role types](https://github.com/FamilySearch/gedcomx/blob/master/specifications/conceptual-model-specification.md#3151-known-role-types) are currently limited to `Principal`, `Participant`, `Official`, and `Witness`. The person being born would be the `Principal`, but what about the parents? The spec gives no direction on this. It seems as though they should be modeled with the role of `Particpant` but you could also argue `Witness`. More explicit roles such as `Child`, `Parent`, `Spouse`, etc would be helpful.