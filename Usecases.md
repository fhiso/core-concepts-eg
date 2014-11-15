# Use cases

This is a list of use cases which will be used to help analyze how well each model
handles different scenarios and data which the CCEG has deemed worthy of consideration.
The list is not meant to be complete in terms of all possibilities but is intended
to be complete in its exercise of the data model's abilities to handle persons, events,
and relationships.

### [Henry VIII](http://en.wikipedia.org/wiki/Henry_VIII_of_England#Marriages_and_issue)

    {
      "persons": [
        {
          "id": 1,
          "name": "Henry VIII of England",
          "sex": "Male",
          "birth": {
            "date": "28 June 1491",
            "place": "Greenwich Palace, Greenwich, London, England"
          },
          "death": {
            "date": "28 January 1547",
            "place": "Palace of Whitehall, London, England"
          }
        },
        {
          "id": 2,
          "name": "Catherine of Aragon",
          "sex": "Female",
          "birth": {
            "date": "16 December 1485",
            "place": "Archbishop's Palace, Alcalá de Henares, Spain"
          },
          "death": {
            "date": "7 January 1536",
            "place": "Kimbolton Castle, Cambridgeshire, England"
          }
        },
        {
          "id": 3,
          "sex": "Female",
          "birth": {
            "date": "31 January 1510"
          },
          "death": {
            "date": "31 January 1510"
          }
        },
        {
          "id": 4,
          "name": "Henry, Duke of Cornwall",
          "sex": "Male",
          "birth": {
            "date": "1 January 1511"
          },
          "death": {
            "date": "22 February 1511"
          }
        },
        {
          "id": 5,
          "sex": "Male",
          "birth": {
            "date": "November 1513"
          },
          "death": {
            "date": "November 1513"
          }
        },
        {
          "id": 6,
          "sex": "Male",
          "birth": {
            "date": "December 1514"
          },
          "death": {
            "date": "December 1514"
          }
        },
        {
          "id": 7,
          "name": "Queen Mary I",
          "sex": "Female",
          "birth": {
            "date": "18 February 1516"
          },
          "death": {
            "date": "17 November 1558"
          }
        },
        {
          "id": 8,
          "name": "Queen Mary I",
          "sex": "Female",
          "birth": {
            "date": "November 1518"
          },
          "death": {
            "date": "November 1518"
          }
        }
      ],
      "relationships": [
        {
          "type": "Couple",
          "spouse1": 1,
          "spouse2": 2,
          "marriage": {
            "date": "11 June 1509",
            "place": "Greenwich Palace, Greenwich, London, England"
          },
          "annullment": {
            "date": "23 May 1533"
          }
        },
        {
          "type": "Child",
          "father": 1,
          "mother": 2,
          "child": 3
        },
        {
          "type": "Child",
          "father": 1,
          "mother": 2,
          "child": 4
        },
        {
          "type": "Child",
          "father": 1,
          "mother": 2,
          "child": 5
        },
        {
          "type": "Child",
          "father": 1,
          "mother": 2,
          "child": 6
        },
        {
          "type": "Child",
          "father": 1,
          "mother": 2,
          "child": 7
        },
        {
          "type": "Child",
          "father": 1,
          "mother": 2,
          "child": 8
        }
      ]
    }
