Download Link: https://assignmentchef.com/product/solved-cis336-lab-1-normal-forms-and-entity-relationship-diagrams-solution
<br>
<header class="entry-header">

 <p class="entry-title">In this exercise, you will analyze a de-normalized data set presented in the form of a spreadsheet. You will next construct a series of dependency diagrams, transforming the evolving data model from First Normal Form (1NF), to Second Normal Form (2NF), and finally to Third Normal Form (3NF). When the model has reached 3NF, you will construct the Entity Relationship Diagram (ERD) depicting the logical design of the database. Your ERD will use Crow’s Foot notation to denote the relationships between tables.

</header>

5/5 - (7 votes)

Sample Exercise, With Solution.

Before completing your lab, please review this example problem. The diagram below is a partial depiction of a business spreadsheet for a retail store operation. The store sells books. Books have a 13-digit International Standard Book Number (ISBN), a title, a publisher, and a unit price. Invoices track sales of books. An Invoice contains one or many line items, with each line item reflecting the sale of one or more copies of a specific book. Every publisher has a company name, and a publisher code.

BookSales

<ol type="1">

 <li style="list-style-type: none">

  <ol type="1">

   <li>Using the BookSales table structure shown above, draw the dependency diagram, and show all dependencies, full, partial, and transitive.Discussion: A composite primary key consisting of InvNum + ISBN13 can be constructed, ensuring that all rows are unique. All remaining attributes are shown to be dependent (at least partially) on this composite key, so the table is 1NF. Further analysis shows that InvDate is dependent on only part of the key (InvNum), and that unitPrice, PubCode, and BookTitle also depend on part of the key (ISBN13). A transitive relationship is also revealed: PubName truly depends on PubCode, which in turn depends on ISBN13.</li>

   <li>Using the answer to exercise 1, remove all partial dependencies and draw the new dependency diagrams. For each new table created, specify its normal form (1NF, 2NF, 3NF).Discussion: To achieve 2NF, we must remove partial dependencies. This is done by decomposing into three tables, and three dependency diagrams at this stage. Notice that the Transitive relationship has not yet been addressed.</li>

  </ol></li>

</ol>




<ol type="1">

 <li>Using the answer to exercise 3, remove all transitive dependencies, and draw the new dependency diagrams. For each new or revised table, specify its normal form.Discussion: The transitive relationship has been removed by creating the Publishers table, in which PubName is fully dependent upon PubCode. Pubcode also persists as a dependent attribute and Foreign Key in Books. All tables are now in 3NF, and have been given meaningful names reflecting the entities they represent. LINEITEMS represents the collection of line items for all invoices. Invoices represents the collection of Invoices for all customer orders. Books makes up the list of all books available for sale (whether they have ever been ordered or not). Each book has a publisher, and the publisher code and Name reside in the Publishers table.</li>

 <li>Draw the ERD for exercise 3, using Crow’s Foot notation.</li>

</ol>

Student ExerciseThe student exercise for this lab is similar to the sample exercise presented above.Consider the following spreadsheet containing information about customers, their shipping and billing addresses, and the countries corresponding to each of those addresses. A customer may be associated with zero to many addresses. A customer may have 0 or 1 default billing address. A customer may have 0 or 1 default shipping address. Each address may be associated with 0 or 1 countries, while each country may be associated with 0 to many addresses.

Using the example solution as a guide, perform the following steps:

<ul type="1">

 <li>Using the CustomerAddressCountry spreadsheet show above, draw the dependency diagram, and show all dependencies, full, partial, and transitive. Paste your solution into the answer sheet, and label it, Answer #1.</li>

 <li>Using the answer to exercise 1, remove all partial dependencies and draw the new dependency diagrams. For each new table created, specify its normal form (1NF, 2NF, 3NF). Paste your solution into the answer sheet, and label it, Answer #2.</li>

 <li>Using the answer to exercise 3, remove all transitive dependencies, and draw the new dependency diagrams. For each new or revised table, specify its normal form. Paste your solution into the answer sheet, and label it, Answer #3.</li>

 <li>Draw the ERD for exercise 3, using Crow’s Foot notation. Paste your solution into the answer sheet, and label it, Answer #4.</li>

</ul>

