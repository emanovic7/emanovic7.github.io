---
layout: post
title:      "JavaScript - Destructuring"
date:       2019-01-18 18:37:45 +0000
permalink:  javascript_-_destructuring
---


Recently I decided to refresh myself on JavaScript after spending too much time on Ruby and React, by “skimming” through tutorials on freeCodeCamp. I am not a JavaScript expert, I went through the course material at the FlatIron School and built an App or two with it.

Everything was fine and dandy until I got to a section on using ES6’s Destructuring Assignment, which stumped me for a good while. Destructuring is a big part of ES6, so it’s worth any amount of time spent acquainting oneself with it. As with everything I am not good at, I learn best by talking about it. So here’s a post on how I got around it.
Here’s how it’s defined on the Mozilla website:

The destructuring assignment syntax is a JavaScript expression that makes it possible to unpack values from arrays, or properties from objects, into distinct variables.
Let’s unpack that, using an object.

```
premLeagueTeam = {
  name: 'Manchester United',
  city: 'Manchester',
  manager: 'Jose Mourinho',
  captain: 'Antonio Valencia',
  standing: 7
};
```
Traditionally, if I wanted to pull name, I’d have to go
```
premLeagueTeam.name;
```
or store it in a variable like
```
const name = premLeagueTeam.name;
```

With ES6’s destructuring syntax, I can just do this
```
const { name } = premLeagueTeam;
```
But the best-est part is doing that for all (or as many as I want) of the object properties in one line, instead of doing that repetitively.
```
const { name, city, captain } = premLeagueTeam 
```
instead of
```
const name = premLeagueTeam.name;
const city = premLeagueTeam.city;
const captain = premLeagueTeam.captain;

This might all seem trivial, at least when you’re well versed in JavaScript, but it’s especially powerful and useful working with nested arrays and objects. Consider the same team object from before (I love English football and Manchester United, sue me), but with more information
```
premLeagueTeam = {
  name: 'Manchester United',
  city: 'Manchester',
  manager: 'Jose Mourinho', 
  coaches: {
    goalkeeping: { 
           name: 'Eric Steele',
           hometown: 'Britain'        
          } 
    defense: {
           name: 'Nemanja Vidic',
           hometown: 'Serbia'
          }
        }
  captain: 'Antonio Valencia',
  current_standing: 7
};
To get the hometown of the defense coach, I’d have had to go
```
const defensive_coach_hometown = premLeagueTeam.coaches.defense.hometown;
```
Imagine doing that for every nested object property, not too DRY. With restructuring, I can just do
```
const { defensive_coach_name, defensive_coach_hometown } = premLeagueTeam.coaches.defense;
```

I should have chosen better variable and object names, but you get the point.
I will write more on destructuring, as there’s more to it and I am sure I’ll stumble upon it using other javaScript based programs like React, but it’s worth getting the gist for now :)
```
