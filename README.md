# Optionals lab

## Question 1

`var userName: String?`

Write 3 different ways of safely unwrapping and printing the value of `userName`.  If it is nil, print "No name".

- Method one: Check for nil and force unwrap

- Method two: Optional binding

- Method three: Nil coalescing

```

userName = "Anthony"

//method 1 - Force unwrap

print(userName!)

//method 2 - Optional binding
if let userName = userName {
print(userName)
} else {
print("No name")
}

//method 3 - Nil coalescing
var unwrappedUserName = userName ?? "No name"

print(unwrappedUserName)
```


## Question 2

Given optional string `backgroundColor`, write code that safely unwraps and prints it. If backgroundColor is nil, give it a value.

`var backgroundColor: String?`

```
var backgroundColor: String?

var unwrappedBackgroundColor = backgroundColor ?? "blue"

```


## Question 3

Given an optional width and an optional height of a rectangle, write code that calculates and prints the area. Print an error message if either value is nil.

```swift
var width: Double?
var height: Double?
```
```
if let width = width {
if let height = height {
print(width * height)
} else {
print("error")
}
} else {
print("error")
}
```

## Question 4

Given the following optional variables `name`, `age` and `height`. Write code so that it prints `name`, `age` and `height` if they all have a value. If any are nil, print an error message. Try using optional binding.

```swift
var name: String?
var age: Int?
var height: Double?
```
```
if let name = name {
print(name)
} else {
print("error: nil name")
}

if let age = age {
print(age)
} else {
print("error: nil age")
}

if let height = height {
print(height)
} else {
print("error: nil height")
}
```

## Question 5

Given the variables `firstName`, `middleName` and `lastName`. Create a variable called `fullName` that is a nicely formatted string.

```swift
var firstName: String = "Johnny"
var middleName: String?
var lastName: String = "Stone"
```
```
var fullName = ""


if let middleName = middleName {
fullName.append(firstName + " " + middleName + " " + lastName)
} else {
fullName.append(firstName + " " + lastName)
}

print(fullName)

```

## Question 6

Write code that adds 15 to `myIntString`, then prints the sum. Use the `Int()` constructor which returns an optional Int `(Int?)`.

`let myIntString = "35"`

```
if let integerVersion = Int(myIntString) {
print(integerVersion + 15)
}
```

## Question 7

Given an optional tuple of optional Ints, write code to safely unwrap the tuple and calculate the sum of its contents that aren't nil.

```swift
var scores: (Int?, Int?, Int?)?

var testCaseOne: (Int?, Int?, Int?)? = (4, nil, 7)
var testCaseTwo: (Int?, Int?, Int?)? = (nil, nil, 9)
var testCaseThree: (Int?, Int?, Int?)? = (5, 10, 24)
```
```
var sum = 0

if let scores = scores {
sum = (scores.0 ?? 0) + (scores.1 ?? 0) + (scores.2 ?? 0)
}
print(sum)
```

## Question 8

Safely unwrap `tuple` if there’s a non-nil tuple value and print it out.

```swift
var tuple: (Int, Int)?
if Bool.random() {
 tuple = (5, 3)
}
```
```
if let tuple = tuple {
print(tuple)
} else {
print("error: nil")
}
```


## Question 9

Write code that either doubles `myInt` and then prints it, or prints an error message if myInt is nil.

```swift
var myInt: Int?
if Bool.random() {
 myInt = 5
}
```
```
if var myInt = myInt {
print(myInt * 2)
} else {
print("error: nil")
}
```

## Question 10

Write code that prints out the product of `myDouble` and `doubleTwo` or prints an error message if `myDouble` is nil.

```swift
var myDouble: Double?
let doubleTwo: Double = 5

if Bool.random() {
 myDouble = 12
}
```
```
if var myDouble = myDouble {
print(myDouble + doubleTwo)
} else {
print("error: nil input for myDouble")
}
```


## Question 11

Determine if the variable contains a Boolean or nil value. If nil set the variable to false, else keep it true.

```swift
var isTheGreatest: Bool?

if Bool.random() {
 isTheGreatest = true
}
```
```
if var isTheGreatest = isTheGreatest {
} else {
isTheGreatest = false
}
print(isTheGreatest!)
```

