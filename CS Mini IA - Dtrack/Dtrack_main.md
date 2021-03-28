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
 
### Criteria for success(based on the feedback during the interview)
Success criteria in order of priority. These criterias have been consulted with and confirmed by the client.
| No. | Success criteria                   | Explanation                                                                                                                                                                                                                              |
|-----|------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1   | Log In/Out system                  | The user should be able to enter his/her email and password into  the app and if the data entered is correct(by checking with an app database)  the user should see a Home screen.  The user should also be able to log out from the app |
| 2   | Registration system                | The user should be able to create a new account by entering  his/her personal data and the app should store this data into a database                                                                                                    |
| 3   | Adding new activities              | The user should be able to add new activities by filling out a form and  the app should store this data into a database                                                                                                                  |
| 4   | Viewing most recent activity       | The app should be able to sort all the activities added by a user and  display the most recent activity on the screen                                                                                                                    |
| 5   | Viewing total distance             | The app should be able to calculate the total distance traveled by  a user from all his/her activities                                                                                                                                   |
| 6   | Viewing all activities             | The app should be able to display all the activities added by a user  in a form of a table. Activities must be sorted by date(most recent on top)                                                                                        |
| 7   | High usability and pleasing design | The app should have easy to navigate user interface. No instructions or manual needed.                                                                                                                                                   |


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
One of the biggest problems that I have encountered while developing Dtrack app was trying to display a data(like a value from the database) on the screen. Not knowing this information was a huge struggle for me as I had to use it pretty often(Especially in the All Activities screen as it almost fully based on displaying and working with the data from a database). I was pretty sure that it was simple but it still took the whole day to solve. I knew it was related to referencing elements by the use of "ids" of elements but when I did that it didn't work. It just didn't print anything and because my development environment(PyCharm) didn't show any errors as my code was technically right, I couldn't understand my mistake. After reading so many articles, mainly on Stack Overflow, I accidentally found that one person typed ".text" it the end when he referencing the element(the article actually wasn't connected at all to the problem I was trying to solve). So I decided to try it out and it finally worked. I was very exhausted as I spent the whole day trying to solve just one problem but at the same time I learned that I can actually overcome any problem if I will put enough time and effort into it.

### Code for Dtrack app
### main.py | backend of the application
```.py
# Backend code for the Dtrack app
# does all necessary calculations; creates,manages database and all data related to database,
# creates all the necessary functions and screens for the app
# displays some of the data on the screens

# Importing all necessery libraries and widgets for the app
from sqlalchemy import Column, Date, String, Integer, ForeignKey, desc
from sqlalchemy.ext.declarative import declarative_base
from kivymd.app import MDApp
from kivymd.uix.label import MDLabel
from kivymd.uix.screen import MDScreen
from kivymd.uix.picker import MDDatePicker

# Creating a base to connect with the database
Base = declarative_base()

# Creating a User table in the database
class User(Base):
    __tablename__ = 'user'
    id = Column(Integer, primary_key=True)
    username = Column(String)
    password = Column(String)
    email = Column(String)

# Creating an Activity table in the database
class Activity(Base):
    __tablename__ = 'activity'
    id = Column(Integer, primary_key=True)
    distance = Column(Integer)
    type_of_activity = Column('type_of_activity', String)
    date = Column(Date)

    # Creating a one-to-mane relationship between User and Activity tables
    user_id = Column(Integer, ForeignKey('user.id'))

# Creating a database
from sqlalchemy import create_engine

engine = create_engine('sqlite:///app.sqlite')

# Creating a connection with a database
from sqlalchemy.orm import sessionmaker
session = sessionmaker()
session.configure(bind=engine)
Base.metadata.create_all(engine)
s = session()

# Backend code for the Register screen
class RegisterScreen(MDScreen):
    # Functions that does registration processes
    def try_register(self):
        # saves all the inputs typed in text fields in a corresponding variables
        email = self.ids.email_input.text
        psw = self.ids.password_input.text
        psw_check = self.ids.password_check.text
        username = self.ids.username.text

        # checking if the confirmation password is equal the password
        if psw != psw_check:
            print("password do not match")
        else:

            # Check if the user is not register already
            user_check = s.query(User).filter_by(username=username, email=email, password=psw).first()
            print(user_check)

            # If the result is not equal to None(if that email and password wasn't found)
            if user_check:
                # there is a user already with this email
                print("Email already registered")

            # Making sure that the email contains "@"
            elif "@" not in email:
                self.ids.email_input.error = True
                self.ids.email_input.helper_text = "Email is not valid"
                print("Email is invalid")

            else:
                # adding a new user to a database
                usr = User(username=username, email=email, password=psw)
                s.add(usr)
                s.commit()
                print(f"User <{username}> with email <{email}> and password: <{psw}> has been created")


# Backend code for the Login screen
class LoginScreen(MDScreen):
    current_user_id = None
    current_user_username = None

    # Making sure that the email contains "@"
    def validate_input(self):
        input_email = self.ids.email_input.text
        if "@" not in input_email:
            self.ids.email_input.error = True
            self.ids.email_input.helper_text = "Email is not valid"

    # Functions that does login
    # makes sure the email and password entered in the text field are correct
    def try_login(self):
        # saves all the inputs typed in text fields in a corresponding variables
        email = self.ids.email_input.text
        psw = self.ids.password_input.text
        # Gets email and password data from the database
        user_check = s.query(User).filter_by(email=email, password=psw).first()

        if user_check:  # if the result different of None
            s.close()
            # id, username, password, email = user_check
            print(f"login succeful for user with email {email} and password {psw}")
            # saves user id and username for a later use(in the home screen)
            LoginScreen.current_user_id = user_check.id
            LoginScreen.current_user_username = user_check.username
            # Go to the Home screen
            self.parent.current = "HomeScreen"
        else:
            print("User does not exist")

# Backend code for the Activity screen
class ActivityScreen(MDScreen):
    selected_date = None
    type_of_activity = None
    distance = None

    # Following three functions control the calendar
    # ---
    def on_save(self, instance, value, date_range):
        title = "Selected date: "
        # Print the date on the activity screen
        date_output = title + str(value)
        self.ids.date_picker_label.text = date_output
        ActivityScreen.selected_date = value

    def on_cancel(self, instance, value):
        '''Events called when the "CANCEL" dialog box button is clicked.'''

    def show_date_picker(self):
        date_dialog = MDDatePicker()
        date_dialog.bind(on_save=self.on_save, on_cancel=self.on_cancel)
        date_dialog.open()
    # ---

    def create_new_activity(self):
        print("activity created")
        type_of_activity = self.ids.type_of_activity_input.text
        distance_travelled_input = self.ids.distance_travelled_input.text
        selected_date = ActivityScreen.selected_date

        # Saves data typed in the type_of_activity,distance_travelled_input,
        # selected_date text fields for later use
        ActivityScreen.selected_date = selected_date
        ActivityScreen.type_of_activity = type_of_activity
        ActivityScreen.distance = distance_travelled_input

        print(
            f"New activity named {type_of_activity} has been created, distance travelled = {distance_travelled_input}.  It happened on {selected_date}")
        # Adds all the entered data in the database
        activity = Activity(distance=distance_travelled_input, type_of_activity=type_of_activity, date=selected_date,
                            user_id=LoginScreen.current_user_id)
        s.add(activity)
        s.commit()

# Backend code for the Home screen
class HomeScreen(MDScreen):

    # following function automatically initiates
    # a function once an user enters a screen.
    def on_pre_enter(self, *args):
        self.user_recent_activity()
        self.user_total_distance()

    def user_recent_activity(self):
        self.ids.recent_activity.text = f"{str(LoginScreen.current_user_username)}, your most recent activity was:"

        # finding the most recent activity by ordering them by date using order_by
        recent_activity = s.query(Activity).order_by(desc('date')).filter_by(
            user_id=LoginScreen.current_user_id).first()
        # Checking if the user have any activities at all
        if recent_activity:
            self.ids.recent_activity_info.text = f"{recent_activity.type_of_activity} for {recent_activity.distance} meters on {recent_activity.date}"
        else:
            self.ids.recent_activity_info.text = "You have no activities yet"

    # Calculating the total distance travelled by a user in all the activities
    def user_total_distance(self):
        total_distance = 0
        activity_data = s.query(Activity).filter_by(user_id=LoginScreen.current_user_id).all()
        for d_value in activity_data:
            total_distance += d_value.distance
        self.ids.total_distance.text = f"{str(total_distance)} m"

# Backend code for the All Activities screen
class AllActivitiesScreen(MDScreen):

    # Function that prints all activity data on the screen
    def print_data(self):
        # Clearing all the widgets(in this case text) on the page
        # to prevent redundancy of the data
        self.ids.container.clear_widgets()
        # Getting data from the database
        activities = s.query(Activity).order_by(desc('date')).filter_by(user_id=LoginScreen.current_user_id).all()

        # Creating labels - Headings for the columns
        activity = MDLabel(text="Activity", font_style="H4", halign="center")
        self.ids.container.add_widget(activity)
        distance = MDLabel(text="Distance", font_style="H4", halign="center")
        self.ids.container.add_widget(distance)
        date = MDLabel(text="Date", font_style="H4", halign="center")
        self.ids.container.add_widget(date)

        # display the data such as type of the activity, distance, date
        for data in activities:
            type = MDLabel(text=str(data.type_of_activity), halign="center")
            self.ids.container.add_widget(type)
            dist = MDLabel(text=str(data.distance), halign="center")
            self.ids.container.add_widget(dist)
            date = MDLabel(text=str(data.date), halign="center")
            self.ids.container.add_widget(date)

# Backend code for the Kivy's whole application
class MainApp(MDApp):
    def build(self):
        self.theme_cls.primary_palette = "Red"
        # Adding an app icon
        self.icon = 'Dtrack app icon.png'

# Running the whole Kivy application
MainApp().run()
```
### main.kv | front-end of the application
```.py
# Creating a screen manager for all the screens
ScreenManager:
    id: scr_manager

#   The top screen in the screen manager will be displayed first(right when the program starts)
#   In this case it is a Login screen
    LoginScreen:
        name: "LoginScreen"

    HomeScreen:
        name: "HomeScreen"

    RegisterScreen:
        name: "RegisterScreen"

    ActivityScreen:
        name: "ActivityScreen"

    AllActivitiesScreen:
        name: "AllActivitiesScreen"

# Front-end code for the Register screen
<RegisterScreen>:

#   Vertical BoxLayout positions all the elements inside in a vertical line(on top of one another)
    BoxLayout:
        orientation: 'vertical'
        size: root.height, root.width
        FitImage:
            source: "Background_image_Register.jpg"

    MDCard:
        size_hint: 0.5, 0.75
        elevation: 10
        pos_hint: {"center_x": 0.5, "center_y": 0.5}
        orientation: "vertical"

        # Changing the color of background of a MDCard
        # last parameter responsible for the opacity of the MDCard
        md_bg_color:[255/255, 255/255, 255/255, 0.4]

        MDBoxLayout:
            id: content #id or name
            adaptive_height: True
            orientation: "vertical"
            padding: dp(30)
            spacing: dp(15)

            MDIconButton:
                icon: "keyboard-backspace"
                theme_text_color: "Custom"
                text_color: app.theme_cls.primary_color
                on_press:
                    root.parent.current = "LoginScreen"

            MDLabel:
                text: "REGISTER"
                font_style: "H3"
                halign: "center"
            MDTextField:
                id: username
                hint_text: "Username"
                icon_right: "account"
                helper_text: "Invalid username"
                helper_text_mode: "on_error"
                required: True

            MDTextField:
                id: email_input
                hint_text: "Email"
                icon_right: "email"
                helper_text: "Invalid email"
                helper_text_mode: "on_error"
                required: True

            MDTextField:
                id:password_input
                hint_text: "Password"
                icon_right: "form-textbox-password"
                helper_text: "Invalid password"
                helper_text_mode: "on_error"
                required: True
                password: True

            MDTextField:
                id:password_check
                hint_text: "Confirm password"
                icon_right: "form-textbox-password"
                helper_text: "Invalid password"
                helper_text_mode: "on_error"
                required: True
                password: True

            MDRaisedButton:
                text: "Register"
                on_release:
                    root.try_register()

# Front-end code for the Login screen
<LoginScreen>:
    BoxLayout:
        orientation: 'vertical'
        size: root.height, root.width

        FitImage:
            source: "Backgrougn_Image_login.jpg"

    MDCard:
        size_hint: 0.5, 0.75
        elevation: 10
        pos_hint: {"center_x": 0.5, "center_y": 0.5}
        orientation: "vertical"


        # make it transparent
        md_bg_color:[255/255, 255/255, 255/255, 0.6]

        FitImage:
            source: "Dtrack logo.png"
            pos_hint: {"center_x": 0.3, "center_y": 0.5}
            size_hint: 0.5, 0.5


        MDBoxLayout:
            id: content #id or name
            adaptive_height: True
            orientation: "vertical"
            padding: dp(30)
            spacing: dp(20)

            MDLabel:
                text: "LOGIN"
                pos_hint: {'center_x': 0.5, 'center_y': 0.3}
                font_style: "H3"
                halign: "center"

            MDTextField:
                id: email_input
                hint_text: "Email"
                icon_right: "email"
                helper_text_mode: "on_error"
                required: True
                on_text_validate:
                    root.validate_input()

            MDTextField:
                id: password_input
                hint_text: "Password"
                icon_right: "form-textbox-password"
                helper_text_mode: "on_error"
                required: True
                password: True

            MDRectangleFlatIconButton:
                icon: 'login'
                text: "Log in"
                padding: dp(10)
                on_release:
                    root.try_login()

            MDRectangleFlatIconButton:
                icon: "human-greeting"
                text: 'Register'
                padding: dp(10)
                font_size: "15sp"
                on_press:
                    root.parent.current = "RegisterScreen"

# Front-end code for the Activity screen
<ActivityScreen>:
    BoxLayout:
        orientation: 'vertical'
        size: root.height, root.width

        FitImage:
            source: "ActivityScreen Background.jpg"

    MDCard:
        size_hint: 0.5, 0.70
        elevation: 10
        pos_hint: {"center_x": 0.5, "center_y": 0.5}
        orientation: "vertical"


        # make it transparent
        md_bg_color:[255/255, 255/255, 255/255, 0.65]

        MDBoxLayout:
            id: content #id or name
            adaptive_height: True
            orientation: "vertical"
            padding: dp(30)
            spacing: dp(20)

            MDIconButton:
                icon: "keyboard-backspace"
                theme_text_color: "Custom"
                text_color: app.theme_cls.primary_color
                on_press:
                    root.parent.current = "HomeScreen"

            MDLabel:

            MDLabel:
                text: "New Activity"
                pos_hint: {'center_x': 0.5, 'center_y': 0.3}
                font_style: "H3"
                halign: "center"

            MDTextField:
                id: type_of_activity_input
                hint_text: "Type of activity"
                icon_right: "run-fast"
                helper_text: "This space should be filled out"
                helper_text_mode: "on_error"
                required: True

            MDTextField:
                id: distance_travelled_input
                hint_text: "Distance travelled(m)"
                icon_right: "map-marker-distance"
                helper_text: "This space should be filled out"
                helper_text_mode: "on_error"
                required: True

#           Calendar: creating "select a date" button and print selected date on the screen
            MDBoxLayout:
                orientation: "horizontal"
                spacing: dp(20)

                MDRectangleFlatIconButton:
                    icon: 'calendar'
                    text: "Select a date"
                    pos_hint: {'center_x': .15, 'center_y': .5}
                    on_release: root.show_date_picker()

                MDLabel:
                    id: date_picker_label
                    size_hint: None, None
                    size: dp(48)*3, dp(48)
                    pos_hint: {'center_x': .25, 'center_y': .5}

            MDLabel:

            MDRaisedButton:
                text: "CREATE"
                padding: dp(50)
                on_release:
                    root.create_new_activity()
                    root.parent.current = "HomeScreen"

            MDLabel:

# Front-end code for the All Activities screen
<AllActivitiesScreen>:

#   Implementing a scrolling option(vertical only by default)
    ScrollView:

        MDCard:
            size_hint: 1, 0
            elevation: 0
            pos_hint: {"center_x": 0.5, "top": 1}
            orientation: "vertical"

            MDCard:
                size_hint: 1, 0.1
                elevation: 0
                padding: 30
                pos_hint: {"center_x": 0.5, "top": 0.8}
                orientation: "horizontal"

                MDIconButton:
                    icon: "keyboard-backspace"
                    theme_text_color: "Custom"
                    pos_hint: {"center_x": 0.1, "top": 0.6}
                    text_color: app.theme_cls.primary_color
                    on_press:
                        root.parent.current = "HomeScreen"

                MDIconButton:
                    icon: "refresh"
                    theme_text_color: "Custom"
                    pos_hint: {"center_x": 0.1, "top": 0.6}
                    text_color: app.theme_cls.primary_color
                    on_press:
                        root.print_data()

                MDLabel:
                    text: "<-- refresh to view"
                    pos_hint: {'center_x': 0.1, 'top': 1}
                    font_style: "Subtitle1"
                    halign: "left"

            GridLayout:
                id: container
                cols: 3
                padding: 50
                spacing: 30
                row_default_height: 60
                row_force_default: True
                pos_hint_y: 0

        #        Column 1
                MDLabel:
                    id: col1
                    text: "Activity"
                    font_style: "H4"
                    halign: "center"

        #        Column 2
                MDLabel:
                    id: col2
                    text: "Distance"
                    font_style: "H4"
                    halign: "center"

        #        Column 3
                MDLabel:
                    id: col3
                    text: "Date"
                    font_style: "H4"
                    halign: "center"

# Front-end code for the Home screen
<HomeScreen>:
    BoxLayout:
        orientation: 'vertical'
        size: root.height, root.width

        FitImage:
            source: "Background_Image_Home.jpg"

    MDCard:
        size_hint: 0.5, 0.75
        elevation: 10
        pos_hint: {"center_x": 0.5, "center_y": 0.5}
        orientation: "vertical"

        # Changing the color of background of a MDCard
        # last parameter responsible for the opacity of the MDCard
        md_bg_color:[255/255, 255/255, 255/255, 0.5]

        MDBoxLayout:
            id: content #id or name
            adaptive_height: True
            orientation: "vertical"
            padding: dp(30)
            spacing: dp(50)

            MDRectangleFlatIconButton:
                icon: 'logout'
                text: "Log out"
                padding: dp(10)
                pos_hint: {'center_x': 0.1, 'center_y': 0.3}
                on_release:
                    root.parent.current = "LoginScreen"

            MDLabel:
                text: "Home"
                pos_hint: {'center_x': 0.5, 'center_y': 0.4}
                font_style: "H3"
                halign: "center"

            MDLabel:
                id: recent_activity
                pos_hint: {'center_x': 0.5, 'center_y': 0.5}
                font_style: "H6"
                halign: "left"

            MDLabel:
                id: recent_activity_info
                pos_hint: {'center_x': 0.5, 'center_y': 0.6}
                font_style: "Subtitle1"
                halign: "left"

            MDCard:
                elevation: 0
                orientation: "horizontal"
                pos_hint: {"center_x": 0.5, "center_y": 0.7}

                MDLabel:
                    text: "Total distance travelled:"
                    font_style: "H6"
                    halign: "left"

                MDLabel:
                    id: total_distance
                    font_style: "Subtitle1"
                    halign: "left"

            MDRectangleFlatIconButton:
                icon: 'page-previous'
                text: "All activities"
                padding: dp(10)
                on_press:
                    root.parent.current = "AllActivitiesScreen"

            MDRaisedButton:
                text: "New Activity"
                pos_hint: {'center_x': 0.15, 'top': 0.8}
                font_size: "15sp"
                on_press:
                    root.parent.current = "ActivityScreen"
```
### Developement story No.2
My second development story is going to be about my struggle of getting function “user_recent_activity()” in the Home screen to start working automatically without pressing any buttons. I wanted to make a sign that would use the username of the user and display it on the Home screen as soon as the user pressed “login” button so that when the screens would change from Login to Home, the user will be able to see “username, your most recent activity was:”. But the problem was that I couldn’t refer to a function that is located inside Home screen by pressing a button located in the Login screen, so I had to find a way to run the function “user_recent_activity()” automatically. First,I spent about one and a half hours to trying to fix this issue by using global variables but it didn’t work. Moreover, global variables would make my program less secure and more vulnerable to getting hacked	. So I again went on the internet and started reading articles and documentations. After about 2 hours of reading I found an article talking about screen manager, in which they mentioned function “on_pre_enter()”. This functions automatically initiates functions inside; once a user enters a screen. I used it and it finally worked! I once again proved to myself that I can find a way to overcome any challenge that I face, I just need enough courage to not give up.

## Criteria D: Functionality
### Login System:
Users are able to login into the app using their emails and passwords.
![](https://github.com/TimurGar/Unit-3/blob/main/CS%20Mini%20IA%20-%20Dtrack/Login%20screen.png)

Fig.4 image of the Login screen

### Registration 
Users are able to create new accounts to then be able login into the app
![](https://github.com/TimurGar/Unit-3/blob/main/CS%20Mini%20IA%20-%20Dtrack/Register%20screen.png)

Fig.5 image of the Register screen

### Home screen 
On the Home screen, each user will be able to see their most recent activity, total distance travelled from all the activities, and view all activities the user has done so far.
If the user hasn't recorded any activity yet, he will see the following:
![](https://github.com/TimurGar/Unit-3/blob/main/CS%20Mini%20IA%20-%20Dtrack/Home%20screen%20no%20acivities%20yet.png)

Fig.7 image of the Home screen of a new user, without any activities

On the other hand, users with some activities will be able to see something like this(recent activity and distance will vary depending on the user as each user has done different acitivities):

![](https://github.com/TimurGar/Unit-3/blob/main/CS%20Mini%20IA%20-%20Dtrack/Home%20screen.png)

Fig.8 image of the Home screen

### All Activities screen 
On All Activities screen user is able to view all his/her activities done(recorded) so far. Each user have different activities therfore the screen will look different for everyone. Moreover all the activities are sorted by date, most recent are going to be on top.
![](https://github.com/TimurGar/Unit-3/blob/main/CS%20Mini%20IA%20-%20Dtrack/All%20Activities%20screen.png)

Fig.9 image of the All Activities screen

### Adding new activities
Every user is able to add an unlimited amount of activites by pressing "New Activity" button on the Home screen. After pressing the button, the user will be transfered to a New Activity screen where he/she can specify the type of activity, distance travelled during the activity, as well as, the date. 

![](https://github.com/TimurGar/Unit-3/blob/main/CS%20Mini%20IA%20-%20Dtrack/New%20activity%20screen.png)

Fig.10 image of the New Activity screen

When the user will press "select a date" button to specify the date the user will see a calendar:
![](https://github.com/TimurGar/Unit-3/blob/main/CS%20Mini%20IA%20-%20Dtrack/Calendar.png)

Fig.11 image of the calendar opened by pressing "select a date" button

After the user will choose a date he/she will see a text written on the screen with the selected date.
![](https://github.com/TimurGar/Unit-3/blob/main/CS%20Mini%20IA%20-%20Dtrack/Selected%20date%20text.png)

Fig.12 image of the Selected date text

After creating a new activity all the data typed by a user will be recorded in the database and it is going to be availble to view in the All activities screen

![](https://github.com/TimurGar/Unit-3/blob/main/CS%20Mini%20IA%20-%20Dtrack/Activities%20database.png)

Fig.13 image of the Activity data table in the database with a sample of user's data

## Testing Plan
Before presenting the program to my client(my dad), I've decided to do various types of testings to make sure the program works as expected and fits for a client.
I've create a plan that I followed to test my program:
1. Alpha testing(I used Alpha,Beta testing table to check my program)
2. Beta testing with classmates(I asked my Computer Science classmate to check my program by using Alpha,Beta testing table)
3. Beta testing with an external expert(I asked an external expert, who is not taking Computer Science and not interested in app developing at all, to check my program by using Alpha,Beta testing table). This allowed me to make sure that you don't need to have any Computer Science skills to check and use my app)
4. User acceptance testing(I asked my client to try my program by using User acceptance testing table)


## Criteria E: Evaluation
Down bellow you can see Alpha,Beta testing table that I've created to check my program before doing User acceptance testing
| Testing level     | Type of Testing                                                           | Success criteria                                                                                                                                                                                                                                                                                                                                                                                                                                         | Procedures                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | Criteria Met? Alpha testing | Criteria Met? Beta testing with classmates | Criteria Met? Beta testing external expert |
|-------------------|---------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------|--------------------------------------------|--------------------------------------------|
| Unit testing      | Log In/Out system check                                                   | The user is able to log in/out to and from the app by  entering correct email and password                                                                                                                                                                                                                                                                                                                                                               | In the Login screen type the following: "test@gmail.com" in the email field  "test" in the password field Press Login button  Press Logout button on the Home screen                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                             |                                            |                                            |
| Unit testing      | Register system check                                                     | The user is able to create a new account in the app. After a user has created a new account the app succesfully saved user's personal information to  User data table in the database.                                                                                                                                                                                                                                                                   | Go to register screen(by pressing Register  button on the Login screen)  Input sample data of your choice Press Register button Go to PyCharm; open User data table and refresh the page You will see your personal information entered                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |                             |                                            |                                            |
| Unit testing      | Error messages                                                            | An error message is displayed:      - if an email typed in the Register screen         doesn't contain "@"      - if some of the fields in the Register or Login        screens are not filled up      - if entered password and confirm password doesn't match      - if email or password of the user entered in the         Login screen is not correct      - if the user's account doesn't exist.      - if the user's account already registered.  | Go to register screen(by pressing Register  button on the Login screen)  Enter sample data in the email input field,  anything that doesn't contain "@". Press Register button Look at the Run menu in the Pycharm  Type any password in the password input field and  type a different password in the confirm password field.  Press Register button Look at the Run menu in the Pycharm  Type the following: "test" in the username field "test@gmail.com" in the email field "test" in the password and confirm password field Press Register button Look at the Run menu in the Pycharm  Go back to login screen(by pressing Arrow-Back button) type  Input sample data in the email field Press Login button Look at the Run menu in the Pycharm and  password input field |                             |                                            |                                            |
| Unit testing      | Functionality of buttons                                                  | All the navigation buttons linking Login, Register, Home, All activities, New Activity screens work:  Login button -> does logging in Register button -> transfers to a Register screen Log out button -> logges out from the app All activities button -> transfers to All activities screen New activy button -> transfrs to New activity screen                                                                                                       | Try pressing all the buttons                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |                             |                                            |                                            |
| Unit testing      | Adding New activity check and Recent  activity notification message check | The user is able to add new activity and view it  on the all activities screen. The app stores activities' information in the database.  A Notification message is displayed under the  most recent activity on the Home screen if a  user hasn't added any activities yet.                                                                                                                                                                              | Login into the app using the account created in the  Adding New activity check.  Look under the most recent activity sign  Press New Activity button  Input the following: "running" in the type of activity field "500" in the distance field Press Select a date button and select March 26,2021 (If no errors occurred, the following Unit testing  criteria is met) Press Create button Go to PyCharm; open Activity data table and refresh the page You will see your personal information about your activity                                                                                                                                                                                                                                                              |                             |                                            |                                            |
| Unit testing      | Selecting date check                                                      | The app is able to open a calendar for a user  to select a date when Select a date button  is pressed.                                                                                                                                                                                                                                                                                                                                                   | In the New Activity screen press select a  date button to see a calendar                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |                             |                                            |                                            |
| Unit testing      | Viewing all activities check                                              | The app displays all added activities by a user  on the All Activities screen                                                                                                                                                                                                                                                                                                                                                                            | Go to Home screen Press All Activities button Refresh the page                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                             |                                            |                                            |
| Unit testing      | Labeling check                                                            | All Buttons,Labels and titles are correctly labelled                                                                                                                                                                                                                                                                                                                                                                                                     | Check the labels of all the buttons                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                             |                                            |                                            |
| Integration check | All GUIs function together properly                                       | Switching between different GUIs doesn't cause any errors                                                                                                                                                                                                                                                                                                                                                                                                | Try switching between the screens and see if  any errors occur                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                             |                                            |                                            |
| Code review       | Revision of the accuracy and efficiency of code                           | No syntax, logic, or compilation errors in code                                                                                                                                                                                                                                                                                                                                                                                                          | If every Unit testing has been passed without  any errors the criteria is met                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                             |                                            |                                            |
| Software Check    | Final compilation check                                                   | All the success criteria are being met, the product  matches the criteria.(Success criteria are specified  in Criteria A: Planning).                                                                                                                                                                                                                                                                                                                     | Go to Criteria A: Planning and make sure every  criteria has been met                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |                             |                                            |                                            |

Table.2 Alpha,Beta testing table

Down bellow you can see User accceptance testing table that I've created to check my program with my client

| No. | Success Criteria                   | Procedures                                                                                                                                                                                                                                                                         | Expected Outcome                                                                                                                                                                                                                                                                                                                                                                                                                        | Met? |
|-----|------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|
| 1   | Registration system                | Go to Register screen(by pressing Register button  on the Login screen)  Input you personal information in the input fields  Press Register button   Go to PyCharm; open User data table and refresh the page                                                                      | After pressing Register button on the Login screen the app should redirect the user to a Register screen  Pressing Register button on the Register screen (after the user will type personal information  in the input fields) ==> Message in the terminal will be printed:  "User <user username> with email <user email> and password:  <user psw> has been created"  ==> user's personal information will be stored in the database. | YES  |
| 2   | Log In/Out system                  | Go to Login screen In the input fields, type your personal information  that you have just used to create  an account in the Criteria above(Criteria 1: Registration system). Press Login button on the Login screen Press Logout button on the Home screen                        | Pressing Login button ==> Message in the terminal will be printed:  "login successful for a user with email <user email> and password <user psw>"  Pressing Logout button on the Home screen ==> user will  be transferred back to Login screen                                                                                                                                                                                         | YES  |
| 3   | Adding new activities              | In the Home screen press New Activity button  Input the following:  "running" in the type of activity field  "500" in the distance field  Press Select a date button and select March 27,2021  Press Create button   Go to PyCharm; open Activity data table and refresh the page  | Pressing New activity button on the Home screen ==>  user will be transferred back to New Activity screen  Inputing the activity information and pressing the Create button  ==> activity data will be stored in the database                                                                                                                                                                                                           | YES  |
| 4   | Viewing most recent activity       | Add new activity as explained in the Criteria above  (Criteria 4: Adding new activities)                                                                                                                                                                                           | In the Home Screen, under your Most recent activity sign the user will see his/her newest(recent) recorded activity                                                                                                                                                                                                                                                                                                                     | YES  |
| 5   | Viewing total distance             | Go to Home screen Look under Total distance travelled sign                                                                                                                                                                                                                         | In the Home Screen, under Total distance travelled sign the user will see his/her total distance calculated by adding distances  from all the activities                                                                                                                                                                                                                                                                                | YES  |
| 6   | Viewing all activities             | Go to Home screen  Press All Activities button  Refresh the page                                                                                                                                                                                                                   | The user should be able to see a table of all activities recorded                                                                                                                                                                                                                                                                                                                                                                       | YES  |
| 7   | High usability and pleasing design | Check the whole app one more time                                                                                                                                                                                                                                                  | If the criteria met the app is easy to navigate through and it  has a pleasing design                                                                                                                                                                                                                                                                                                                                                   | YES  |
 
 Table 3. User acceptance testing table

### Alpha testing of my program
https://youtu.be/izhUgLs4vP4
### Beta testing with classmates:
https://youtu.be/Yjk6c1R0nU8
### Beta testing with an external expert:
https://youtu.be/_ump7FVCI0c
### User acceptance testing:
https://youtu.be/5-7AnFYEkrI

### Alpha, Beta Testing results:
![Testing results 1](https://user-images.githubusercontent.com/60378207/112711274-817f9880-8f0a-11eb-83d6-60100f3650ab.jpg)
![Testing results 2](https://user-images.githubusercontent.com/60378207/112711281-90664b00-8f0a-11eb-959c-dc268bdeafae.jpg)
Fig.14 images of Aplha, Beta testing results 


### Bug found during Beta testing
As you may noticed from Beta testing with an external expert video, the expert(Natalia G11) found a bug in my app. The bug is caused by pressing Create button on the New Activity screen before inputing any data in the input fields(type of activity, distance, date). This cause the program to save an empty row in the database and so causing a problem when the programis trying to calculate the total distance. 
![Error during Beta testing](https://user-images.githubusercontent.com/60378207/112708067-1d050f00-8ef3-11eb-9874-f4de7174c21a.png)

Fig.15 image of error occured during Beta testing

To fix that during the Beta testing I had to go to Activity data table in the database, and manually delete the activity(errase the whole row of data), which is definetly not a way to go. 
![Errored activity](https://user-images.githubusercontent.com/60378207/112708145-a6b4dc80-8ef3-11eb-9e9c-404f7eccf59b.png)

Fig.16 image of activty that caused an error during the beta testing

To fix that once and for all, I added the if statement which checks wherther inputs are empty("") or None type.
```.py
# Checks where the inputs fields are filled in
if type_of_activity == None or type_of_activity == "" or distance_travelled_input == None or distance_travelled_input == "" or selected_date == None or selected_date == "":
   print("All the input fields has to be fielded out")
else:
```
The difference between empty input and None type input is:
* if you don't click on the input field at all -> None type
* if you click on the input field but don't type anything -> empty input

In the database it looks like that:

![Errored activity types](https://user-images.githubusercontent.com/60378207/112710842-6bbca400-8f07-11eb-835c-c785793dc431.png)
Fig.17 image of types of data that were stored in the database during the bug

And this is how my program works now:
https://user-images.githubusercontent.com/60378207/112711016-af63dd80-8f08-11eb-9ae1-be9f165321ea.mov
Fig. 18 video of the app after the bug fix

In conclusion, I want to say that I am very happy that during the Beta testing an actual bug was found. This means that the testing wasn't pointless.



