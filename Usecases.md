# Use Cases

This is a list of use cases which will be used to help analyze how well each model
handles different scenarios and data which the CCEG has deemed worthy of consideration.
The list is not meant to be complete in terms of all possibilities but is intended
to be complete in its exercise of the data model's abilities to handle persons, events,
and relationships.

Names, dates, and places are included for the sake of completeness and to see where they are stored in the models. However, the CCEG is not concerned with their formatting. In other words, we care about whether a person's birth facts are stored as an attribute of the person or as an attribute of a birth event that is connected to the person but we are not concerned with whether dates are formatted according to [ISO 8601](http://en.wikipedia.org/wiki/ISO_8601).

### A Single Person

__Description:__ Model <a href="#henry-viii">Henry VIII</a>, including his name, sex, vital events, and other personal data.

__Purpose:__ Show how a single person is modeled, especially their vital events and personal data. Are vital events attached directly to the person as properties or indirectly via events? Are events treated differently than facts? How is the gender represented?

### A Simple Family

__Description:__ Model the relationship between <a href="#henry-viii">Henry VIII</a>, his first wife <a href="#catherine-of-aragon">Catherine of Aragon</a>, and their children.

__Purpose:__ Show how simple family relationships are modeled. How are spouses relationship modeled? Where are the marriage dates and places stored? Do children have separate relationships with each parent? Where are `biological` and `adopted` facts stored?

### Multiple Marriages

__Description:__ Model the relationships between <a href="#henry-viii">Henry VIII</a> and all of his wives.

__Purpose:__ Demonstrate how multiple marriage relationships are handled.

### Never Married

__Description:__ Model the fact that <a href="#queen-elizabeth-1">Queen Elizabeth I</a> never married.

__Purpose:__ To show if and how the models handle explicitly stating that a person never married despite reaching the appropriate age.

### Child out of Wedlock

__Description:__ Model the relationship between <a href="#henry-fitzroy">Henry FitzRoy</a> and his parents <a href="#henry-viii">Henry VIII</a> and <a href="#elizabeth-blount">Elizabeth Blount</a>.

__Purpose:__ Demonstrate how child relationships are modeled when the parents are not married. Does the model imply that parents are married? Do the couples have a separate relationship? Does the absence of a relationship between the parents imply the child was born out of wedlock?

## Data