<table class="easy-table easy-table-default " border="0">

 <thead>

  <tr>

   <th>InvNum</th>

   <th>ISBN13</th>

   <th>InvDate</th>

   <th>BookTitle</th>

   <th>PubCode</th>

   <th>PubName</th>

   <th>Qty</th>

   <th>unitPrice</th>

  </tr>

 </thead>

 <tbody>

  <tr>

   <td>1022</td>

   <td>9781291940336</td>

   <td>2015-03-09</td>

   <td>MYSQL Functions</td>

   <td>1001</td>

   <td>Lulu.com</td>

   <td>3</td>

   <td>4.99</td>

  </tr>

  <tr>

   <td>1022</td>

   <td>9780321833877</td>

   <td>2015-03-09</td>

   <td>MySQL Fifth Edition</td>

   <td>1029</td>

   <td>Addison-Wesley</td>

   <td>5</td>

   <td>33.95</td>

  </tr>

  <tr>

   <td>1022</td>

   <td>9781890774820</td>

   <td>2015-03-09</td>

   <td>Murach’s MySQL 2nd Edition</td>

   <td>1032</td>

   <td>Murach, Mike &amp; Associates Inc</td>

   <td>2</td>

   <td>48.95</td>

  </tr>

  <tr>

   <td>1249</td>

   <td>9781449374020</td>

   <td>2015-02-22</td>

   <td>MySQL Cookbook: Solutions for Database Developers and Administrators</td>

   <td>1118</td>

   <td>O’Reilly Media Incorporated</td>

   <td>9</td>

   <td>50.59</td>

  </tr>

  <tr>

   <td>1249</td>

   <td>9781449325572</td>

   <td>2015-02-22</td>

   <td>PHP &amp; MySQL: The Missing Manual</td>

   <td>1118</td>

   <td>O’Reilly Media, Incorporated</td>

   <td>6</td>

   <td>29.95</td>

  </tr>

  <tr>

   <td>1249</td>

   <td>9781890774790</td>

   <td>2015-02-22</td>

   <td>Murach’s PHP and MySQL 2nd Edition</td>

   <td>1032</td>

   <td>Murach, Mike &amp; Associates Inc</td>

   <td>1</td>

   <td>48.95</td>

  </tr>

 </tbody>

</table>

<table class="easy-table easy-table-default " border="0">

 <thead>

  <tr>

   <th>cust_id</th>

   <th>fname</th>

   <th>lname</th>

   <th>def_bill_addr_id</th>

   <th>def_ship_addr_id</th>

   <th>addr_id</th>

   <th>street_addr</th>

   <th>city</th>

   <th>state</th>

   <th>zip</th>

   <th>country_code</th>

   <th>country_name</th>

  </tr>

 </thead>

 <tbody>

  <tr>

   <td>202</td>

   <td>John</td>

   <td>Smith</td>

   <td>1096</td>

   <td>2039</td>

   <td>1096</td>

   <td>123 Happy Ave.</td>

   <td>Orlando</td>

   <td>FL</td>

   <td>32801</td>

   <td>76</td>

   <td>United States</td>

  </tr>

  <tr>

   <td>202</td>

   <td>John</td>

   <td>Smith</td>

   <td>1096</td>

   <td>2039</td>

   <td>2039</td>

   <td>2024 Shorline Dr.</td>

   <td>Seattle</td>

   <td>WA</td>

   <td>98101</td>

   <td>76</td>

   <td>United States</td>

  </tr>

  <tr>

   <td>202</td>

   <td>John</td>

   <td>Smith</td>

   <td>1096</td>

   <td>2039</td>

   <td>8053</td>

   <td>100 N. Kent Ave. St.</td>

   <td>James</td>

   <td>WA</td>

   <td>54364</td>

   <td>34</td>

   <td>Jamaica</td>

  </tr>

  <tr>

   <td>175</td>

   <td>Hilda</td>

   <td>Yeager</td>

   <td>2172</td>

   <td>2172</td>

   <td>3879</td>

   <td>48 Spatzel Ct.</td>

   <td>Dusseldorf</td>

   <td>DD</td>

   <td>5111</td>

   <td>29</td>

   <td>Germany</td>

  </tr>

  <tr>

   <td>175</td>

   <td>Hilda</td>

   <td>Yeager</td>

   <td>2172</td>

   <td>2172</td>

   <td>3921</td>

   <td>162 Rue Moritz</td>

   <td>Paris</td>

   <td>PR</td>

   <td>75001</td>

   <td>28</td>

   <td>France</td>

  </tr>

  <tr>

   <td>321</td>

   <td>Siri</td>

   <td>Apple</td>

   <td>1881</td>

   <td>1881</td>

   <td>1881</td>

   <td>1 Infinite Loop</td>

   <td>Cupertino</td>

   <td>CA</td>

   <td>95014</td>

   <td>76</td>

   <td>United States</td>

  </tr>

 </tbody>