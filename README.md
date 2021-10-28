# bank-app
Capital Banking Management App
Capital Banking Management App is an Updated Version of Capital Bank Version 1, Which is an Restful Web based Java Application Which allows Users to Open an account, Transfer funds to Different Accounts, Deposit Amount, Withdraw Amount and also provide facility to view previous transactions. The additioal thing I have added is Front-end Stack instead of plain console.

Request and Response Work Flow
Sending a Request
For sending the request from Frontend to Backend, I have used JSON where I have converted my request into a JSON object and pass it on to the backend, As Java Servlet can't able read JSON data for proper communication between the Front-end and Back-end additionally I have used Jackson API, What it basically does is, it takes the JSON format data and convert a JSON string to an equivalent Java object.

Sending a Response
For sending the response from Backend to Frontend, I have bind my java object into a Jackson library object and converted the java object into an equivalent JSON object. From the Front End side, I have used Fetch API to fetch the details and then rendered it onto my View(HMTL page).

Front-End Tech Stack & Tools
1. HTML5

2. CSS3

3. Bootstrap

4. JavaScript ES6

5. JSON for Parsing
Backend-End Tech Stack & Tools
1. Java8

2. Servlet

3. JDBC

4. POSTGRESQL

5. MAVEN

6. TOMCATSERVER9
Testing Tools
1. POSTMAN for HTTP Request and Response Test

2. JNUNIT for Testing Java Code Logic
IDE'S
1. VS CODE for Frontend Code

2. SPRING BOOT for Backend Code

3. DBEAVER for SQL Scripts
API'S
1. Fetch API

2. Jackson API
Installation
Clone the git repository
https://github.com/Pallavi-desh/bank-app/

Extract the .zip file and Open it in Spring Boot
Build the Maven
Go to com.app.dbutil => PostgresConnection.java => set your own credentials
Run the below Queries in your DBEAVER
--Do create schema named => bank_schema
-- creating 1)employeedetails table
create table employeedetails(empusername varchar primary key,emppassword varchar not null , empname varchar not null);
insert into employeedetails (empusername,emppassword,empname) values('pallavi123','123','Pallavi');

-- creating 2) custlogindetails table
create table custlogindetails(name varchar not null,email varchar not null,username varchar primary key,password varchar not null);

-- creating 3) customer_personal_info table
create table customer_personal_info(custusername varchar primary key, custfname varchar not null, custlname varchar not null, custgender varchar not null,
custdob varchar not null,
custmobileno varchar not null unique,
custpan varchar not null unique,
custcity varchar not null,
custstate varchar not null,
openingbalance float4 not null);


-- creating 4) custacctdetails
create table custacctdetails(custfname varchar not null,
custusername varchar primary key,
openingbalance float4 not null,
acctcreatdate date default CURRENT_DATE);

-- creating 5) custtransaction
create table custtransaction(tid bigserial primary key,
ttype varchar not null,
openingbalance float4,
tamount float4,
tdate date default CURRENT_DATE,
closingbalance float4,
custusername varchar not null,
foreign key (custusername) references custacctdetails(custusername));

select * from employeedetails;
After Succesfully creation of schema and running the quries.
Go to the Project
=> Right Click on Project name and Run it as Server
=> Your are good to Go!!! :)
