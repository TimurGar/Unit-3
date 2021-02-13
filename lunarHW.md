# lunar Homework
![](https://github.com/TimurGar/Unit-3/blob/main/ER%20diagram%20for%20Phone%20Store%20Application.png)


Fig 1. Image of the ER diagram for the Phone store

```.py
-- Database for the phone store

CREATE TABLE IF NOT EXISTS User(
    id integer primary key autoincrement not null,
    Name varchar(30),
    Phone integer,
    email varchar(50),
    purchaseDate DATETIME
);
INSERT INTO User(NAME, PHONE, EMAIL, PURCHASEDATE)
VALUES ('Juan',12345678,'juan@gmail.com','2020-11-20'),
       ('Ben',34579388,'ben@email.es','2014-05-13'),
       ('Tim',9760492,'timtim@gmail.com','2021-01-01');
```
