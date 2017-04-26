# User stories

## Assignment in the course PA1415 Programvarudesign  

#### 2017-04-11

### Authors:
Name                    | Social Security Number | Thinking | Writing |
------------------------|------------------------|----------|---------|
Axel Gehlin Björnberg   |  x	                    | 20%      | 50%     |
Carl Sandnes            |  x                     | 20%      | 20%     |
Emil Nero               |  x                     | 20%      | 30%     |
Shaghayegh Pourmahdi    |  x	                    | 20%      | 00%     |
Peter Eriksson          |  x	                    | 20%      | 00%     |



### Actor description:  
**Server**:  
The server is the physical computer which people connect to in order to use multiplayer function and access the chat function.
It also holds saved games for multiplayer sessions.

**System**:  
The system refers to the code being run in the background that handles and responds to the player inputs.

**Player**:  
The player refers to the user of the machine/game. The one who inputs commands to the system and expects different results
depending on the input.

### System description:  
The goal of the system is to have a functional and stable program which goal is to mimic the popular "mindhack" game,
with randomly (or with the help of twitter), generated dungeons.  
As well as a functional multiplayer, where other players can join an ongoing session.

The system shall also have to option of connecting to an existing server and communicate with it.
The system shall also handle communication with others through the server which it is connected to.  

### High-level Epics:
**Motivation**:  
We prioritised in the current order because we deemed it important that the ones
on top works before the ones under. This is because some depend on other parts of the system to work properly.
Without the correct parts of the system working, the parts which depend upon previous parts, will not be functional.
Therefore, we have chosen to prioritise the parts which other parts of the system relies upon.

**Epics**:
```
Epic: Accessing game sessions


Actors:
Player, System

Description:
As a player I want to, upon game start-up and logging in, have the option to choose between my previously saved games, or to start a new one, as well as customising my character before playing. 

Conditions of satisfaction:
-	Player is logged in
-	Player has chosen their own appearance
-	A previous game is loaded into or a new one created.

```
```
Epic: Generate dungeon

Actors:
Player, System

Description:  
As a player I want to be able to generate a new game session using keywords from a twitter feed of my choice, as long as I have an internet connection whilst doing so, as an interesting way to generate a dungeon layout.
Otherwise generate a random dungeon from a pre existing offline-available algorithm, so that an internet connection is not required to play.

Conditions of satisfaction:
-	A new dungeon layout is generated
-	Player entered the game

```
```
Epics: Accessing online game sessions

Actors:
Player, System

Description:
As a player I want to be able to play online, connecting either randomly or by entering a server address, so that I can play and communicate alongside others.

Conditions of satisfaction:
-	The player is connected to and playing on a server.

```
```
Epic: Playing the game

Actors:
Player, System

Description:
As a player I want to be able to move around, attack enemies, pick up and use items, and if online, write to my fellow players in my game session, so that I am provided an interactive experience.

Conditions of satisfaction:
-	Player can move
-	Player can attack
-	Player can loot
-	Player can use items
-	Player can type and send messages
```
```
Epic: Quit the game

Actors:
Player, System

Description:
As a player, I want the option to save my game manually as I am quitting my current game session, so that I may resume playing the same session later. Alternatively if I am playing online, the server automatically saves if all players has hit the disconnect button and quit the session.

Conditions of satisfaction:
-	Players game is saved locally if offline
-	Players game is saved on server if online
-	Player is logged out
```
# User stories and use cases

#### User stories:
```
player login: 
As a player, I want the ability to access my own account so I can access my own previous progress.  
So that I won't have to start over again every time I play.
Conditions of satisfaction:
 - 
```
```
player logout:
As a player, I want the ability to log out of my account so nobody else can play on it or tamper with my progress without my permission.
Conditions of satisfaction:
 - 
```
```
save game:  
As a player, I want to be able to save my current session,  
so I may go back to it at another time and continue where I left off.
Conditions of satisfaction:
 - Players game is saved to text file
```
```
move player:
As a player, I want to be able to move my character around in dungeons,  
so that I can explore them.
Conditions of satisfaction:
 - 
```
```
player attack:
As a player, I want to be able to attack whatever is before me. 
Be it enemy or object. So I can decimate any foe in my path.
Conditions of satisfaction:
 - 
```
```
pickup item:
As a player, I want the ability to pick up items which are scattered around the dungeon. 
So I can change my current loadout and attributes.
Conditions of satisfaction:
 - 
```
```
customise player:
As a player, I want the ability to change the appearance of my personal character. 
So that I may stand out in the crowd.
Conditions of satisfaction:
 - 
```
```
new world:
As a player, I want to be able to randomly generate a dungeon using both keywords selected from a certain twitter feed and using a set offline-available algorithm, so that I have a world to move in.
Conditions of satisfaction:
 - 
```
```
throw item:
As a player, I want the option to throw something within my inventory,  
as either an offensive action or as a means to discard something from my inventory. 
Conditions of satisfaction:
 - 
```
```
multiplayer session:  
As a player, I want the option of connecting to an online session, 
so that I may play along and communicate with other players.
Conditions of satisfaction:
 - 
```
```
chat with other players:
As a player, I want the ability to communicate other players in my online game session through text in a chatroom,  
so that we may strategize and socialize.
Conditions of satisfaction:
 - 
```


#### Estimated velocity per iteration
25 points/week average
10 points/week minimum
35 points/week maximum

80 points Minimum total
100 points average total
120 points maximum total

#### Implementation plan  
**Motivation**:  
With this order of priority we will create a functional product as soon as possible, we will then be able to test the other functions in the game directly, saving time and effort. And would also, if we had any, be able to beta test the program with the users and get feedback.
 
**Prioritisation plan**:  

Points                  | name of use cases                |
------------------------|----------------------------------|
10                      | selfUpdatingWindow               |
17                      | generateDungeonWithoutTwitter    |
6                       | movePlayer                       |
5                       | pickupItem                       |
6                       | playerAttack                     |
4                       | throwItem                        |
4                       | save game                        |
4                       | load game                        |
1                       | player Login                     |
1                       | Player logout                    |
8                       | connectToMultiplayerSession      |
2                       | Chat with multiplayer session    |
6                       | disconnectFromMultiplayerSession |
20                      | generateDungeonWithTwitter       |
3                       | customisePlayer                  |

