## system sequence diagram:
```@plantuml
actor player
activate selfUpdatingWindow
activate system
player --> selfUpdatingWindow: starts game 
player --> selfUpdatingWindow: credentials
selfUpdatingWindow--> system: sends credentials
system --> system: checks credentials
system --> selfUpdatingWindow: sends response
selfUpdatingWindow --> player: displays welcome message
deactivate selfUpdatingWindow 
selfUpdatingWindow --> selfUpdatingWindow: updates to menu window
activate selfUpdatingWindow
selfUpdatingWindow --> player: displays options
deactivate selfUpdatingWindow

alt online session
player --> selfUpdatingWindow: presses connect button
activate selfUpdatingWindow
selfUpdatingWindow --> player: adress request
player --> selfUpdatingWindow: server adress
selfUpdatingWindow --> system: server adress
system --> server: connection request
activate server
server --> system: credentials request
system --> selfUpdatingWindow: credentials request
selfUpdatingWindow --> player: asks for credentials
player --> selfUpdatingWindow: credentials
selfUpdatingWindow --> system: credentials
system --> server: credentials
server --> server: checks credentials
server --> system: response
system --> selfUpdatingWindow: welcome message
selfUpdatingWindow --> player: displays successful connection attempt
deactivate selfUpdatingWindow
selfUpdatingWindow --> selfUpdatingWindow: updates to menu for online session 
activate selfUpdatingWindow
selfUpdatingWindow --> player: displays options
player --> selfUpdatingWindow: joins game session
selfUpdatingWindow --> system: sends option to join
system --> server: joins game session
server --> server: checks for previous progression for player
server --> server: loads available character and progress for player
server --> system: send game session info
system --> selfUpdatingWindow: send game session info
deactivate selfUpdatingWindow
selfUpdatingWindow --> selfUpdatingWindow: updates to online session
activate selfUpdatingWindow
selfUpdatingWindow --> player: display game session

loop until player wants to disconnect
player --> selfUpdatingWindow: input for game session 
selfUpdatingWindow --> system: sends input
system --> server: sends input
server --> server: alters game session according to input
server --> server: saves current session to database
server --> system: sends new current info for game session
system --> selfUpdatingWindow: sends current data
selfUpdatingWindow --> player: displays current session
end

player --> selfUpdatingWindow: presses disconnect button
selfUpdatingWindow --> system: sends disconnect signal
system --> server: disconnects
server --> server: stores data about disconnected player
deactivate server
system --> selfUpdatingWindow: sends disconnected signal
selfUpdatingWindow --> player: displays disconnected message
player --> selfUpdatingWindow: presses shutdown button
selfUpdatingWindow --> system: sends shutdown signal
deactivate selfUpdatingWindow
deactivate system


else offline session
player --> selfUpdatingWindow: presses 

end
```

## States:
```@plantuml
start

if(correctinput?) then (yes)
-	allow
else (no)
-	deny
endif

stop
```

```@plantuml
class player{
username : string
xPos : int
yPos : int
inventory : strignArray
move()
attack()
throw()
}
class server{
ip : string
}
object login
player --> login
```
