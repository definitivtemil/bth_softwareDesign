# User stories

## Assignment in the course PA1415 Programvarudesign  

#### 2017-04-11

### Authors:
Name                    | Social Security Number | Thinking | Writing |
------------------------|------------------------|----------|---------|
Axel Gehlin Björnberg   |  x	                   | 20%      | 50%     |
Carl Sandnes            |  x                     | 20%      | 20%     |
Emil Nero               |  x                     | 20%      | 30%     |
Shaghayegh Pourmahdi    |  x	                   | 20%      | 00%     |
Peter Eriksson          |  x	                   | 20%      | 00%     |



### Actor description:  
**Server**:  
The server is the physical computer wich people connect to in order to use multiplayer function and access the chat function.
It also holds the savegames for multiplayer sessions.

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
We prioritised in the current order beacuse we deemed it important that the ones
on top works before the ones under. This is because some depend on other parts of the system to work properly.
Without the correct parts of the system working, the parts which depend upon previous parts, will not be functional.
Therefore, we have chosen to prioritise the parts which other parts of the system relies upon.

**Epics**:
```
Epic: Accessing game sessions

Description:
When the player starts the game, a login screen pops up and requires the player to input his/her credentials.
The system then checks these credentials and allows the player access to the players previous game sessions
and the ability to create new ones. If the player choses a previously played game session, the player will
have the abilty to decide the apperance of the character the player will control during the game session.  
```
```
Epic: Generate dungeon

Description:  
If the player decides to make a new game session and there's an internet connecttion, the player will have the
option to generate a dungeon based on gathered information from a specific twitter feed. When the player has chosen
a twitter feed, the system will gather data through the twitter API and use the gathered data to base the dungeon
generation on.  
If there is no internet connection available, the system will generate its own data to base the dungeon generation on.  
```
```
Epics: Accessing online game sessions

Desciption:
The system gives the player the option to connect to a server which hostes a game session for multiple players.
In this session, the multiple players are able to see, communicate, and interact with eachother. When the player
decides to join an online session, the player is asked to provide the address to the server, after which, the system
connects to the server and allows the player to play with other players and communicate with them.
```
```
Epic: Playing the game

Description:
When the player has chosen what game session to join. He/she will be put into a generated dungeon with enemies
to kill and loot to gather. While in the game session, the player shall be
able to move, attack and interact with items freely. When in the multiplayer session, the player will be able
to interact with otehr players as well.  
```
```
Epic: Quit the game

Description:
Whenever the player decides to end the game session and the player is connected to an online session, the
player quits by pressing the disconnect button. The server saves the current progress of the player as the
players system quits.  
When the player decides to quit a local game, the system will end the game session and quit it self without
saving the current progress. It is therefore important that the player saves the progress before ending the
local game session.
```
#### User stories:
```
User story: playerLogin  

As a player, I want the ability to access my own account so I can access my own previous progress.  
So that I won't have to start over again everytime I play.
```
```
User story: playerLogout:  

As a player, I want the option to log out.  
So that my play session is not altered when I'm not present.
```
```
User story: saveGame:  

As a player, I want to be able to save my current session.  
So I may go back to it at another time and continue where I left off.
```
```
User story: loadGame:  

As a player, I want the option of loading a saved game.  
So I may continue where I left off in a previous session.
```
```
User story: movePlayer:

As a player, I want to be able to move my character around in dungeons.  
So that I can explore them.
```
```
User story: playerAttack:

As a player, I want to be able to attack whatever is before me.
Be it enemy or object. So I can decimate any foe in my path.
```
```
User story: pickupItem:

As a player, I want the ability to pick up items which are scattered around the dungeon.
So I can change my current loadout and attributes.
```
```
User story: customisePlayer:

As a player, I want the abilty to change the apperance of my personal character.
So that I may stand out in the crowd.
```
```
User story: generateDungeonWithTwitter:

As a player, I want to be able to randomly generate a dungeon using keywords selected from a certain twitter feed,  
as an interesting way of creating levels.
```
```
User story: generateDungeonWithoutTwitter:

As a player, I want an option to generate a new game session when there is no internet connection,  
using a set offline-available algorithm.
```
```
User story: throwItem:

As a player, I want the option to throw something within my inventory,  
as either an offensive action or as a means to discard something from my inventory.
```
```
User story: connectToMultiplayerSession:  

As a player, I want the option of connecting to an online session,
so that I may play along and communicate with other players.
```
```
User story: chatWithOtherPlayers:

As a player, I want the ability to communicate other players in my online game session through text in a chatroom,  
so that we may strategize and socialize.
```

