# CS360-MobileArchitecture-Programming
Work towards development of a mobile application for the purpose of users who wish to track daily weights and work towards a goal weight.

## Summary of Requirements and User Needs
The Weight Tracking Application is a project pertaining to mobile application development that seeks to satisfy specific requirements and user needs. Requirements included a screen to login or register a user, the implementation of a database that can store and retrieve items, a prompt for the user to opt for SMS notifications if they so choose, and implement a number of screens and UI elements that allow for end users to navigate a fully functional application that suits their needs. 

As is suggested by its nomenclature, the Weight Tracking Application seeks to aid users that are searching for an application that can record their daily weights and set a goal weight. The application solves this by allowing the user to add their goal weight as well as individual weights from weigh-ins on a daily basis.


## Screens, Features, and UI
Multiple activity screens were utilized in order to offer as much functionality as possible that would cater towards user needs. The login screen allows for entering of both a username and password via the phone's keyboard, as well as two separate buttons "Login" and "Register" that serve their own features. "Login" will check the database's existence of the entered username and compare this username's stored password to the user's entered password in order to validate the user and provide access to the remainder of the application.

The MainActivity screen serves as the home screen for the application, and includes a display of the user's goal weight and their entered weight for the current day. If this screen is visited for the first time after registration, the application will first navigate the user to an activity that will prompt them to enter their goal weight so that it can display on the MainActivity screen. If no daily weight is entered for the current date, user is prompted to click an on-screen button that directs them to an activity that prompts the user to enter their weight for the day. This MainActivity screen also includes an app toolbar that includes buttons for accessing the Weights History screen as well as the Settings screen.

The Weights History Screen is used in order to display all of the user's entered weights and their associated dates. As of the time of writing this README, this activity is not currently fully functional, as there were issues with the addWeight() function not adding data to the database, so only one daily weight will currently display when viewing this screen. Future updates to this screen include the ability to delete or update weights that have already been entered into the database by clicking on the weight value that the user wants to change within the current TextView. This TextView will likely be refactored into a RecyclerView that will contain multiple clickable objects that are populated with weight data from the database.

The Settings screen currently only offers the option to opt for SMS notifications that will be sent when the user is approaching or has reached their goal weight. While the method exists to prompt this change in permissions, it currently does not function as intended, and no code for the proposed SMS Message to be sent is currently present within the existing code.


## Coding Process
The application development process began with creating the necessary UI for each screen within the Layout Editor and editing the .xml files when needed. When beginning to code the different activity classes, I felt it best to begin with the MainActivity class, as this is likely to be the most viewed screen where most other activities will stem from. From here, the smaller activities such as adding a goal weight or adding a daily weight were programmed and then connected to the MainActivity screen via button onClickListeners that call to startActivity().

For accessing the Weights History and Settings screens, I felt the UI would become too cluttered were I to simply add more buttons to the existing UI. I instead opted to create an app toolbar that would house icons for these options on the top of the screen. If either the Weights History or Settings screen are accessed via MainActivity, they will maintain this toolbar at the top of the screen with an "up" button that will bring the user back to the MainActivity screen.

Before tackling the Login, Weights History, and Settings screens, I felt it necessary to put the database in place and account for storing daily weights, goal weights, and user credentials. After creating SQL tables for each and implementing any necessary methods that would need to be called by the applications activities, I worked on the Login screen, then Weights History, and then Settings.


## Testing
Testing was mainly carried out through the use of the Android Studio emulator using the API 34 model Pixel. This emulation process was great for simulating how the application may behave on a tangible phone, and it made any elements that did not work as intended very evident. Sending messages to the Logcat command-line was also beneficial when it came to pinpointing certain points within the code to identify where exactly undesired behaviors may be occurring.


## Overcoming Challenges
To overcome persisting challenges, I honestly just had to take breaks or simply switch to working on a different activity within the application before continuing where a problem area was occurring. Namely, I was running into some issues where I would find myself refactoring, researching, refactoring, re-emulating, refactoring, ad infinitum with no luck. I also had quite a bit of trouble wrapping my head around how fragments work properly at certain points within development. In order to preserve the functionality of the application while saving myself extra stress and time, the elements I initially considered implementing as fragments were instead refactored into activities, which actually led the application more towards the direction I had envisioned in my mind.


## Areas of Success in Demonstrating Skills
In particular, I felt the database class was the best instance that outlined my skills in terms of programming, as it stores a variety of data types with differing variables and a multitude of methods that are used across the entire application. When considering the connection between the UI and the back end code, I felt the MainActivity and its connections to other screens provided a good demonstration of understanding how to connect code to UI elements and have these elements function as intended, making switching between screens easy to accomplish without confusion.
