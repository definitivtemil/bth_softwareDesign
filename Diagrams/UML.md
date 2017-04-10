## Login:
```@plantuml
actor Player
Player --> Login: credentials
Login --> System: authentication request
actor database
System --> database : gather required 
System --> Login: authentication response
Login --> Player: response
```

## Connecting to server
```@plantuml
actor player
player --> system : presses connect button
actor server
system --> server : connection request
server --> system : connection response
system --> player :  
```

## Relations:
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
