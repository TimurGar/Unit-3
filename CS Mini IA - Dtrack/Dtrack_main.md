# Computer Science mini IA| Dtrack
### By Timur Garifullin
## Criteria A: Planning
### Context of the product
My dad has a diabity type-1 therefore he has an increased amount of sugar in the blood. To decrease the amount of sugar you need to exercise(Ex: running). 
Decreased amount of sugar means less insulin has to be injected therefore your liver stays more healthy and so a better quality of life. To keep track of the blood sugar my dad exercises a lot, he at least once a day.
He needs to keep track of his activities and for now he uses notices of the smartphone which takes a lot of time to organise and he constantly afraid to lose his data.
My dad would like to have a program that would make it very easy to add and view the activities that he does and so my dad asked me to create an app that would solve his problems with keeping his activities.

After interviewing my dad I understood what problems he is currently facing(translated from Russian):
 1. It takes a long time to add new activity, no templates are available
 1. It takes a long time to organise and view actvities in the notes 
 1. There are a constant fear of accidently deleting activities
 1. No security, everybody who has an unlocked phone can view my dad's activity

Additional requests:
My dad would like to see a total distance conbined from all the activities that he has travelled so far for the motivational purposes.

 Based on the problems listed above as well as additional requests I decided to create an app called Dtrack which will solve my dad's problems. The program will have a Log In/Out screen to make sure no one except my dad can view his activity. It will have an easy to understand UI(user interface) which my allow my dad to navigate in the application and to easlity view his activity. The program will calculate the total distance travelled so far(from all the activities). The program will also allow my dad to quickly add new activity by just filling out a few spaces. All the activities as well as the user information will be stored in the database to prevent the lost of data.

### Sketches of the ideas
![](https://github.com/TimurGar/Unit-3/blob/main/CS%20Mini%20IA%20-%20Dtrack/Sketches%20of%20the%20ideas.png)
Fig.1 Sketches of the application. The design for all five screens(Log In/Out, Register, Home, All activities, New activity) are shown as well as how they interract with one another

## Criteria B: Design
### System Diagram
![](https://github.com/TimurGar/Unit-3/blob/main/CS%20Mini%20IA%20-%20Dtrack/System%20diagram%20Dtrack.png)
Fig.2 System diagram of the Dtrack app
### ER diagram
![](https://github.com/TimurGar/Unit-3/blob/main/CS%20Mini%20IA%20-%20Dtrack/ER%20diagram%20Dtrack%20app.png)
Fig.3 Er diagram of the Dtrack app. The diagram shows that the program will have 2 data tables in the database called User and Activity. One User may have N number of Activities therefore the relanship shown on the diagram is one to many. The User data table will store: username, email, password, and id(primary key). The Activity data table will store: distance, type of activity, date, and id(primary key).

### Record of tasks
| Task No. | Action                                                                        | Planned outcome                                                                                          | Time estimated | Target Completion date | Criteria |
|----------|-------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|----------------|------------------------|----------|
| 1        | Planning: Discuss the context of the situation(1st interview with the client) | Written context of the problem                                                                           | 15 min         | March 18th             | A        |
| 2        | Design: Created the system diagram and the ER diagram of the app              | Completed an ER  and  system diagrams explaining and showing the process of how the app works            | 60 min         | March 19th             | B        |
| 3        | Development: Finish Log In/Out screen and Register screen for the app         | Working Log In/Out screen and Register screen which are able to add and check the data from the database | 120 min        | March 20th             | C        |
| 4        | Development: Create a Home screen and New Activity screen for the app         | Working Home and New Activity screen                                                                     | 180 min        | March 21th             | C        |
| 5        | Development: Create an All activities screen for the app                      | Working All Activities screen                                                                            | 120 min        | March 21th             | C        |
| 6        | Development: Check the program, write comments, fix small bugs                | Finished and working as intended app                                                                     | 60 min         | March 23th             | C        |
| 7        | Evaluation: Do testing(User acceptance testing, alpha testing, beta testing)  | All tested has been completed and documented                                                             | 120 min        | March 25the            | E        |



Table.1 My plan for developing an app. The process is split up into stages for organizational and time consumption purposes

## Criteria C: Development
### Developement story No.1
One of the biggest problems that I have encountered while developing Dtrack app was the creation of the All Activities screen. When you look at it, it seems pretty easy to make but it actually took me about 4 hours to create just that screen. The reason for that is that it has a lot of backend code(main.py) which is also closely connected to the front-end(main.kv). I really wanted to challenge myself and so I put a very high requirements for this screen. 
This is the list of the requirements that I have put to myself while creating All Activites screen:
1. It has to get and display all the information about every activity on the screen
1. Only activities that are corresponded to a specific user has to be displayed
1. Activities has to be filtered by date(most recent one on top)
1. The screen should have a scrolling fiature to make sure the activities don't go over the boundries 
1. The screen should look like a table 

At first I didn't really know how to just get the information from the database and just display it on the screen. I was pretty sure that it was simple but I couldn't find a write article to meet my first requirement for the screen. I knew it is related to referencing elements by the use of "ids" of elements but we I did that it didn't work. After reading many articles, mainly on Stack Overflow I accidently fount that one person typed .text when he referencing the element. So I decided to try it out and it finaly worked. 
