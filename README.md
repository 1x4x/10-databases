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
> [!NOTE]
> INSERT INTO person (Fnamn, Enamn, Adress, Postnr, Stad, Telefon, Email, Modell, Märke)
> VALUES ('Bo', 'Karlsson', 'Furuv. 8', '12388', 'Göteborg', '01055223', 'bokarlsson@hotmail.com', 'Volvo', 'XC90');


> INSERT INTO person (Fnamn, Enamn, Adress, Postnr, Stad, Telefon, Email, Modell, Märke)
> VALUES ('Anna', 'Nilsson', 'Borgv. 4', '14577', 'Stockholm', '07012345', 'annapanna@live.se', 'BMW', 'M3');



2. Every time we add a new car for Bo, we have to re-enter his details.<br>
a. Provide at least two reasons why this is not ideal.<br>
> [!NOTE]
> Reduntant "person data" about Bo in every row containing every car Bo owns
> If another developer in the company that did not build this part is tasked to change this in the future they will maybe not understand that the same data is saved in multiple places and can for example change the data in 1 place but then its still wrong in the other places (rows) and can have unintended effects in the system. for example maybe a package will be sent to the wrong adress if the addresss would be used for that.

3. To solve this problem, we need a primary key and a secondary key. Define these terms and<br>
explain the difference between them.<br>
4. Is a personal identity number (personnummer) a good choice for a primary key? Justify your answer.<br>
5. Should a secondary key be unique? Justify your answer.<br>
6. What is the difference between data and information?<br>
7. Provide examples for at least two of the following types of relationships: one-to-one, one-to-many, and many-to-many.<br>
8. Restructure the table so that the car owner's details only need to be entered once.<br>







Frågor och Svar<br>
1. Lägg in ytterligare två bilar för Bo Karlsson i tabellen.<br>
2. Varje gång vi lägger in en ny bil för Bo måste vi skriva hans uppgifter igen.<br>
a. Ange minst två skäl till varför detta inte är bra.<br>
3. För att lösa problemet behöver vi primärnyckel och sekundärnyckel. Beskriv dessa och<br>
ange vad skillnaden är.<br>
4. Är personnummer ett bra val för en primärnyckel? Motivera.<br>
5. Ska sekundärnyckeln vara unik? Motivera.<br>
6. Vad är skillnaden på data och information?<br>
7. Ge exempel på de minst två av relationerna en till en, en till många och många till många.<br>
8. Gör om tabellen så att vi endast behöver mata in bilägarens uppgifter en gång.<br>



