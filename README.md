# Initialization Lab


## 1: Structs Review

Download the resources at the link below:

https://developer.apple.com/go/?id=app-dev-swift-student (Links to an external site.)


Open the folder titled "2 - Introduction to UIKit" then open the folder titled "3 - Structures".  Open the Playground there, and work through the exercises.

```swift
//pg.1

struct GPS {
var latitude = 0.0
var longitude = 0.0
}

var somePlace = GPS()
print(somePlace.latitude)
print(somePlace.longitude)

somePlace.latitude = 51.514004
somePlace.longitude = 0.125226
print(somePlace.latitude)
print(somePlace.longitude)


struct Book {
var title: String
var author: String
var pages = 0
var price = 0.0
}

var favoriteBook = Book(title: "Extremely Loud and Incredibly Close", author: "Jonathan Safran Foer", pages: 368, price: 11.45)
print(favoriteBook)


//pg. 2 

struct RunningWorkout {
var distance = 0.0
var time = 0.0
var elevation = 0.0
}

var firstRun = RunningWorkout()
print(firstRun)


firstRun.distance = 2396.0
firstRun.elevation = 94.0
firstRun.time = 15.3
print(firstRun)


//pg. 3

struct GPS {
var latitude: Double
var longitude: Double
}

let somePlace = GPS(latitude: 51.514004, longitude: 0.125226)
print(somePlace)


struct Book {
var title: String
var author: String
var pages: Int
var price: Double
}

var favoriteBook = Book(title: "Extremely Loud and Incredible Close", author: "Jonathan Safran Foer", pages: 368, price: 11.45)
print("The title of my favorite book is called '\(favoriteBook.title)'.")


struct Height {
var heightInInches:Double
var heightInCentimeters:Double

init(heightInInches: Double) {
self.heightInInches = heightInInches
self.heightInCentimeters = heightInInches * 2.54
}

init(heightInCentimeters: Double) {
self.heightInCentimeters = heightInCentimeters
self.heightInInches = heightInCentimeters / 2.54
}

}

var someonesHeight = Height.init(heightInInches: 65)
print(someonesHeight.heightInCentimeters)


var myHeight = Height.init(heightInCentimeters: 162.56)
print(myHeight.heightInInches)


//pg. 4

struct User {
var name: String
var age: Int
var height: Double
var weight: Double
var activityLevel: Int
}


var sunni = User(name: "Sunni", age: 27, height: 64.0, weight: 120.0, activityLevel: 8)


struct Distance {
var meters: Double
var feet: Double

init(meters: Double) {
self.meters = meters
self.feet = meters * 3.28084
}

init(feet: Double) {
self.feet = feet
self.meters = feet / 3.28084
}
}

let mile = Distance(meters: 1600)
print(mile.feet)

let kilometer = Distance(meters: 1000)
print(kilometer.feet)


//pg. 5

struct Book {
var title: String
var author: String
var pages: Int
var price: Double

func description() {
print("The book title is \(title). It is written by \(author) and has \(pages) pages. It costs \(price).")
}
}

var someBook = Book(title: "Extremely Loud Incredibly Close", author: "Jonathan Safran Foer", pages: 368, price: 11.45)
someBook.description()


struct Post {
var message: String
var likes: Int
var numberOfComments: Int

mutating func addLike() {
likes += 1
}
}

var somePost = Post(message: "Hi!", likes: 1, numberOfComments: 3)
print(somePost.likes)
somePost.addLike()
print(somePost.likes)


//pg. 6

struct RunningWorkout {
var distance: Double
var time: Double
var elevation: Double

func postWorkoutStatus() {
print("You ran for \(distance) miles in \(time) minutes. There was an elevation gain of \(elevation) ft.")
}
}

var myWorkout = RunningWorkout(distance: 2.4, time: 32.2, elevation: 5.4)
myWorkout.postWorkoutStatus()


struct Steps { 
var steps: Int
var goal: Int

mutating func takeStep() {
steps += 1
}
}

var stepsToday = Steps(steps: 3242453, goal: 23423455354)
print(stepsToday.steps)
stepsToday.takeStep()
print(stepsToday.steps)


//pg. 7

struct Rectangle {
var width: Int
var height: Int

func area() {
print(width*height)
}
}

var myRectangle = Rectangle(width: 2, height: 2)
myRectangle.area()


//pg. 8

struct RunningWorkout {
var distance: Double
var time: Double
var elevation: Double
var averageMileTime: Double


init(distance: Double, time:Double, elevation: Double) {
self.distance = distance
self.time = time
self.elevation = elevation
self.averageMileTime = distance/time
}
}

var myWorkout = RunningWorkout(distance: 3.2, time: 10.2, elevation: 4.3)
myWorkout.averageMileTime



```


## 2: Classes and Inheritance

Open the folder titled "2 - Introduction to UIKit" then open the folder titled "4 - Classes and Inheritance".  Open the Playground there, and work through the exercises.




## BONUS: Actor mini-project

Complete each of the following exercises by creating a new Command Line App in Xcode.  Classes and structs allow us to separate out our code into multiple different files.  In you main.swift file, copy and paste the code at the link below.

 https://gist.github.com/benstone1/75ae3cf24c8cb2ade792b9c66e79ee5c



## 3

Create a new file and name it "Movie.swift".  Make sure to save it right below your main.swift file.


Inside of the Movie.swift file, create a class called Movie that has properties for name (String), year (Int), genre (String), cast ([String]), and description (String).


Inside of main.swift, populate an array of Movies converted from the array of dictionaries in the gist above.

## 4

Then, for each movie in the Movie array, print the name of each movie and associated cast on a single line. Be sure not to print the array of cast members, only the string elements.



Correct Output Examples:

Minions: Sandra Bullock, Jon Hamm, Michael Keaton
Shrek: Mike Myers, Eddie Murphy, Cameron Diaz


Incorrect Output Examples (printing an array instead of the actors joined together as a String):

Minions: ["Sandra Bullock", "Jon Hamm", "Michael Keaton"]
Shrek: ["Mike Myers", "Eddie Murphy", "Cameron Diaz"]


## 5

Let's refactor our Movie class with what we learned today.



Create a failable convenience initializer convenience init?(with dict: [String:Any]) for the Movie class that takes in a dictionary, and uses the values of the input dictionary to initialize a Movie object.



Go back to the for loop in main.swift where we iterate through the movies array. Rewrite the body of the loop such that it creates a Movie object for each dictionary in the movies array using the new convenience initializer.


## 6

Repeating the same process you used to make the Movie.swift file, create files named:

- Person.swift
- Actor.swift


In Person.swift, create a class named Person with

- A name of type String
- A birthYear of type Int
- A deathYear of type Optional Int

In Actor.swift, create a class named Actor that

- Inherits from Person
- Has a breakoutYear of type Int
- Has a breakoutRole of type String

Rewrite your Movie class to have its case property be an array of Actors instead of Strings.

## 7

Repeating the same process you used to make the Movie.swift file, create a file named:

Genre.swift

In Genre.swift, create an enumeration with raw String values with the following cases:

- animation
- action
- drama


Rewrite your Movie class to have its genre property be of type Genre instead of String.


## 8

Refactor your code and create an area of your improved Movie class out of the array of dictionaries.

Then, use your new array to complete each of the following questions:

a. Print the name of the first movie.

b. Print a list of all movie names on one line.

c. Print a list of all movie years and names (each on a new line) as follows:

2015: Minions
2001: Shrek

d. Print the title of each movie and add an appropriate emoji to represent its genre.

e. Print out the title of each movie and all of the actors that were older than 40 when then movie was made.
