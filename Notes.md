# Hacking With SwiftUI Notes

# Day 0

Working on Day 0.

Core Skills

- Swift
- SwiftUI
- Working with Data
- Networking
- Version Control

The only way to write great code is to write a whole bunch of bad code first.

SwiftUI uses Swift to build UI. Framework built on top of Swift.

Benefits of SwiftUI

- It is significantly easier than UIKit, with fewer things to learn along the way.
- Built for Swift. Takes care of some things behind the scenes. Unlike UIkit, that was built for ObjC
- Works on all platforms.
- SwiftUI is where things are going. It will be the dominant UI framework.

Networking is getting and sending data.

Working with data, getting data from a server, loading it, and showing it on the screen.

Version Control, using something like Git. It's about publishing your code somewhere.

## Swift

Extension Skills

- UIKit
- Core Data
- Testing
- Architecture
- Multithreading

Why UIKit?

- It's popular
- It's more powerful than SwiftUI
- It's precise
- It's proven, because it's been around longer.

Why Not UIKit?

- It's more complicated than SwiftUI.
- It's got features that hidden in SwiftUI
- Protocols and Delegates
- Nothing about AutoLayout is Auto.

Core Data

- Allows to store data
- Syncs to iCloud

Why not Core Data?

- It's freaking complicated
- Does not feel comfortable in Swift
- Surprisingly complex

Testing is an extension not a core skill. iOS community is bad at Testing. Big apps have like no tests. Writing tests don't seem as much fun. Testing is a smaller topic, theoretically.

Software Architecture comes with experience:

- Design Patterns

Multithreading -> headache for our brain to work. Goal is understand enough without going a great deal forward.

Quote from David Smith.

---

Common Mistakes:

1. Memorizing everything
2. Shiny object syndrome
3. lone wolf learning
4. Using beta software
5. Relying on Apple's Documentation
6. Learning Objective C
7. Taking Shots at others languages

Memorizing Everything, do not do it. It will suck all your willpower out of you. No one memorizes everything. Learn how to look it back up. The more you look up the more you will remember. You learn through repetition. The more you relearn you make it clear to your brain that this topic matters. This is worth stashing away. Don't worry about forgetting things. Know where to look. **ps, this is why i'm taking notes**.

Shiny Object syndrome. Learning lots of material isn't exciting. Some things give you great results; others take a long time to understand.

Lone Wolfing is about learning by yourself. Extremely easy to lose motivation this way. Share what you are learning.

Using Beta Versions. I don't need to be cautioned on this. So much is just wrong.

---

Free Resources

