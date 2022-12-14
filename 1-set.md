# Set

## Introduction

Set is another kind of data structure, but different of the most types of data structures sets don't care about the
the order of the data. The most import thing of a set is making sure that there's no duplicated data.

![Set example diagram](Assets/SetPics/setExample.png)

## Big O Efficiency

A set efficiency is increased because sets don't care about the order in which the data was stored. As said before
sets only bother in not adding duplicated data. Sets use a technique called hashing to add, remove, and check
membership in O(1). In a simple way hashing will keep track of each elements position after adding them to the set.

## Set Methods

Sets most common methods are adding values, removing values, check membership, and checking the set size.

### Adding
.Add is the method to add an element to a set. It won't care about the order.
```csharp
HashSet<int> numbers = new HashSet<int>();

numbers.Add(1);
numbers.Add(2);
numbers.Add(3);
numbers.Add(4);
numbers.Add(5);

foreach(int i in numbers){
    Console.WriteLine(i);
}
```
Output
```
1
2
3
4
5
```

### Removing
.Remove is the method to remove an element from a set.
```csharp
numbers.Remove(2);
numbers.Remove(4);

foreach(int i in numbers){
    Console.WriteLine(i);
}
```
Output
```
1
3
5
```

### Membership
.Contains is the method to check and element membership inside a set.
```csharp
Console.WriteLine(numbers.Contains(5);
Console.WriteLine("-----");
Console.WriteLine(numbers.Contains(4);
```
Output
```
true
-----
false
```

### Size
.Count is the method to check how many elements exist inside the set.
```csharp
Console.WriteLine(numbers.Count);
```
Output
```
3
```
## Set Operations

The sets in programming languages are like sets in math. A long with the methods they also have what we call operations.
The most common operations are union, intersection, and difference. In C# they are known respectively as union, intersect,
and except. Sets operations involve more then one set to be accomplished.

### Union
Union will combine the content of both sets involved in the operations.

![Union example diagram](Assets/SetPics/unionDiagram.png)
```csharp
HashSet<int> set1 = new HashSet<int>() {3,1,4,2,5};
HashSet<int> set2 = new HashSet<int>() {8,4,6,10,2;

var unionSet = set1.Union(set2);

foreach(int i in unionSet){
    Console.WriteLine(i);
}
```
Output
```
3
1
4
2
5
8
6
10
```
### Intersect
Intersect will return the elements that exist in both sets involved in the operations.

![Intersect example diagram](Assets/SetPics/intersectDiagram.png)
```csharp
var interSet = set1.Intersect(set2);

foreach(int i in interSet){
    Console.WriteLine(i);
}
```
Output
```
2
4
```

### Except
Compare the values of both sets involved in the operation and return the one from one set who are not in the second set.

![Except example diagram](Assets/SetPics/exceptDiagram.png)
```csharp
var excepSet = set1.Except(set2);

foreach(int i in excepSet){
    Console.WriteLine(i);
}
```
Output
```
1
3
5
```

## Set real life application

- playlist
- class attendance
- Work list
- Domains



## Music Playlist Example

A common example of a set that we see almost everyday is music playlists. When creating a playlist of songs in your music app
the app won't let you add the same song twice. When you try to add a song that is already there it will give you an error message
saying that the song is already in the playlist.

![Playlist Set diagram](Assets/SetPics/playlistSetDiagram.png)

In the diagram above we can see how the playlist works like a set. Song can me added to the set and also removed from the set.
We can also check how many songs that set contains. To check if a song is already in the set we can use the Contains method.
Nevertheless song apps usually don't have this feature, but what we usually do to test if a song is the playlist is trying to add
to the playlist. If you try to add a song and the app tells you that the song is already there is because in the background the app
ran a ".Contains" method in the playlist to check if the song was there to not run to the error of trying to add a duplicated song.

The code bellow would be the representation of the playlist working in C#.

```csharp
HashSet<string> playList = new HashSet<string>() {"Yellow", "Paradise", "Fix you"};
foreach (var song in playList)
{
    Console.WriteLine(song);
}
Console.WriteLine("");
playList.Add("Paradise"); //Add paradise won't work because is already there.
playList.Remove("Yellow");
Console.WriteLine("-----------");
foreach (var song in playList)
{
    Console.WriteLine(song);
}
Console.WriteLine("----------");
Console.WriteLine(playList.Contains("Paradise"));
Console.WriteLine(playList.Contains("Viva la vida"));
```
Output
```
Yellow
Paradise
Fix you
----------
Paradise
Fix you
----------
True
False
```

## Problem to Solve: School Report.

Write a program that will generate a school report when comparing to different classes. The school needs to know how many students
are taking both Math and English class and how many are taking only Math and only English classes. The program will have an option to
add students in each class and one option to print the reports. You will start the program with both classes each having five students.
The English class will already have the following students: antony, breanna, gilbert, brandon, and cassidy.
The Math class will already have the following students: antony, carla, benjamin, sara, and breanna.

Below is an example of the output:

```
0. Exit
1. Add a student in the English class
2. Add a student in the Math class
3. Print report
Your choice: 1
Student name: John

0. Exit
1. Add a student in the English class
2. Add a student in the Math class
3. Print report
Your choice: 2
Student name: John

0. Exit
1. Add a student in the English class
2. Add a student in the Math class
3. Print report
Your choice: 1
Student name: John
John is already registered for this class

0. Exit
1. Add a student in the English class
2. Add a student in the Math class
3. Print report
Your choice: 1
Student name: Mark

0. Exit
1. Add a student in the English class
2. Add a student in the Math class
3. Print report
Your choice: 2
Student name: Julia

0. Exit
1. Add a student in the English class
2. Add a student in the Math class
3. Print report
Your choice: 3

There are 11 students in total
There are 4 students taking only the English class: Gilber, Brandon, Cassidy, mark
There are 4 students taking only the Math class: carla, benjamin, sara, julia
There are 3 students taking both English and Math class: antony breanna, john

0. Exit
1. Add a student in the English class
2. Add a student in the Math class
3. Print report
Your choice: 0
```

You can check the solution here: [Solution](Set-solution)





