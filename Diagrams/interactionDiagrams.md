## Player Login
```@plantuml



activate systemhandler



-->systemhandler: pressesLoginButton(name, pass)
activate database
systemhandler-->database: sendsCredentials(name, pass)
activate file
database-->file: getInfo()
file-->database: sendInfo(name, pass)
deactivate file
database-->systemhandler: response(text)
deactivate database
<--systemhandler:welcomeMessage()




```
## Player Logout
```@plantuml
activate systemhandler
-->systemhandler: pressesLogoutButton()
activate database
systemhandler --> database: saveGame()
deactivate database
<-- systemhandler: goodbyeMessage()


```
## Pick Up Item
```@plantuml
activate characterHandler
activate character
-->characterHandler: walks over item

characterHandler-->character:additem(item)
character-->characterHandler: updateInfo(info)
deactivate character
<--characterHandler:displayUpdatedInfo()
```
## Join game session
```@plantuml
---> selfUpdatingWindow: joins game session
selfUpdatingWindow --> systemHandler: sends option to join
systemHandler --> server: joins game session
server --> serverDatabase: checks for previous progression for player
serverDatabase --> server:
server --> serverDatabase: loads available character and progress for player
server --> systemHandler: send game session info
systemHandler --> selfUpdatingWindow: send game session info
deactivate selfUpdatingWindow
selfUpdatingWindow --> selfUpdatingWindow: updates to online session
activate selfUpdatingWindow
<-- selfUpdatingWindow: display game session
```
## disconnect game session
```@plantuml
--> selfUpdatingWindow: presses disconnect button
selfUpdatingWindow --> systemHandler: sends disconnect signal
systemHandler --> server: disconnects
server --> serverDatabase: stores data about disconnected player
deactivate server
systemHandler --> selfUpdatingWindow: sends disconnected signal
<-- selfUpdatingWindow: displays disconnected message
 --> selfUpdatingWindow: presses shutdown button
selfUpdatingWindow --> systemHandler: sends shutdown signal
deactivate selfUpdatingWindow
deactivate systemHandler


```

## Move Player
```@plantuml
alt online
loop until player wants to disconnect
--> selfUpdatingWindow: input for game session
selfUpdatingWindow --> systemHandler: sends input
systemHandler --> server: sends input
server --> server: alters game session according to input
server --> serverDatabase: saves current session to database
server --> systemHandler: sends new current info for game session
systemHandler --> selfUpdatingWindow: sends current data
<--selfUpdatingWindow: displays current session
end

else offline
loop until player wants to quit
--> selfUpdatingWindow: input for game session
selfUpdatingWindow --> systemHandler: sends input
systemHandler --> selfUpdatingWindow: sends current data
<--selfUpdatingWindow: displays current session
end
end
```
## Player Attack
```@plantuml
alt online
loop until player wants to attack
--> selfUpdatingWindow: input for game session
selfUpdatingWindow --> systemHandler: sends input
systemHandler --> server: sends input
server --> server: updates game session
server --> serverDatabase: saves current session to database
server --> systemHandler: sends new current info for game session
systemHandler --> selfUpdatingWindow: sends current data
<--selfUpdatingWindow: displays current session
end

else offline
loop until player wants to attack
--> selfUpdatingWindow: input for game session
selfUpdatingWindow --> systemHandler: sends input
systemHandler --> selfUpdatingWindow: sends current data
<--selfUpdatingWindow: displays current session
end
end

```
## Generate dungeon with Twitter
```@plantuml

---> selfUpdatingWindow: presses generate button
selfUpdatingWindow --> systemHandler: generate signal
systemHandler --> twitterAPI: generate()
twitterAPI-->twitter: request data()
twitter-->twitterAPI : data
twitterAPI-->systemHandler :data
systemHandler-->systemHandler: generateDungeon()
systemHandler --> selfUpdatingWindow: send game session info
selfUpdatingWindow --> selfUpdatingWindow:updates representation of  current session
<-- selfUpdatingWindow: display game session


``` 
## Generate dungeon without Twitter
```@plantuml

---> selfUpdatingWindow: presses generate button
selfUpdatingWindow --> systemHandler: generate signal
systemHandler --> systemHandler: generateRandomData()
systemHandler-->systemHandler: generateDungeon()
systemHandler --> selfUpdatingWindow: send game session info
selfUpdatingWindow --> selfUpdatingWindow:updates representation of  current session
<-- selfUpdatingWindow: display game session


``` 