## Question 12

Given the code below print the sum of each non-nil element in `myTuple`.

 ```swift
var myTuple: (Int?, Int?, Int?, Int?)

if Bool.random() {
 myTuple.0 = 5
 myTuple.2 = 14
} else {
 myTuple.1 = 9
 myTuple.3 = 10
}
```
```
var sum = 0

if let firstElement = myTuple.0 {
sum += firstElement
}
if let secondElement = myTuple.1 {
sum += secondElement
}
if let thirdElement = myTuple.2 {
sum += thirdElement
}
if let thirdElement = myTuple.3 {
sum += thirdElement
}

print(sum)
```

## Question 13

Given the helper functions and code below, check to see if your `evolutionaryStone` is able to evolve your pokemon.  The table below shows the appropriate matches of pokemon to stone:

| Pokemon	   | Stone    |
| :--------: | :------: |
| Pikachu	   | Electric |
| Bulbasaur	 | Grass    |
| Charmander | Fire     |
| Squirtle	 | Water    |


```swift
// Helper Functions

func eStone() -> String {
 let random = Int(arc4random_uniform(5))
 switch random {
 case 0:
  return "Electric"
 case 1:
  return "Grass"
 case 2:
  return "Fire"
 case 3:
  return "Water"
 default:
  return "No Stone"
 }
}

func starterPokemon() -> String {
 let random = Int(arc4random_uniform(5))
 switch random {
 case 0:
  return "Pikachu"
 case 1:
  return "Bulbasaur"
 case 2:
  return "Charmander"
 case 3:
  return "Squirtle"
 default:
  return "Not a Pokemon"
 }
}

let pokemon: String?
var evolutionaryStone: String?
pokemon = starterPokemon()
evolutionaryStone = eStone()
```
```
if let pokemon = pokemon ,
let evolutionaryStone = evolutionaryStone {
if pokemon == "Pikachu" && evolutionaryStone == "Electric" {
print("\(pokemon) + \(evolutionaryStone) = Will Evolve!")
} else if pokemon == "Bulbasaur" && evolutionaryStone == "Grass" {
print("\(pokemon) + \(evolutionaryStone) = Will Evolve!")
} else if pokemon == "Charmander" && evolutionaryStone == "Fire" {
print("\(pokemon) + \(evolutionaryStone) = Will Evolve!")
} else if pokemon == "Squirtle" && evolutionaryStone == "Water" {
print("\(pokemon) + \(evolutionaryStone) = Will Evolve!")
} else {
print("not able to evolve")
}
}
```

## Question 14

Given an optional int `numberOfPeople`, write code that unwraps and prints it **only if it is even**. Try using optional binding with a condition.

```swift
var numberOfPeople: Int?

if Bool.random() {
 numberOfPeople = 108
}
```
```
if let numberofPeopleUnwrapped = numberOfPeople {
if numberofPeopleUnwrapped % 2 == 0 {
print(numberofPeopleUnwrapped)
} else {
print("error: uneven number")
}
} else {
print("error nil")
}
```


## Question 15

Given the array of optional Ints `someNumbers`, write code to find the product of the array not including any nil values.

```swift
var someNumbers: [Int?] = []

for i in 0..<20 {
    someNumbers.append(Bool.random() ? i : nil)
}
```
```
var fixedNums: [Int] = []

if case var someNumbersUnwrapped = someNumbers {
for n in someNumbersUnwrapped {
if n != nil {
fixedNums.append(n!)
}
}
}
print ("\(fixedNums) Product = \(fixedNums.reduce(1, *))")
```


## Question 16

Given the array `poorlyFormattedCityNames`, create a new array with the city names capitalized and any nil values removed.

```swift
let poorlyFormattedCityNames: [String?] = ["new york", "BOSTON", nil, "chicago", nil, "los angeles", nil, "Dallas",]

Output: ["New York", "Boston", "Chicago", "Los Angeles", "Dallas"]
```
```
var formattedNames = [String]()

if case let unwrappedNames = poorlyFormattedCityNames {
for name in unwrappedNames {
if name != nil {
formattedNames.append(name!.capitalized)
}
}}

print(formattedNames)
```

