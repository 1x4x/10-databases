# 10-databases
| Fnamn | Enamn | Adress | Postnr | Stad | Telefon | Email | Modell | Märke |
|-------|-------|--------|--------|------|---------|-------|--------|-------|
| Lars | Persson | Skolg. 2 | 23456 | Hässleholm | 07212344 | lars@live.se | Ferrari | F40 |
| Anna | Nilsson | Borgv. 4 | 14577 | Stockholm | 07012345 | anna@live.se | Bugatti | Veyron |
| Anna | Nilsson | Borgv. 4 | 14577 | Stockholm | 07012345 | anna@live.se | Mercedes | C112 |
| Lars | Persson | Skolg. 2 | 23456 | Hässleholm | 07212344 | lars@live.se | Toyota | Corolla |
| Bo | Karlsson | Furuv. 8 | 12388 | Göteborg | 01055223 | bo@live.se | Nissan | Pulsar |
| Lars | Persson | Skolg. 2 | 23456 | Hässleholm | 07212344 | lars@live.se | Ford | Mustang |


## Questions and Answers<br>
1. Add two more cars for Bo Karlsson to the table.<br>
> INSERT INTO person (Fnamn, Enamn, Adress, Postnr, Stad, Telefon, Email, Modell, Märke)
> VALUES ('Bo', 'Karlsson', 'Furuv. 8', '12388', 'Göteborg', '01055223', 'bo@live.se', 'Volvo', 'XC90');

> INSERT INTO person (Fnamn, Enamn, Adress, Postnr, Stad, Telefon, Email, Modell, Märke)
> VALUES ('Bo', 'Karlsson', 'Furuv. 8', '12388', 'Göteborg', '01055223', 'bo@live.se', 'BMW', 'M3');

## Here are the table after we added 2 more cars for Bo
| Fnamn | Enamn | Adress | Postnr | Stad | Telefon | Email | Modell | Märke |
|-------|-------|--------|--------|------|---------|-------|--------|-------|
| Lars | Persson | Skolg. 2 | 23456 | Hässleholm | 07212344 | lars@live.se | Ferrari | F40 |
| Anna | Nilsson | Borgv. 4 | 14577 | Stockholm | 07012345 | anna@live.se | Bugatti | Veyron |
| Anna | Nilsson | Borgv. 4 | 14577 | Stockholm | 07012345 | anna@live.se | Mercedes | C112 |
| Lars | Persson | Skolg. 2 | 23456 | Hässleholm | 07212344 | lars@live.se | Toyota | Corolla |
| Bo | Karlsson | Furuv. 8 | 12388 | Göteborg | 01055223 | bo@live.se | Nissan | Pulsar |
| Lars | Persson | Skolg. 2 | 23456 | Hässleholm | 07212344 | lars@live.se | Ford | Mustang |
| Bo | Karlsson | Furuv. 8 | 12388 | Göteborg | 01055223 | bo@live.se | Volvo | XC90 |
| Bo | Karlsson | Furuv. 8 | 12388 | Göteborg | 01055223 | bo@live.se | BMW | M3 |


2. Every time we add a new car for Bo, we have to re-enter his details.<br>
a. Provide at least two reasons why this is not ideal.<br>

> 1. Data redundancy: We have to enter Bo's personal information (name, address, phone number, email, etc.) every time we add a new car. This wastes storage space and makes the database less efficient.

> 2. Risk of inconsistent data: If Bo changes his address or phone number, we must update every record associated with him. If we forget to update one, the database will contain incorrect or inconsistent information.

> 3. Increased risk of errors: Re-entering the same information multiple times increases the chance of typing mistakes.

> Solution: Split the table into two separate tables: one for people (Person) and one for cars (Car). Connect them using a primary key and foreign key. This way, Bo's personal information is stored only once, and we can add new cars without repeating it. This is called database normalization.

3. To solve this problem, we need a primary key and a secondary key. Define these terms and<br>
explain the difference between them.<br>
> Primary Key (PK): A primary key is a unique identifier for each record in a database table. It ensures that every record can be identified individually. > A primary key cannot contain duplicate or NULL values.

> Secondary Key: A secondary key is a field used to help search, sort, or retrieve data. Unlike a primary key, it does not have to be unique and can contain duplicate values.

