Download Link: https://assignmentchef.com/product/solved-cs561-assignment2-evaluating-simple-report-queries-and-produce-the-output
<br>
<strong><em>Objectives</em></strong>: • You will continue with evaluating simple report queries and produce the output. As with

the assignment #1, you will also express the queries in SQL. The reports below are

similar in nature with the reports from the assignment #1; however, there are <u>two main</u>

<u>differences</u> between the two: (1) the new reports will require <u>aggregation “outside” the</u>

<u>groups</u> (in assignment #1, all of the aggregates were computed for the rows within the

groups); (2) some of the aggregates in the new reports will be computed based on other

aggregates of the same reports – they are known as “<u>dependent aggregates</u>”.

<strong><em>Description</em></strong>: • Generate reports based on the following queries:
<ol>
 	<li>For each <em>product</em> and <em>month,</em> <em>count</em> the number of sales transactions that were</li>
</ol>
between the <em>previous</em> and the <em>following</em> month’s average sales quantities. For

January and December, display &lt;NULL&gt; or 0.
<ol start="2">
 	<li>For <em>customer</em> and <em>product</em>, show the average sales <em>before, during </em>and <em>after</em> each</li>
</ol>
month (e.g., for February, show average sales of January and March. For “before”

January and “after” December, display &lt;NULL&gt;. The “YEAR” attribute is not

considered for this query – for example, both January of 2007 and January of 2008

are considered January regardless of the year.
<ol start="3">
 	<li>For each <em>customer</em>, <em>product</em> and <em>state</em> combination, compute (1) the product’s average</li>
</ol>
sale of this customer for the state (i.e., the simple AVG for the group-by attributes –

this is the easy part), (2) the average sale of the product and the state but for <em>all of the </em>

<em>other customers</em> and (3) the customer’s average sale for the given state, but for <em>all of </em>

<em>the other products</em>.
<ol start="4">
 	<li>For <em>customer</em> and <em>product</em>, find the <em>month</em> by which time, 1/3 of the sales quantities</li>
</ol>
have been purchased. Again, for this query, the “YEAR” attribute is not considered.

Another way to view this problem (as in problem #2 above) is to pretend all 500 rows

of sales data are from the same year.

The following are sample report output (NOTE: the numbers shown below are <u>not</u> the actual

aggregate values. You can write simple SQL queries to find the actual aggregate values).

Yfuonctions other thanu are only allowed to the 5 aggregate functions (sum, count, avg, max &amp; min); <u>standard SQL syntax covered in class</u> – do not use any other and use only

simple syntax of ‘agg(x)’ – i.e., do not use features such as CASE statement inside (such

features hide implicit JOINs).

<u>Report #1:</u>

PRODUCT MONTH SALES_COUNT_BETWEEN_AVGS

======= ===== ========================

Cookies 1 &lt;NULL&gt;

Yogurt 3 19

. . . .

CS 561 Page 1 of 2

Database Management Systems I

Spring 2020

<u>Report #2:</u>

CUSTOMER PRODUCT MONTH BEFORE_AVG DURING_AVG AFTER_AVG

======== ======= ===== ========== ========== =========

Bloom Coke 1 &lt;NULL&gt; 1539 2434 Sam Eggs 3 254 539 325 . . . .

<u>Report #3:</u>

CUSTOMER PRODUCT STATE PROD_AVG OTHER_CUST_AVG OTHER_PROD_AVG

======== ======= ===== ======== ============== ==============

Helen Bread NY 243 268 1493 Emily Milk NJ 1426 478 926

. . . .

<u>Report #4:</u>

CUSTOMER PRODUCT 1/3 PURCHASED BY MONTH

======== ======= ======================

Emily Butter 2

Bloom Soap 3

. . . .