## Question 17

Given a random array of optional numbers, create a new array of all the even numbers that aren't nil.

```swift
var aBunchOfNumbers: [Int?] = []

for _ in 0..<20 {
 aBunchOfNumbers.append(Bool.random() ? Int(arc4random_uniform(102)) : nil)
}
```
```
var evenNumbers = [Int]()

if case var aBunchofNumbersUnwrapped = aBunchOfNumbers {
for n in aBunchofNumbersUnwrapped {
if (n != nil) && (n! % 2 == 0) {
evenNumbers.append(n!)
}
}
}
print(evenNumbers)
```

## Question 18

Given the following array of zip codes as strings, write code that turns them into an array of Ints.

`let zipCodeStrings = ["11377", "11101", "11373", "10014", "10003", "11223"]`

```
let zipCodeInts = zipCodeStrings.map { Int ($0)!}
print(zipCodeInts)
```


## Question 19

Some students were asked some questions about their favorite foods and colors and the answers were stored in an array `studentInfo`.
`let studentInfo: [(String, String?, String?)] = [("Bill", "Burgers", "Blue"), ("Rita", nil, "Red"), ("Peter", "Pizza", "Purple"), ("Sarah", "Sandwiches", nil), ("Jeff", nil, nil), ("Lucy", "Leftovers", "Lilac"), ("Mike", "Meat", "Mauve"), ("Gemma", nil, "Green")]`


- Print the names of the students that do not have a favorite color.

```
for array in studentInfo {
if array.2 == nil {
print("\(array.0) does not have a favorite color" )
}}
```
- Print the names of the students that don't have a favorite color or a favorite food.
```
for array in studentInfo {
if array.2 == nil && array.1 == nil {
print("\(array.0) does not have a favorite color or food" )
}}
```
- Create a new array of type `[(String, String, String)]` that contains the students with both favorite colors and foods.
```
var newArray = [(String, String, String)]()

for array in studentInfo {
if array.2 != nil && array.1 != nil {
newArray.append(array as! (String, String, String))
}
}
print (newArray)

```

## Question 20

Given an optional array of optional tuples of optional UInt8s,

- Write code to safely unwrap and print the tuples in the array with all 3 RGB values.

- Write code that counts all the nil values.

`let possibleColors: [(r: UInt8?, g: UInt8?, b: UInt8?)?]? = [(128, 21, 7), (0, 0, 0), nil, (nil, 25, 82), (255, 255, 255), nil, (200, 100, nil), (120, nil, 23), (0, 255, 106), (nil, nil, nil), nil, (100, 100, 200)]`

```
var nilCounter = 0

var final = [(r: UInt8?, g: UInt8?, b: UInt8?)]()


if let possibleColorsUnwrapped = possibleColors {
for stuff in possibleColorsUnwrapped {
if stuff != nil {
final.append(stuff!)
} else {
nilCounter += 1
}
}
}
for rgbValues in final {
if rgbValues.0 != nil && rgbValues.1 != nil && rgbValues.2 != nil {
print("(r: \(rgbValues.0!), g: \(rgbValues.1!), b: \(rgbValues.2!))")
} else {
nilCounter += 1
}
}
print(nilCounter)
```
I know the nilCounter isn't quite working properly. I ran out of time. 
## Question 21

Consider the following nested optional. It corresponds to a number inside a box inside a box inside a box.

- Fully force unwrap and print number.

- Optionally bind and print number.

`let number: Int??? = 10`


## Question 22

Given an Array of Optional Strings, write code that concatenates all non-nil values together except for strings with 3 or more vowels.

`let monkeyingAround = ["orangutan", "apes",nil, "monkeys", "gorillas", "lemurs", nil]`

output: `"apesmonkeyslemurs"`


## Question 23

Given the value below, print out all of the non-nil Ints it contains by accessing each of them.

`var strangeStructure: ([Int]?, [[Int?]], [[Int]?], Int)? = ([1], [[2,3,4],[],[5,nil],[nil]], [nil, [6,7,8],nil,[],[9]], 10)`
