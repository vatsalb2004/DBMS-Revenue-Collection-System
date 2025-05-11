RELATIONAL SCHEMA:


![image](https://user-images.githubusercontent.com/41203937/148672017-1bf0d3a4-8389-4cd4-b4bf-efb893fda837.png)

ER Diagram:


![image](https://user-images.githubusercontent.com/41203937/148672029-1366d0a9-dd9c-4281-95f5-546e183925f8.png)



Selecting bank name,account number by identifying the taxid.as every person in the database has his unique taxid therefore the account number and the bank name details can be obtained for a payment made by the person in the database.
(NESTED QUERY)
select account_number,bankname from taxpayment where account_number in(select account_number from holds where taxid=45781);
![image](https://user-images.githubusercontent.com/41203937/148672063-ec387998-c471-459e-9c60-09507fb5dcbe.png)


(SET QUERY)
identifying the person who has not made the tax payment,but this is done very efficiently without any long query and without creating some extra table .This is simply done by set query.select all name and remove the names who have made payment ,and we are left with people who have not made pyment.
select taxid from holds minus select taxid from holds natural join payment;

![image](https://user-images.githubusercontent.com/41203937/148672072-a16f235b-d7d2-4500-bdff-2a4a3083dbb3.png)




(GROUPBY)
In this query output we retrieve the details of payment which are received from taxid with particular type of verification document linked.
all accounts with pan linking has one particular sum received under its head.
all accounts with form 60 linking has one particular amount of sum received under its head
select sum(amount) from taxpayment, bank_account where bank_account.account_number=taxpayment.account_number group by type;


![image](https://user-images.githubusercontent.com/41203937/148672077-eaf9b48e-7d8f-4a51-bb88-6388fe2dd697.png)


 
(NATURAL JOIN)
This query can be used to retrieve user id and password on feeding input as account number USE CASE: when a person needs to update user id and password using account number.
 

![image](https://user-images.githubusercontent.com/41203937/148672085-98d7d617-5190-4e80-bada-3b832cefca12.png)


DELETE QUERY:
1
This if someone has already paid before the deadline of payment date ,on the user side the person can select/find his particular taxid by identifying his name in the database and then using taxid internally the system can delete his payment schedule.

![image](https://user-images.githubusercontent.com/41203937/148672107-7df3599c-75c1-4b66-983d-728863b863fc.png)


2
suppose some person with a history of default applies for default history removal and he gets approved by the officials,this command can be used to remove the details of the person by using taxid

![image](https://user-images.githubusercontent.com/41203937/148672117-7eee92b7-6be1-4762-ae26-e6232190b111.png)





# Database Management Systems

1.	Choose a mini world for design and implementation of it’s a database assigning an appropriate title for the database.	(2)
2.	Write down the data requirements and functional requirements for the database (in approximately 1500 words). The data requirements, apart from data to be stored in the database should also take into account the necessary integrity constraints that are reasonable for the database under consideration. The functional requirements should involve at least two different scenarios of removal of old data, at least two different scenarios for modification of existing data and four different scenarios of data retrieval.	(10)
3.	Draw an ER/EER diagram based on the data requirements. Indicate key constraints, cardinality constraints and participation constraints on the diagram.	(8)
4.	Convert the ER/EER diagram into a relational database schema diagram.	(15)
5.	Implement the relational database schema incorporating appropriate (based on data requirements) integrity constraints and enter necessary sample data into the tables.	(15)
6.	Write down the necessary SQL statements for implementation of functional requirements through SQL query, delete and update statement.	(15)
7.	Define and implement one PL/SQL function and one PL/SQL procedure appropriate for the database under consideration.	(10)
8.	Define two business rules appropriate for the database under consideration and implement the rules using trigger.
(15)
9.	Submission of the complete project document.	(10)
