---
priority: 0.9
title: Final Robot Design
excerpt: What our robot can do
categories: aboutus
background-image: ourrobot2.jpg

---
## Our Finalized Robot

<p align="center">
  <img src="/images/finalrobot.jpg" width="600px" height="450px"/><br/>
</p>

Throughout the Fall 2018 semester, we created a robot that could:
- Navigate a maze
- Start when a 660 Hz noise is detected
- Use sensors to follow lines and detect walls
- Avoid other robots using IR detection
- Use depth first search and path planning algorithm to determine how to navigate through the maze
- Communicate using radios to update a GUI 
- Detect treasures using image processing

**Our final robot cost: $86.00**
- Pololu Line Sensors (3 @ $3.00): $9.00
- Short Range IR sensors (3 @ $7.00): $21.00
- Camera: $14.00
- Parallax servos (2 @ $13.00): $26.00
- Arduino Uno: $16.00


### Modifications to Robot Design
Beyond the baseline requirements from the labs and milestones required in class, we made several improvements to our robot so that it would have the best chance when competing against other robots in the final competition. We document these additions and improvements in this section.

#### Better Maze-Solving Algorithm

#### Mechanics
While iteratively testing our robot in the maze, we learned several things about the mechanics of our robot. First, our robot was a little bit top heavy from the two batteries and large breadboard on its top tier. 
- weight bearing towards bottoms
- perfboarding everything/making a shield

#### Speed vs Searching Algorithm Tradeoff
- How our larger wheels didn't work out for us

#### Debugging
- LED indicators

### Ideas for Future Improvements
- Schmitt triggers to make line sensors digital inputs
