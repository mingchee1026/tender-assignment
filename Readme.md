# Tendermint Assignment

## Problem Statement
> Alien invasion

>Mad aliens are about to invade the earth and you are tasked with simulating the
invasion.
You are given a map containing the names of cities in the non-existent world of
X. The map is in a file, with one city per line. The city name is first,
followed by 1-4 directions (north, south, east, or west). Each one represents a
road to another city that lies in that direction.
For example:
Foo north=Bar west=Baz south=Qu-ux
Bar south=Foo west=Bee
The city and each of the pairs are separated by a single space, and the
directions are separated from their respective cities with an equals (=) sign.
You should create N aliens, where N is specified as a command-line argument.
These aliens start out at random places on the map, and wander around randomly,
following links. Each iteration, the aliens can travel in any of the directions
leading out of a city. In our example above, an alien that starts at Foo can go
north to Bar, west to Baz, or south to Qu-ux.
When two aliens end up in the same place, they fight, and in the process kill
each other and destroy the city. When a city is destroyed, it is removed from
the map, and so are any roads that lead into or out of it.
In our example above, if Bar were destroyed the map would now be something
like:
Foo west=Baz south=Qu-ux
Once a city is destroyed, aliens can no longer travel to or through it. This
may lead to aliens getting "trapped".
You should create a program that reads in the world map, creates N aliens, and
unleashes them. The program should run until all the aliens have been
destroyed, or each alien has moved at least 10,000 times. When two aliens
fight, print out a message like:

> *Bar has been destroyed by alien 10 and alien 34!*

## Assumptions
- All the cities will have unique names
- All the aliens will have unique names  
- There is no buffer period or time taken by alien to move from one city to next city, each move made by aliens are instantenous

> Note : this is a non deterministic system as all the moves made by the aliens are at random

## Special condition 
#### In some cases like for example 
- city1 north=city2
>alien 1 is spanned in city1 and alien 2 is spanned in city2 
In the next move alien2 will move to city1 and alien1 moves to city2 
this is the special case as we assume that there is no travel or buffer time between movements of aliens so in this scenario there we be no such situation that alien1 and alien2 are present in both the cities at the same time. The  moves made by aliens will be instantaneous


### Command line Instructions  
- to see all the flags
    >```
    >go run . --help
    >```

- default configuration run 
    - generates 10 random aliens in random cities, 10000 max iterations in simulation 
        >```
        >go run .
        >```
- sample command
    >```
    >go run . -alienname files/sample_alien_name.txt -totalalien 3 -verbose true      
    >```

    explanation :
    > - -alienname : path for sample name of the aliens
    > - -totalalien N: total N alien are generated in simulation
    > - -verbose true : prints useful information like current iteration number >   and    moves made by aliens in each iteration


- Run all tests at once 
    >```
    >go test ./... -v
    >```

### to do 
- [ ] determenistic simulation using seed value provided by user
- [ ] coverage report for code base 
- [ ] more unit tests
