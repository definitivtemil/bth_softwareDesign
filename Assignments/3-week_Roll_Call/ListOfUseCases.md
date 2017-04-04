# List of Use Cases for System; TwitterNetHack

## Assignment in the course PA1415 Programvarudesign  

#### 2017-04-07

### Authors:
Name    | Social Security Number | Thinking | Writing |
--------|------------------------|----------|---------|
Axel    | XXXXXXXX-XXXX	         | 100%     | 100%    |
Carl    | XXXXXXXX-XXXX	         | XX%      | XX%     |
Emil    | XXXXXXXX-XXXX	         | XX%      | XX%     |
Shaya   | XXXXXXXX-XXXX	         | XX%      | XX%     |
Peter   | XXXXXXXX-XXXX	         | XX%      | XX%     |

//don't put in social number yet


### System description:
The system is a game in the form of a dungeon crawler.  
The game will be about the user surviving in a dungeon while gathering loot and killing enemies.
While having internet access, the user will be able to connect his/hers game session to twitter  
and see the in-game world change as the twitter feed does.
 

### Use Cases:
The game is supposed to be able to:
- update player
- Connect to multiplayer
- Send text message to other players

//must be  5-15 use cases listed   

---
Use case: playerLogin  

Actors: Player, system

Description: 
The player inserts his/hers username and password into the dedicated box and hits the login button. The system checks the input to see if it matches any in the database. 

---

---
Use case: playerLogout

Actors: Player, system

Description:
A player hits the logout button, the system return to the state of the program's intro screen

---

---
Use case: saveGame  

Actors: Player, system

Description:  
A player hits the "save game" button, the system saves the state of the game to a text file and resumes the game.  

---

--- 
Use case: loadGame  

Actors: Player, system  

Description:  
The player hits the "load game" button. The system displays all saved games and the player chooses which saved game to resume.

---

---
Use case: movePlayer

Actors: Player, system

Description: A player hits any of the arrow keys and the system moves the player 1 square in that direction.

---

---
Use case: playerAttack

Actors: Player, system

Description: The player presses the "attack button" in order to attack in the direction last moved.

---

---
Use case: pickUpItem

Actors: Player, system

Description: The player walks over an item on the ground, the system adds it to the player's inventory.

---

---
Use case: customisePlayer

Actors: Player, system

Description: The player iterates through pre-selected ascii characters. When the player presses the "confirm button", the system assigns that character to the player's current profile. 

---

---
Use case: generateDungeonWithTwitter

Actors: System

Description: When the game session starts, the system gathers data from a selected twitter feed and uses it to generate a dungeon. 

---

---
Use case: generateDungeonWithoutTwitter

Actor: System

Description: When the game session starts, the system generates data and uses that data to generate a dungeon. 

---

---
Use case: throwItem

Actors: Player, system

Description: When the player presses the dedicated "throw button", the system removes the item from the player's inventory and moves it in the direction that the player is headed.

---

---
Use case: connectToMultiplayerSession

Actors: Player, system

Description:
---