Data for the use cases was extracted from the Wikipedia articles on [Henry VIII](http://en.wikipedia.org/wiki/Henry_VIII_of_England#Marriages_and_issue) and his family.

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
        <li>
          <a href="#anne-boleyn">Anne Boleyn</a><br>
          <em>Married</em>: 25 January 1533 in Westminster Abbey, Westminster, London, England<br>
          <em>Annulled</em>: 17 May 1536
          <ul>
            <li><a href="#queen-elizabeth-1">Queen Elizabeth</a></li>
            <li><a href="#henry-duke-of-cornwall-3">Henry, Duke of Cornwall</a></li>
            <li><a href="#son-2">[Unnamed Son]</a></li>
          <ul>
        </li>
        <li>
          <a href="#jane-seymour">Jane Seymour</a><br>
          <em>Married</em>: 30 May 1536 in York Place, London, England
          <ul>
            <li><a href="#king-edward-vi">King Edward VI</a></li>
          <ul>
        </li>
        <li>
          <a href="#anne-of-cleves">Anne of Cleves</a><br>
          <em>Married</em>: 6 January 1540<br>
          <em>Annulled</em>: 9 July 1540<br>
          <em>No Children</em>
        </li>
        <li>
          <a href="#catherine-howard">Catherine Howard</a><br>
          <em>Married</em>: 28 July 1540 in Oatlands Palace, Surrey, England<br>
          <em>Annulled</em>: 23 November 1541<br>
          <em>No Children</em>
        </li>
        <li>
          <a href="#catherine-parr">Catherine Parr</a><br>
          <em>Married</em>: 12 July 1543 in Hampton Court Palace, Surrey, England<br>
          <em>No Children</em>
        </li>
      </ul>
      <p><strong>Illigitimate Children</strong></p>
      <ul>
        <li><a href="#henry-fitzroy">Henry FitzRoy</a></li>
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
  <tr>
    <td valign="top">
      <a name="anne-boleyn"></a>
      <p><strong>Anne Boleyn</strong></p>
      <em>Sex</em>: Female<br>
      <em>Born</em>: 1501/1507<br>
      <em>Died</em>: 19 May 1536<br>
      <em>Beheaded</em>
    </td>
    <td>
      <p><strong>Spouses and Children</strong></p>
      <ul>
        <li>
          <a href="#henry-viii">Henry VIII</a><br>
          <em>Married</em>: 25 January 1533 in Westminster Abbey, Westminster, London, England<br>
          <em>Annulled</em>: 17 May 1536
          <ul>
            <li><a href="#queen-elizabeth-1">Queen Elizabeth</a></li>
            <li><a href="#henry-duke-of-cornwall-3">Henry, Duke of Cornwall</a></li>
            <li><a href="#son-2">[Unnamed Son]</a></li>
          <ul>
        </li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>
      <a name="queen-elizabeth-1"></a>
      <p><strong>Queen Elizabeth I</strong></p>
      <em>Sex</em>: Female<br>
      <em>Born</em>: 7 September 1533<br>
      <em>Died</em>: 24 March 1603
    </td>
    <td>
      <p><strong>Parents</strong></p>
      <ul>
        <li><a href="#henry-viii">Henry VIII</a></li>
        <li><a href="#anne-boleyn">Anne Boleyn</a></li>
      </ul>
      <p><strong>Spouses</strong></p>
      <em>Never Married</em>
    </td>
  </tr>
  <tr>
    <td>
      <a name="henry-duke-of-cornwall-3"></a>
      <p><strong>Henry, Duke of Cornwall</strong></p>
      <em>Sex</em>: Male<br>
      <em>Born</em>: August/September 1534<br>
      <em>Died</em>: August/September 1534
    </td>
    <td>
      <p><strong>Parents</strong></p>
      <ul>
        <li><a href="#henry-viii">Henry VIII</a></li>
        <li><a href="#anne-boleyn">Anne Boleyn</a></li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>
      <a name="son-2"></a>
      <p><strong>[Unnamed Son]</strong></p>
      <em>Sex</em>: Male<br>
      <em>Born</em>: 29 January 1536<br>
      <em>Died</em>: 29 January 1536
    </td>
    <td>
      <p><strong>Parents</strong></p>
      <ul>
        <li><a href="#henry-viii">Henry VIII</a></li>
        <li><a href="#anne-boleyn">Anne Boleyn</a></li>
      </ul>
    </td>
  </tr>
  <tr>
    <td valign="top">
      <a name="jane-seymour"></a>
      <p><strong>Jane Seymour</strong></p>
      <em>Sex</em>: Female<br>
      <em>Born</em>: 1508<br>
      <em>Died</em>: 24 October 1537
    </td>
    <td>
      <p><strong>Spouses and Children</strong></p>
      <ul>
        <li>
          <a href="#henry-viii">Henry VIII</a><br>
          <em>Married</em>: 30 May 1536 in York Place, London, England
          <ul>
            <li><a href="#king-edward-vi">King Edward VI</a></li>
          <ul>
        </li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>
      <a name="king-edward-vi"></a>
      <p><strong>King Edward VI</strong></p>
      <em>Sex</em>: Male<br>
      <em>Born</em>: 12 October 1537<br>
      <em>Died</em>: 6 July 1553
    </td>
    <td>
      <p><strong>Parents</strong></p>
      <ul>
        <li><a href="#henry-viii">Henry VIII</a></li>
        <li><a href="#jane-seymour">Jane Seymour</a></li>
      </ul>
      <p><strong>Spouses</strong></p>
      <em>Never Married</em>
    </td>
  </tr>
  <tr>
    <td valign="top">
      <a name="anne-of-cleves"></a>
      <p><strong>Anne of Cleves</strong></p>
      <em>Sex</em>: Female<br>
      <em>Born</em>: 22 September 1515<br>
      <em>Died</em>: 16 July 1557
    </td>
    <td>
      <p><strong>Spouses and Children</strong></p>
      <ul>
        <li>
          <a href="#henry-viii">Henry VIII</a><br>
          <em>Married</em>: 6 January 1540<br>
          <em>Annulled</em>: 9 July 1540<br>
          <em>No Children</em>
        </li>
      </ul>
    </td>
  </tr>
  <tr>
    <td valign="top">
      <a name="catherine-howard"></a>
      <p><strong>Catherine Howard</strong></p>
      <em>Sex</em>: Female<br>
      <em>Born</em>: 1521<br>
      <em>Died</em>: 13 February 1542<br>
      <em>Beheaded</em>
    </td>
    <td>
      <p><strong>Spouses and Children</strong></p>
      <ul>
        <li>
          <a href="#henry-viii">Henry VIII</a><br>
          <em>Married</em>: 28 July 1540 in Oatlands Palace, Surrey, England<br>
          <em>Annulled</em>: 23 November 1541<br>
          <em>No Children</em>
        </li>
      </ul>
    </td>
  </tr>
  <tr>
    <td valign="top">
      <a name="catherine-parr"></a>
      <p><strong>Catherine Parr</strong></p>
      <em>Sex</em>: Female<br>
      <em>Born</em>: 1512<br>
      <em>Died</em>: 5 September 1548
    </td>
    <td>
      <p><strong>Spouses and Children</strong></p>
      <ul>
        <li>
          <a href="#henry-viii">Henry VIII</a><br>
          <em>Married</em>: 12 July 1543 in Hampton Court Palace, Surrey, England<br>
          <em>No Children</em>
        </li>
      </ul>
    </td>
  </tr>
  <tr>
    <td valign="top">
      <a name="elizabeth-blount"></a>
      <p><strong>Elizabeth Blount</strong></p>
      <em>Sex</em>: Female<br>
      <em>Born</em>: 1498/1502<br>
      <em>Died</em>: 1539/1540
    </td>
    <td>
      <p><strong>Children</strong></p>
      <ul>
        <li>
          <a href="#henry-fitzroy">Henry FitzRoy</a>, illigitimate son of Henry VIII
        </li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>
      <a name="henry-fitzroy"></a>
      <p><strong>Henry FitzRoy, 1st Duke of Richmond and Somerset</strong></p>
      <em>Sex</em>: Male<br>
      <em>Born</em>: 15 June 1519<br>
      <em>Died</em>: 23 July 1536<br>
      <em>Illegitimate; acknowledged by Henry VIII in 1525</em>
    </td>
    <td>
      <p><strong>Parents</strong></p>
      <ul>
        <li><a href="#henry-viii">Henry VIII</a></li>
        <li><a href="#elizabeth-blount">Elizabeth Blount</a></li>
      </ul>
    </td>
  </tr>
</table>