> Difference: A primary key uniquely identifies each record, while a secondary key is mainly used to make searching and retrieving data easier.
> Example using our database
> - Primary Key: PersonID – A unique number assigned to each person, such as Bo Karlsson having PersonID = 3.
> - Secondary Key: Enamn – Can be used to search for people by their last name, even if multiple people have the same last name.
> Important: To solve our original problem, we actually need a foreign key (FK) rather than a secondary key. A foreign key connects two tables by referencing a primary key in another table.

> For example, the Car table can use PersonID = 3 as a foreign key to connect Bo Karlsson to all his cars without repeating his personal information.

4. Is a personal identity number (personnummer) a good choice for a primary key? Justify your answer.<br>
> A personal identity number (personnummer) can be used as a primary key because it is unique to each person and helps prevent duplicate records.

> However, it is not the best choice because it contains sensitive personal information, which creates privacy and security risks. It can also cause problems if a person's identity number changes or needs to be corrected.

> A better solution is to use an automatically generated PersonID as the primary key. This keeps personal information separate and makes the database easier to manage.

5. Should a secondary key be unique? Justify your answer.<br>
> No, a secondary key does not have to be unique because its purpose is to help search, sort, and retrieve data rather than uniquely identify each record.

> For example, if Enamn (last name) is a secondary key, multiple people can have the same last name, such as "Karlsson". The database can still use it to find all people with that name.

> Unlike a primary key, a secondary key can contain duplicate values.

6. What is the difference between data and information?<br>

> Data is raw facts and values that have not yet been processed or organized, such as names, numbers, or dates.

> Information is data that has been processed, organized, or given context so that it becomes meaningful and useful.

> Example:
> - Data: "Bo", "Karlsson", "Volvo", "XC90".
> - Information: "Bo Karlsson owns a Volvo XC90."
> The main difference is that data consists of raw facts, while information gives those facts meaning and context.

7. Provide examples for at least two of the following types of relationships: one-to-one, one-to-many, and many-to-many.<br>
> 1. One-to-One (1:1): One record in a table is connected to exactly one record in another table.
> - Example: One person has one passport, and each passport belongs to one person.
> 2. One-to-Many (1:N): One record in a table can be connected to multiple records in another table.
> - Example: Bo Karlsson owns multiple cars (Volvo XC90, BMW M3, Nissan Pulsar), but each car belongs to only one person.
> 3. Many-to-Many (M:N): Multiple records in one table can be connected to multiple records in another table.
> - Example: A student can attend multiple courses, and each course can have multiple students.


8. Restructure the table so that the car owner's details only need to be entered once.<br>

> To avoid entering the same owner's details multiple times, we can split the original table into two separate tables: Person and Car. One-toMany (1:N).

> Each person gets a unique PersonID (Primary Key), and each car uses PersonID as a Foreign Key to identify its owner.
## 1. Person Table
<br>
> Stores each person's information only once.
| PersonID (PK) | Fnamn | Enamn | Adress | Postnr | Stad | Telefon | Email |
|---------------|-------|-------|--------|--------|------|---------|-------|
| 1 | Lars | Persson | Skolg. 2 | 23456 | Hässleholm | 07212344 | lars@live.se |
| 2 | Anna | Nilsson | Borgv. 4 | 14577 | Stockholm | 07012345 | anna@live.se |
| 3 | Bo | Karlsson | Furuv. 8 | 12388 | Göteborg | 01055223 | bo@live.se |

## 2. Car Table
<br>
> Stores each car separately and connects it to its owner using PersonID.
| CarID (PK) | PersonID (FK) | Modell | Märke |
|------------|---------------|--------|-------|
| 1 | 1 | Ferrari | F40 |
| 2 | 2 | Bugatti | Veyron |
| 3 | 2 | Mercedes | C112 |
| 4 | 1 | Toyota | Corolla |
| 5 | 3 | Nissan | Pulsar |
| 6 | 1 | Ford | Mustang |
| 7 | 3 | Volvo | XC90 |
| 8 | 3 | BMW | M3 |



> - Primary Key (PK): Uniquely identifies each person or car.
> - Foreign Key (FK): Connects each car to its owner.
> - One-to-Many (1:N): One person can own multiple cars, but each car has one owner in this database.
> Result: When Bo Karlsson buys another car, we only need to add a new record to the Car table using PersonID = 3. His personal information does not need to be entered again.

> This process is called database normalization, which reduces duplicated data and makes the database easier to maintain.





