# lunar Homework

## ER diagram for the database
![](https://github.com/TimurGar/Unit-3/blob/main/ER%20diagram%20for%20Phone%20Store%20Application.png)
Fig 1. Image of the ER diagram for the Phone store

![](https://github.com/TimurGar/Unit-3/blob/main/Phone%20store%20db.png)
Fig 2. Image of the table of the Phone store database 


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



## UML diagram for the database
![](https://github.com/TimurGar/Unit-3/blob/main/UML%20diagram%20for%20Phone%20store.png)
Fig 3. Image of the UML diagram for the Phone store

## Creating the database using ORM and adding some sample users
```.py
# Phone store database using ORM

from sqlalchemy import Column, DateTime, String, Integer, ForeignKey
from sqlalchemy.ext.declarative import declarative_base
from sqlalchemy.orm import relationship

Base = declarative_base()

class User(Base):
    __tablename__ = 'user'
    id = Column(Integer, primary_key=True)
    name = Column(String)
    email = Column(String)
    purchaseDate = Column(String)
    phone = Column(Integer)

    def __repr__(self):
        return f"<User with username {self.username} with email {self.email}>"

#create the database and the connection
from sqlalchemy import create_engine
engine = create_engine('sqlite:///GenericApplicationDB.sqlite')

from sqlalchemy.orm import sessionmaker
session = sessionmaker()
session.configure(bind=engine)
Base.metadata.create_all(engine)

s = session()

# Adding new users

user1 = User(id=1,name= 'Juan',phone= 12345678,email='juan@gmail.com',purchaseDate='2020-11-20')
user2 = User(id=2,name='Ben',phone= 34579388,email='ben@email.es',purchaseDate='2014-05-13')
user3 = User(id=3,name='Tim',phone= 9760492,email='timtim@gmail.com',purchaseDate='2021-01-01')
s.add(user1)
s.add(user2)
s.add(user3)
s.commit()
s.close()
```
![](https://github.com/TimurGar/Unit-3/blob/main/Phone%20store%20db.png)
Fig 4. Image of the table of the Phone store database created using ORM
