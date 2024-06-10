# copilot-demo-github-java

A small demo project to exercise the basic capabilities of Copilot in ***Visual Studio Code***. In this demo you should develop Java coding for Flight reservation that you can access from the UI. We use copilot/chat to help in developing Java coding. Enjoy !

## Pre-Requisits
- Make sure to have...

<img width="50%" src="images/copilot-and-chat.png">

...correctly installed in Visual Studio Code

...correctly installed in Mysql workbench

...create Database using this 

```
CREATE DATABASE RESERVATION;

USE RESERVATION;

CREATE TABLE FLIGHT
(
  ID INT  NOT NULL AUTO_INCREMENT,
  FLIGHT_NUMBER VARCHAR(20)  NOT NULL, 
  OPERATING_AIRLINES VARCHAR(20)  NOT NULL,
  DEPARTURE_CITY VARCHAR(20)  NOT NULL,
  ARRIVAL_CITY VARCHAR(20)  NOT NULL,
  DATE_OF_DEPARTURE DATE  NOT NULL,
  ESTIMATED_DEPARTURE_TIME TIMESTAMP DEFAULT CURRENT_TIMESTAMP,  
  PRIMARY KEY (ID)
);

CREATE TABLE PASSENGER
(
  ID INT NOT NULL AUTO_INCREMENT,
  FIRST_NAME       VARCHAR(256),
  LAST_NAME    VARCHAR(256),
  MIDDLE_NAME   VARCHAR(256),
  EMAIL VARCHAR(50),
  PHONE VARCHAR(10),
  PRIMARY KEY (ID)
);

CREATE TABLE RESERVATION
(
  ID INT NOT NULL AUTO_INCREMENT,
  CHECKED_IN INT,
  NUMBER_OF_BAGS INT,
  PASSENGER_ID INT,
  FLIGHT_ID INT,
  CREATED TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (ID),
  FOREIGN KEY (PASSENGER_ID) REFERENCES PASSENGER(ID) ON DELETE CASCADE,
  FOREIGN KEY (FLIGHT_ID) REFERENCES FLIGHT(ID)
);


insert into flight values(1,'AA1','American Airlines','AUS',
'NYC',STR_TO_DATE('02-05-2024', '%m-%d-%Y'),'2024-02-05 03:14:07');

insert into flight values(2,'AA2','American Airlines','AUS',
'NYC',STR_TO_DATE('02-05-2024', '%m-%d-%Y'),'2024-02-05 05:14:07');

insert into flight values(3,'AA3','American Airlines','AUS',
'NYC',STR_TO_DATE('02-05-2024', '%m-%d-%Y'),'2024-02-05 06:14:07');

insert into flight values(4,'SW1','South West','AUS',
'NYC',STR_TO_DATE('02-05-2024', '%m-%d-%Y'),'2024-02-05 07:14:07');

insert into flight values(5,'UA1','United Airlines','NYC',
'DAL',STR_TO_DATE('02-05-2024', '%m-%d-%Y'),'2024-02-05 10:14:07');

insert into flight values(6,'UA1','United Airlines','NYC',
'DAL',STR_TO_DATE('02-05-2024', '%m-%d-%Y'),'2024-02-05 10:14:07');

insert into flight values(7,'SW1','South West','AUS',
'NYC',STR_TO_DATE('02-06-2024', '%m-%d-%Y'),'2024-02-06 07:14:07');

insert into flight values(8,'SW2','South West','AUS',
'NYC',STR_TO_DATE('02-06-2024', '%m-%d-%Y'),'2024-02-06 08:14:07');

insert into flight values(9,'SW3','South West','NYC',
'DAL',STR_TO_DATE('02-06-2024', '%m-%d-%Y'),'2024-02-06 10:14:07');

insert into flight values(10,'UA1','United Airlines','NYC',
'DAL',STR_TO_DATE('02-06-2024', '%m-%d-%Y'),'2024-02-06 10:14:07');
```

## Generate Entities classes

Create folder name 'entities' in this path src\main\java\com\bharath\flightreservation

Create 'Flight.java' in this path src\main\java\com\bharath\flightreservation\entities

Delete everything in Flight.java and ask copilot by using ctrl+i open up the chat prompt and type in 

```
flight jpa model class with id, flight number, operating airlines, depature city, arrival city, date of depature, estimated depature time
```
<details><summary>Output</summary> <p>

```


```
</p> </details>

As copilot gives javax it is not a right package so replace with the jakarta 

