# Use Cases

This is a list of use cases which will be used to help analyze how well each model
handles different scenarios and data which the CCEG has deemed worthy of consideration.
The list is not meant to be complete in terms of all possibilities but is intended
to be complete in its exercise of the data model's abilities to handle persons, events,
and relationships.

Names, dates, and places are included for the sake of completeness and to see where they are stored in the models. However, the CCEG is not concerned with their formatting. In other words, we care about whether a person's birth facts are stored as an attribute of the person or as an attribute of a birth event that is connected to the person but we are not concerned with whether dates are formatted according to [ISO 8601](http://en.wikipedia.org/wiki/ISO_8601).

## A Single Person

__Description:__ Model Henry VIII, including his name, sex, vital events, and other personal data.

__Purpose:__ Show how a single person is modeled, especially their vital events and personal data. Are vital events attached directly to the person as properties or indirectly via events? Are events treated differently than facts? How is the gender represented?

## A Simple Family

__Description:__ Model the relationship between Henry VIII, his first wife Catherine of Aragon, and their children.

__Purpose:__ Show how simple family relationships are modeled. How are spouses relationship modeled? Where are the marriage dates and places stored? Do children have separate relationships with each parent? Where are `biological` and `adopted` facts stored?

## Data

The data for the use cases is of [Henry VIII](http://en.wikipedia.org/wiki/Henry_VIII_of_England#Marriages_and_issue) and his family.

<table>
  <tr>
    <th>Person</th>
    <th>Relationships</th>
  </tr>
  <tr>
    <td valign="top">
      <a name="henry-viii"></a>
      <p><strong>Henry VIII</strong></p>
      <em>Sex</em>: Male<br>
      <em>Born</em>: 28 June 1491 in Greenwich Palace, Greenwich, London, England<br>
      <em>Died</em>: 28 January 1547 in Palace of Whitehall, London, England
    </td>
    <td>
      <p><strong>Parents</strong></p>
      <ul>
        <li>Henry VII of England</li>
        <li>Elizabeth of York</li>
      </ul>
      <p><strong>Spouses and Children</strong></p>
      <ul>
        <li>
          <a href="#catherine-of-aragon">Catherine of Aragon</a><br>
          <em>Married</em>: 11 June 1509 in Greenwich Palace, London, England<br>
          <em>Annulled</em>: 23 May 1533
          <ul>
            <li><a href="#daughter-1">[Unnamed Daughter]</a></li>
            <li><a href="#henry-duke-of-cornwall-1">Henry, Duke of Cornwall</a></li>
            <li><a href="#son-1">[Unnamed Son]</a></li>
            <li><a href="#henry-duke-of-cornwall-2">Henry, Duke of Cornwall</a></li>
            <li><a href="#queen-mary-i">Queen Mary I</a></li>
            <li><a href="#daughter-2">[Unnamed Daughter]</a></li>
          <ul>
        </li>
      </ul>
    </td>
  </tr>
  <tr>
    <td valign="top">
      <a name="catherine-of-aragon"></a>
      <p><strong>Catherine of Aragon</strong></p>
      <em>Sex</em>: Female<br>
      <em>Born</em>: 16 December 1485 in Archbishop's Palace, Alcalá de Henares, Spain<br>
      <em>Died</em>: 7 January 1536 in Kimbolton Castle, Cambridgeshire, England
    </td>
    <td>
      <p><strong>Spouses and Children</strong></p>
      <ul>
        <li>
          <a href="#henry-viii">Henry VIII</a><br>
          <em>Married</em>: 11 June 1509 in Greenwich Palace, London, England<br>
          <em>Annulled</em>: 23 May 1533
          <ul>
            <li><a href="#daughter-1">[Unnamed Daughter]</a></li>
            <li><a href="#henry-duke-of-cornwall-1">Henry, Duke of Cornwall</a></li>
            <li><a href="#son-1">[Unnamed Son]</a></li>
            <li><a href="#henry-duke-of-cornwall-2">Henry, Duke of Cornwall</a></li>
            <li><a href="#queen-mary-i">Queen Mary I</a></li>
            <li><a href="#daughter-2">[Unnamed Daughter]</a></li>
          <ul>
        </li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>
      <a name="daughter-1"></a>
      <p><strong>[Unnamed daughter]</strong></p>
      <em>Sex</em>: Female<br>
      <em>Born</em>: 31 January 1510<br>
      <em>Died</em>: 31 January 1510<br>
      <em>Misscarried</em>
    </td>
    <td>
      <p><strong>Parents</strong></p>
      <ul>
        <li><a href="#henry-viii">Henry VIII</a></li>
        <li><a href="#catherine-of-aragon">Catherine of Aragon</a></li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>
      <a name="henry-duke-of-cornwall-1"></a>
      <p><strong>Henry, Duke of Cornwall</strong></p>
      <em>Sex</em>: Male<br>
      <em>Born</em>: 1 January 1511<br>
      <em>Died</em>: 22 February 1511
    </td>
    <td>
      <p><strong>Parents</strong></p>
      <ul>
        <li><a href="#henry-viii">Henry VIII</a></li>
        <li><a href="#catherine-of-aragon">Catherine of Aragon</a></li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>
      <a name="son-1"></a>
      <p><strong>[Unnamed Son]</strong></p>
      <em>Sex</em>: Male<br>
      <em>Born</em>: November 1513<br>
      <em>Died</em>: November 1513
    </td>
    <td>
      <p><strong>Parents</strong></p>
      <ul>
        <li><a href="#henry-viii">Henry VIII</a></li>
        <li><a href="#catherine-of-aragon">Catherine of Aragon</a></li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>
      <a name="henry-duke-of-cornwall-2"></a>
      <p><strong>Henry, Duke of Cornwall</strong></p>
      <em>Sex</em>: Male<br>
      <em>Born</em>: December 1514<br>
      <em>Died</em>: December 1514
    </td>
    <td>
      <p><strong>Parents</strong></p>
      <ul>
        <li><a href="#henry-viii">Henry VIII</a></li>
        <li><a href="#catherine-of-aragon">Catherine of Aragon</a></li>
      </ul>
    </td>
  </tr>
  <tr>
    <td valign="top">
      <a name="queen-mary-i"></a>
      <p><strong>Queen Mary I</strong></p>
      <em>Sex</em>: Female<br>
      <em>Born</em>: 18 February 1516<br>
      <em>Died</em>: 17 November 1558
    </td>
    <td>
      <p><strong>Parents</strong></p>
      <ul>
        <li><a href="#henry-viii">Henry VIII</a></li>
        <li><a href="#catherine-of-aragon">Catherine of Aragon</a></li>
      </ul>
      <p><strong>Spouses and Children</strong></p>
      <ul>
        <li>
          Phillip II of Spain
          <em>Married</em>: 1554
          <em>No Children</em>
        </li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>
      <a name="daughter-2"></a>
      <p><strong>[Unnamed daughter]</strong></p>
      <em>Sex</em>: Female<br>
      <em>Born</em>: November 1518<br>
      <em>Died</em>: November 1518<br>
      <em>Stillborn</em>
    </td>
    <td>
      <p><strong>Parents</strong></p>
      <ul>
        <li><a href="#henry-viii">Henry VIII</a></li>
        <li><a href="#catherine-of-aragon">Catherine of Aragon</a></li>
      </ul>
    </td>
  </tr>
</table>
