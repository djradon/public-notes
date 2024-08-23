---
id: 7e2jxafaqhxdk5pdeqlw8e4
title: Mario Project
desc: 'Managing Active and healthy aging with use of caRing servIce robots.'
updated: 1724448285141
created: 1724447785671
---

- related: [[prdct.mario-ontology-network-mon]]


## Highlights

### Action

![](/assets/images/2024-08-23-14-20-16.png)

The MON’s Action module is meant to implement the  <a href="http://ontologydesignpatterns.org/wiki/Submissions:TaskExecution">Task Execution Ontology Design Pattern</a>. 
This module allows to keep track of the actions performed either by the robot or by its users. 
Actions execute and are classified by tasks. 
The class <tt>action:Task</tt> aims at collecting all the behaviors of the robot.

<b>Example of Usage</b>

We provide an example of usage of the Action ontology for specifying the following scenario.
X is a social robot can entertain its users by ​playing music, showing videos or telling jokes.
On 23 April 2015 from 3pm to 4p, X played some music for Monica.

```turtle
@prefix action: <https://w3id.org/MON/action.owl>
@prefix time: <https://w3id.org/MON/time.owl#>

:April23015Beg a time:Instant ;
   time:inXSDDateTime "2015-04-23T15:00:00+02:00" .


:April23015End a time:Instant ;
   time:inXSDDateTime "2015-04-23T16:00:00+02:00" .

:April23015 a time:Interval ;
   time:hasBeginning :April23015Beg ;
   time:hasEnd  :April23015End .

:MusicBehavior a action:Behavior .

:X a action:Agent .

:Monica a action:Agent .

:PlayMusicForMonica a action:Action ;
  time:atTime :April23015 ;
  action:byAgent :X ;
  action:executesTask :MusicBehavior ;
  action:hasParticipant :Monica .

</pre>