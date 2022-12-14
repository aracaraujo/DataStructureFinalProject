# Queue

## Introduction
A Queue is a list that follows the patter of First In First Out (FIFO). To easily understand you can think of
a line in a car wash. When a person gets in the car wash they go to the end of the line. The car in the front
of the line is the first car to go inside the washer and is removed from the queue. The line keeps moving in
this direction. The first car will go to through the car wash and then if any more cars shows up they are added
at the back of the line.

![Car line to car wash queue diagram](Assets/QueuePics/queueDiagram.png)

## Queue Methods

The process of adding and removing elements in a queue are called Enqueue and Dequeue.

### Enqueue
In our car wash line example the process of adding a car to the back of the line represents how elements are added
to a queue. Elements in a queue are always added to the back of the line.
```csharp
Queue carLine = new Queue();
carLine.Enqueue("firstCar");
carLine.Enqueue("secondCar");
carLine.Enqueue("thirdCar");

foreach(var ele in carLine)
{
    Console.WriteLine(ele);
}
```
In the example above we added, enqueue, three cars to our car line queue and print them.

Output
```
firstCar
secondCar
thirdCar
```



### Dequeue
In our car wash line example the process of having a car go through the wash and being removed from the queue
represents how elements are removed from a queue.
```csharp
carLine.Dequeue();
carLine.Dequeue();
carLine.Dequeue();

Console.WriteLine(carLine.Count);
```

In the example above we removed, dequeue, the three cars that we added previously. Because queues work in the
method of First In First Out we don't need to specify where we are adding or removing elements. Elements will
always be added to the back and removed from the front. We printed how many elements exist in the queue in the
end.

Output
```
0
```

### Other Methods

In some situations you need to do more things than just adding or removing elements from a queue. A few of queue
methods are:
- Count : returns how many elements exist on the queue.
- Peek : returns the first element of the queue, but doesn't remove them from the queue.
  like Dequeue does.
- Contains : Checks rather a specific element is on the queue or not.

Those are just a few examples of queue methods. There are more methods that can be used with queues.

## Big O Efficiency

Depending of the method that is being used it will have a different performance using the Big O notation.

- Enqueue : O(1)
- Dequeue : O(1)
- Count : O(1)
- Contains O(n)

Because the queue only allows to add o remove elements from the back and front of the queue, the efficiency goes down
to O(1) because it know from where to remove or add. The queue also keeps track of its size, so the count method is also
O(1). The contains method is different. The queue doesn't keep track of every element, so it needs to search through the
whole queue in search of the desire element. In the worst case scenario the element will be in the end of the queue, so
the big O is O(n).

## Real Life Applications

Our car wash line is a real life example of a queue in real life.

Queue are a representation of lines, so almost every possible line that you can see in real life are representations of
queues. Here are a few examples:

- Car wash line
- Music Playlist
- Wait list in a restaurant
- Class wait list
- Game wait room


## Music Playlist Example

A common example of a queue that we see almost everyday, but we don't think about it is listening to our music playlist.
Our music playlist works exactly like a queue. We start to adding musics there and they play in the sequence that they were
added to First In First Out.

![Playlist diagram](Assets/QueuePics/playlistDiagram.png)

In the diagram above we can see how the playlist works like a queue. When you add a song to the playlist the song is added to
the using the Enqueue method. The playlist will Dequeue the song in the front of the list and play it. After que song is done
it will Dequeue the next and play the next and so forth. Notice that in queue you can't add elements inside the list of elements.
In other words you can add a song in the middle of the songs that you have added to the playlist. New songs added will always
be added to the end of the queue. That's the biggest difference between a queue and a list.

The code below would be the representation of the playlist working in c#.

```csharp
Queue playList = new Queue();

//When we add a song to a playlist that the program uses the enqueue method to add the song
playList.Enqueue("Californication");
playList.Enqueue("Scar Tissue");
playList.Enqueue("Under the Bridge");

//The program then dequeue the first song and send the song to be played and when the song is done the next one is dequeued
var musicToPlay = playList.Dequeue();
//musicToPlay variable which holds the song will be passed to the function that plays the song
```

## Problem to Solve: Game waiting room

Write a program that will manager the waiting room for a online game. The waiting room will begin empty and as players start to
enter the game they will be added to the waiting room. A game needs at least 4 players to be begin. The program will receive
players from a server. You will represent the server. So the program will ask for a player username and game mode. The server(you) 
will give a players username and choose a game mode, so the program adds the player to the respective waiting room queue. The program
will constantly check if the waiting room have 4 players. If the waiting room has 4 players all the players are dequeued from the waiting
room because they will start a game.

Below is an example of the output:

```
Choose a game mode:
1. Battle royal
2. Team mode
3. Campaign
Your choice: 2
Player username: user1

None of the rooms have enough players

Choose a game mode:
1. Battle royal
2. Team mode
3. Campaign
Your choice: 2
Player username: user2

None of the rooms have enough players

Choose a game mode:
1. Battle royal
2. Team mode
3. Campaign
Your choice: 2
Player username: user3

None of the rooms have enough players

Choose a game mode:
1. Battle royal
2. Team mode
3. Campaign
Your choice: 2
Player username: user4

Team mode game began with: user1,user2,user3,user4

Choose a game mode:
1. Battle royal
2. Team mode
3. Campaign
Your choice: 0

The waiting room was finished.
```

You can check the solution here: [Solution](Queue-solution)





