readme.txt

This is a Course Management System (CMS) developed by Vikas Nair. The program allows a global admin to sign on, add and edit courses and students, and view/sort data. Students added to the system can sign on and register/withdraw to courses and view select data. After program end, all data is serialized into storage for retrieval at run-time. The following is a quick breakdown of the program design + structure:

—Application
	The main class, which contains methods for log-in, menu, and serialization.
–Course
	A course entry class, which contains data fields describing a simple course. Includes an array-list of registered students, with methods for searching and editing the registry.
–CourseList
	An object containing an array-list of courses, which contains methods for searching, viewing, editing, and sorting the course list. A method also allows for an initial list of courses to be read into the array-list from a file.
–User
	A class containing data fields which describe a basic user.
–Admin
	A user class which generates a fixed username and password through the default constructor.
–Student
	A user class which contains additional data-fields. Includes an array-list of registered courses, with methods for searching and editing the registry.
–StudentList
	An object containing an array-list of students, which contains methods for searching, viewing, editing, and sorting the student pool.
–AInterface
	An interface describing the basic functions of an admin (empty, because admin-access to methods is determined in menu w/ reference to methods in other classes, CourseList + StudentList)
–SInterface
	An interface describing the basic functions of a student.

Descript:
	This program was designed from the main, starting with a menu for admin and for student. Access to methods (described in the requirements page) are granted via these menus. Most relavent methods are in CourseList + StudentList. The following is a breakdown of the program run-timeline:

–program start
–read from serialized file if it exists; else, populate a new course list from a .CSV file and generate a new student pool
–take the user to log-in page, and automatically judge whether the credentials are those of a student or the admin credentials
–if admin, send to the admin menu; else, send to the student menu
	–from these menus, the user can iterate through data via the allotted methods
–after returning from the menu, log-in again or enter the secret code to exit
–serialize the CourseList and StudentList data into .SER files within the directory
–program end

Exemplification of core concepts:
–Method overloading // DEF: a feature which allows a class / family to declare a plurality of methods with the same name but different signatures
	–I did not use overloading in this program.
–Method overriding // DEF: a feature which allows a class / family to declare a plurality of methods with the same name and signature but different implementation
	–I used one instance of overriding in this program: the Collections sort function. Method "compareTo" in class Course overrides "compareTo" in implemented class Comparable.
–Abstract class // DEF: a class which contains at least one abstract method (a declared method without implementation)
	–I did not use an abstract class in this program.
–Inheritance // DEF: a feature which allows a class to be "extended" from a parent class, thus inheriting data-fields and methods
	–Admin and Student are inherited from User.
–Polymorphism // DEF: a feature which allows an object to be declared as a data type that differs its explicit type; e.g. the data type of a parent class
	–I did not use polymorphism in this program.
–Encapsulation // DEF: a feature which allows the programmer to hide data fields and methods and contain them within a class or package
	–Many of the classes in this program are encapsulated; e.g. the data fields of Course and Student are private and only accessible via getters and setters.
–ADT (Abstract Data Type) // DEF: a model of a data structure which does not describe implementation