- [Apple Teaching Code site](https://www.apple.com/education/k12/learn-to-code/)
- Ray Wenderlich

My Playgrounds App

Cummunity Folks

- @seanallen_dev
- Antoine v.d. SwiftLee
- NovallSwift
- Steve Troughton-Smith
- Kaya Thomas @kthomas901
- Majid Jabrayilov @mecid
- Donny Wals @donnywals
- Sommer Panage @Sommer
- Natashca Fadeeva
- Paul Hudson

iosdevweekly.com

hackingwithsift.com/forums

iosdevhappyhour.com

developer.apple.com/wwdc

github.com/twostraws/wwdc

Sean Allen's interview Tips.

### Debrief from the day

Much of this material was review for me. I already know a lot about swift and a little about SwiftUI. I've worked with Apple's Developer Documentation for years and know it's pitfalls.

In general, I like Paul, love his dogs, and his teaching style.

Bigger issue I think I'm going to have is sticking with it when I get bored. Too much review.

# Day 1

Why Swift?

- It's new and doesnt have cruft of old languages.
- It is the best way to write iOS apps.

How to follow along

- Try to execute the code so you can really understand what is going on.
- Need XCode 13 or later
- Learning swift through Playgrounds (MacOS blank)
- Do follow along

Variables and Constants

- Variables change over time.
- `var` means create a new variable
- I'm not going over the details of the following:

```swift
import Cocoa
var greeting = "Hello, playground"
```

- semicolons are only required to put two lines of code on the same line.
- Constants are defined with `let`
- Swift will error if you try to change a constant
- `let` comes from math proofs
- Variables names can be named pretty much whatever you want.
- Standard amongst Swift Developers, camel case is the standard, eg `playerName`
- Prefer to use constants over variables if you can.

How To Create Strings

- Strings start and end with double quotes.
- Can contain punctuation and emojis.
- To use double quotes in strings, use a backslash like `"Swift string \"with quotes\""`

```swift
let movie = """
A day in
the life of an
Apple Engineer
"""
```

- Multi line strings must start with """ on their own lines.
- Strings are class and you can run things like `count` which returns the number of characters in the string.
- You can also call functions on string objects like `.toUpperCase()` on a string. Other examples `hasPrefix("foo")` or `hasSuffix("bar")`

How to store whole numbers?

- created with let or var.
- Can create really big numbers with underscores for readability:

```swift
let reallyBig = 100_000_000
```

- Can also create them with operators
- Compound assignment equal operators like `+=`
- have functions like `isMultipleOf()`

```swift
let reallyBig = 100_000_000
let score = 10
let lowerScore = 10-2
let halfScore = score / 2

var counter = 10
counter = counter + 5
counter += 5
print(counter)

print(120.isMultiple(of: 3))
```

How to store decimal numbers

- called floating point number. Comes from the way computers store these numbers. Decimal point is moved around for the number.
- Can be confusing:

```swift
let number = 0.1 + 0.2
print(number) // => "0.30000000000000004\n"
```

- Ints are 100% accurate
- Decimals always a decimal point in their definition. Without a decimal it is an Int.
- Once a variable is assigned a type it must remain that type.
- Swift lets us use `Double` and `CGFloat` interchangeably.

### Debrief

Today was mostly a review for me. A couple of small details were details that I had forgotten. I haven't seen a bunch of multiline strings so the """ thing was interesting. I forgot about the use of underscores for readability on large numbers.

On the website, it was unclear where one day ended and the next began, so I started Day 2 without meaning to. I will pay closer attention on the next day.

# Day 2

How to store truth with Booleans

- Storing truth in variables
- We've seen it in things like `isMultipelOf()`
- Assigned to either true or false.
- Has a few methods of not, which is a ! at the beginning.
- Also has method `.toggle()`

How to join strings together

- join with `+`, can do with multiple strings.
- The plus operator is overloaded for strings
- Swift does linear adding so things like "1" + "2" + "3" => "12" + "3" => "123" which is inefficient.
- Going over string interpolation ` "five * five is \(5*5)"`

Summary: Sample data.

- use let as much as possible.
- Swift strings can be short or long
- Swift strings have methods like count
- Reviewing types, Int, Double, Bool
- String interpolation

Checkpoint 1: creating a swift temperature converter

full disclosure, I can't spell:

```swift
var celciusTemp = 10.0
var fTemp = celciusTemp * 9.0 / 5.0 + 32.0
print("Celcius: \(celciusTemp) is \(fTemp) in Farenhieght")
```

# Day 3

Complex Data Types

How to store data in arrays

- collections of data zero indexed.
- only allows like data in the array
- Swift knows the type of the array.
- Enforces **Type safety**.

```swift
var scores = Array<Int>()

scores.append(100)
scores.append(80)
scores.append(85)

print(scores[1])
```

- use angle brackets to specify type.
- `()` invokes constructor, can be used to specify size.

```swift
var albums = Array<String>()
albums.append("Folklore")
albums.append("Fearless")
albums.append("Red")

// Shorthand for defining an array.
var albums2 = [String]()

var albumsShort = ["Folklore"]
albumsShort.append("Fearless")
albumsShort.append("Red")
```

- Methods: remove(at:) and removeAll(). Goes over contains(). Sorted

```swift
let cities = ["London", "Tokyo", "Rome", "Budapest"]
print(cities.sorted())

let presidents = ["Bush", "Obama", "Trump", "Biden"]
let reversedPresidents = presidents.reversed()
print(reversedPresidents) // Returns a reversed array
```

How to Store and find data in dictionaries

- Dictionaries allow you to associate keys with values.
- Arrays use indexes, Dictionaries use keys

```swift
let employee2 = [
    "name": "taylor swift",
    "job": "singer",
    "location": "Nashville"
]

print(employee2["name"])
print(employee2["password"])
```

- covering optionals as return types, because password doesn't exist.
- Can provide default values `employee["name", defualt "foo"]`
- Can override keys by redefining them

How to use Sets for fast data lookup

- Sets are like arrays but don't care about order and don't allow duplicates
- Don't contain duplicate elements.
- you insert, don't append. Arrays don't have order.
- No duplicates allowed might be what you need.
- Sets store their data in highly optimized structure so they are faster to search through.
- the sorted() function returns an array because sets don't have order.

How to create and use enums

- set of named values
- can be used to create type safety.

```swift
enum Weekday {
    case Monday
    case Tuesday
    case Wednesday
    case Thursday
    case Friday
}

var day = Weekday.Monday
day = Weekday.Friday
day = .Thursday

print(day)
```

# Day 4

How to use Type Annotations

- used when you want override a default, or belay assigning a value.
- We have been using type inference `let surname = "lasso"` (will infer type String)
- Can be specific with `let surname : String = "Lasso"`

Summary: Complex Data

- Arrays store many values in one place (index starting at 0)
  - one type only
  - helpful functionality
- Dictionaries store many values by key
  - only one type for key and one type for value
- Sets store values in one place
  - don't choose order
- Enums create our types
- Swift uses type inference to figure out what we are storing
- It is also possible to use type annotation to force a particular type.

Checkpoint 2:

My solutions is slightly different than Pauls. I used a set with my array and .count in string interpolation to do everything in one step.
