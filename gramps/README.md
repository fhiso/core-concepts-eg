# Gramps

Gramps is a genealogy program that is both intuitive for hobbyists and feature-complete for professional genealogists. It is a community project, created, developed and governed by genealogists.

### Table of Contents

1. [Model](#model)
    1. [Primary](#primary)
    2. [Person](#person)
    3. [Family](#family)
    4. [Event](#event)
    5. [LdsOrd](#ldsord)
    6. [Attribute](#attribute)
    7. [EventRef](#eventref)
    8. [ChildRef](#childref)
    9. [PersonRef](#personref)
2. [Use Cases](#use-cases)
    1. [Single Person](#single-person)
    2. [Simple Family](#simple-family)
    3. [Multiple Marriages](#multiple-marriages)
    4. [Never Married](#never-married)
    5. [Child out of Wedlock](#child-out-of-wedlock)
3. [Analysis](#analysis)

## Model

There is a [diagram](Data_Model.svg) which shows the core objects in the model.

Further information is available on the Gramps website:

* [RELAX NG schema](https://gramps-project.org/xml/1.6.0/grampsxml.rng)
* [Full data model](https://gramps-project.org/wiki/index.php?title=Gramps_Data_Model)
* [Database API](https://gramps-project.org/wiki/index.php?title=Using_database_API)

### Primary

Primary objects are top-level entities.

name  | description | data type | constraints
------|-------------|-----------|------------
handle | Primary key. | ID | REQUIRED.
change | Last modification time. | timestamp | REQUIRED.
id | Human readable unique identifier. | string | OPTIONAL.
priv | Privacy flag. | boolean | OPTIONAL.

### Person

Extends: [Primary](#primary)

Person objects hold information about an individual.

name  | description | data type | constraints
------|-------------|-----------|------------
gender | The gender of this person. | string | REQUIRED. M=Male, F=Female or U=Unknown.
name | A list of personal names. | Name[] | OPTIONAL.
eventref | A list of event references. | EventRef[] | OPTIONAL.
lds_ord | A list of LDS ordinances. | LdsOrd[] | OPTIONAL.
objref | A list of media references. | MediaRef[] | OPTIONAL.
address | A list of addresses. | Address[] | OPTIONAL.
attribute | A list of attributes. | Attribute[] | OPTIONAL.
url | A list of Urls. | Url[] | OPTIONAL.
childof | Links to families where this person is a child. | ID[] | OPTIONAL.
parentin | Links to families where this person is a parent. | ID[] | OPTIONAL.
personref | A list of person references. | PersonRef[] | OPTIONAL.
noteref | A list of note handles. | ID[] | OPTIONAL.
citationref | A list of citation handles. | ID[] | OPTIONAL.
tagref | A list of tag handles. | ID[] | OPTIONAL.

### Family

Extends: [Primary](#primary)

Family objects are used to define the relationship between a mother, father and their children.

name  | description | data type | constraints
------|-------------|-----------|------------
rel | Family relationship. | FamilyRelType | OPTIONAL.
father | Link to father. | ID | OPTIONAL.
mother | Link to mother. | ID | OPTIONAL.
eventref | A list of event references. | EventRef[] | OPTIONAL.
lds_ord | A list of LDS ordinances. | LdsOrd[] | OPTIONAL.
objref | A list of media references. | MediaRef[] | OPTIONAL.
childref | A list of child references. | ChildRef[] | OPTIONAL.
attribute | A list of attributes. | Attribute[] | OPTIONAL.
noteref | A list of note handles. | ID[] | OPTIONAL.
citationref | A list of citation handles. | ID[] | OPTIONAL.
tagref | A list of tag handles. | ID[] | OPTIONAL.

### Event

Extends: [Primary](#primary)

Event objects are used to record something that happened at a particular time and place.

name  | description | data type | constraints
------|-------------|-----------|------------
type | Type of event. | EventType | REQUIRED.
date | Date that the event occurred. | Date | OPTIONAL.
place | Place that the event occurred. | ID | OPTIONAL.
description | Additional information describing the event. | string | OPTIONAL.
noteref | A list of note handles. | ID[] | OPTIONAL.
citationref | A list of citation handles. | ID[] | OPTIONAL.
objref | A list of media references. | MediaRef[] | OPTIONAL.
tagref | A list of tag handles. | ID[] | OPTIONAL.

A Date object can hold an exact date or a date range.

See also: [Events in Gramps](https://gramps-project.org/wiki/index.php?title=Events_in_Gramps) 

### LdsOrd

The LdsOrd object is used to record LDS ordinances. They are similar to events, but specific to the LDS church.

name  | description | data type | constraints
------|-------------|-----------|------------
priv | Privacy flag. | boolean | OPTIONAL.
type | Ordinance. | LdsOrdType | REQUIRED.
date | Date. | Date | OPTIONAL.
temple | LDS temple. | string | OPTIONAL.
place | Place. | ID | OPTIONAL.
status | Status. | string | OPTIONAL.
sealed_to | Family sealed to. | ID | OPTIONAL.
noteref | A list of note handles. | ID[] | OPTIONAL.
citationref | A list of citation handles. | ID[] | OPTIONAL.

### Attribute

Attribute objects are used to record facts or permanent characteristics.

name  | description | data type | constraints
------|-------------|-----------|------------
priv | Privacy flag. | boolean | OPTIONAL.
type | Type. | AttributeType | REQUIRED.
value| Value. | string | REQUIRED.
citationref | A list of citation handles. | ID[] | OPTIONAL.
noteref | A list of note handles. | ID[] | OPTIONAL.

See also: [Attributes in Gramps](https://gramps-project.org/wiki/index.php?title=Attributes_in_Gramps)

### EventRef

The EventRef object is used to store information about how a person participates in the referenced event.

name  | description | data type | constraints
------|-------------|-----------|------------
hlink | Link to an event. | ID | REQUIRED.
priv | Privacy flag. | boolean | OPTIONAL.
role | Role in the event. | EventRoleType | OPTIONAL.
attribute | A list of attributes. | Attribute[] | OPTIONAL.
noteref | A list of note handles. | ID[] | OPTIONAL.

### ChildRef

ChildRef objects are used to store information about the relationship between a child and their parent family.

name  | description | data type | constraints
------|-------------|-----------|------------
hlink | Link to a child. | ID | REQUIRED.
priv | Privacy flag. | boolean | OPTIONAL.
mrel | Relationship to mother. | ChildRefType | OPTIONAL.
frel | Relationship to father. | ChildRefType | OPTIONAL.
citationref | A list of citation handles. | ID[] | OPTIONAL.
noteref | A list of note handles. | ID[] | OPTIONAL.

The relationship to the mother and father are stored separately.

### PersonRef

PersonRef objects are used to define an association between two people.

name  | description | data type | constraints
------|-------------|-----------|------------
hlink | Link to a person. | ID | REQUIRED.
priv | Privacy flag. | boolean | OPTIONAL.
rel | Relationship. | string | REQUIRED.
citationref | A list of citation handles. | ID[] | OPTIONAL.
noteref | A list of note handles. | ID[] | OPTIONAL.

Associations are directional.

Used for relationships such as godparent or friend.

## Use Cases

A Gramps XML version of the [Use Cases](Use_Cases.gramps) has been created to illustrate the Gramps data model.

### Single Person

Henry VIII is represented as follows:

```
    <person handle="_ce381362115ba4cd7dc2d22d6f" change="1417130770" id="I0000">
      <gender>M</gender>
      <name type="Birth Name">
        <first>Henry</first>
        <surname></surname>
        <suffix>VIII</suffix>
      </name>
      <eventref hlink="_ce38165640876127041967c66fa" role="Primary"/>
      <eventref hlink="_ce38174668148a43c7652db17d1" role="Primary"/>
      <childof hlink="_ce38186327c42337a3fa247869b"/>
      <parentin hlink="_ce381e4301328c459673aad75ab"/>
      <parentin hlink="_ce3829283e77b3ba0a6887b9bde"/>
      <parentin hlink="_ce382da3cf044ff834233b551e3"/>
      <parentin hlink="_ce3831cd3fd6dd11faacf8452c6"/>
      <parentin hlink="_ce383596cbf3d0f13bea341c37c"/>
      <parentin hlink="_ce38375826b51c1646d2571ed70"/>
      <parentin hlink="_ce383a1cf5368e13af7d5c454e"/>
    </person>
```

Gender can be either M=Male, F=Female or U=Unknown. There is a [feature request](https://gramps-project.org/bugs/view.php?id=5730) and [enhancement proposal](https://gramps-project.org/wiki/index.php?title=GEPS_027:_Gender_as_an_Entry_Field) relating to better handling of LGBT data.

If facts are time-dependent, they are modelled as events, otherwise they are modelled as attributes.
The eventref objects contain links to top-level events.

Relationships are modelled by links to family objects.  The childof elements link the person to families in which they are a child. The parentin elements link the person to families in which they are a parent.

### Simple Family

The relationship between Henry VIII and Catherine of Aragon is represented as follows:

```
    <family handle="_ce381e4301328c459673aad75ab" change="1417128523" id="F0001">
      <rel type="Married"/>
      <father hlink="_ce381362115ba4cd7dc2d22d6f"/>
      <mother hlink="_ce381b3bc8015c6cea433ecb1dd"/>
      <eventref hlink="_ce381ec286ee802889fe2de4d" role="Family"/>
      <eventref hlink="_ce381f4fdf874fc507cd68a8918" role="Family"/>
      <childref hlink="_ce38228582d6feb9a0d8fdc10c"/>
      <childref hlink="_ce38232f50862dacb9cc7d8e2cd"/>
      <childref hlink="_ce3823bc1d447910bf1e2070043"/>
      <childref hlink="_ce3824204a1686fa9a8f464c85b"/>
      <childref hlink="_ce3825591e83e2f56213ae3c79b"/>
      <childref hlink="_ce3826111542ef68cf26e35eac8"/>
    </family>
```

Common relationship types are:  *Married*, *Unmarried* and *Civil Union*.

The father and mother elements link to the two people in the relationship.  These people can be both the same gender.

The eventref objects contain links to top-level family events such as marriage, divorce and annulment.

The childref objects can contain the relationship to the mother and father separately.  The pre-defined types are:  *None*, *Birth*, *Adopted*, *Stepchild*, *Sponsored*, *Foster* and *Unknown*, but users are allowed to define custom types.  The default is *Birth*, so it is not shown in this example.

### Multiple Marriages

Each marriage of Henry VIII is reresented by a separate family object:

```
    <family handle="_ce3829283e77b3ba0a6887b9bde" change="1417129216" id="F0002">
      <rel type="Married"/>
      <father hlink="_ce381362115ba4cd7dc2d22d6f"/>
      <mother hlink="_ce3828043d52217a6b9797e069"/>
      <eventref hlink="_ce382a227ab5e6f0fdfea90ea6a" role="Family"/>
      <eventref hlink="_ce382a4bf6b6b6d304d9bed2bc8" role="Family"/>
      <childref hlink="_ce382bbcfcc2369895f80775870"/>
      <childref hlink="_ce382cb8e6420fbe214c1ef32"/>
      <childref hlink="_ce382d4117054205c4b59b6780f"/>
    </family>
    <family handle="_ce382da3cf044ff834233b551e3" change="1417129587" id="F0003">
      <rel type="Married"/>
      <father hlink="_ce381362115ba4cd7dc2d22d6f"/>
      <mother hlink="_ce382e109ba4ed0a92d0a2c5271"/>
      <eventref hlink="_ce382f8a1a51b816ea3a3ce647" role="Family"/>
      <childref hlink="_ce38302e7ac2873f00308368890"/>
    </family>
    <family handle="_ce3831cd3fd6dd11faacf8452c6" change="1417133807" id="F0004">
      <rel type="Married"/>
      <father hlink="_ce381362115ba4cd7dc2d22d6f"/>
      <mother hlink="_ce3832889af5613432fb5fa3154"/>
      <eventref hlink="_ce38335625a2bdd6c0426055ef" role="Family"/>
      <eventref hlink="_ce383388a795d5a3b8ce29ec099" role="Family"/>
      <attribute type="No Children" value=""/>
    </family>
    <family handle="_ce383596cbf3d0f13bea341c37c" change="1417133825" id="F0005">
      <rel type="Married"/>
      <father hlink="_ce381362115ba4cd7dc2d22d6f"/>
      <mother hlink="_ce383642951a5775e35ed9c84f"/>
      <eventref hlink="_ce3837257e0537d8c925c253038" role="Family"/>
      <attribute type="No Children" value=""/>
    </family>
    <family handle="_ce38375826b51c1646d2571ed70" change="1417133836" id="F0006">
      <rel type="Married"/>
      <father hlink="_ce381362115ba4cd7dc2d22d6f"/>
      <mother hlink="_ce3838585e32cb0983f15af4ae5"/>
      <eventref hlink="_ce383917d92395ee008becccd22" role="Family"/>
      <attribute type="No Children" value=""/>
    </family>
```

### Never Married

Elizabeth I is represented as follows:

```
    <person handle="_ce382bbcfcc2369895f80775870" change="1417133738" id="I0011">
      <gender>F</gender>
      <name type="Birth Name">
        <first>Elizabeth</first>
        <surname></surname>
        <suffix>I</suffix>
      </name>
      <eventref hlink="_ce382b7e4a21f3ab39439176363" role="Primary"/>
      <eventref hlink="_ce382bb968e372830b28ddfd2fc" role="Primary"/>
      <attribute type="Never Married" value=""/>
      <childof hlink="_ce3829283e77b3ba0a6887b9bde"/>
    </person>
```

Here an attribute is used to explicitly state that Elizabeth I was never married.


### Child out of Wedlock

The relationship between Henry VIII and Elizabeth Blount is represented as follows:

```
    <family handle="_ce383a1cf5368e13af7d5c454e" change="1417130770" id="F0007">
      <rel type="Unmarried"/>
      <father hlink="_ce381362115ba4cd7dc2d22d6f"/>
      <mother hlink="_ce383b2541e7b4ee6965321bbb"/>
      <childref hlink="_ce383c22ca6533a4487a5024d35"/>
    </family>
```

In this example, the child is clearly illegitimate because the relationship type is set to unmarried and there is no link to a marriage event.

## Analysis

