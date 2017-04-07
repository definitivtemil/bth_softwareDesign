## Login:
```@plantuml
actor Player
Player --> Login: credentials
Login --> System: authentication request
System --> database : gather required 
System --> Login: authentication response
Login --> Player: response
```

## Connecting to server
```@plantuml
actor Player
player --> system : presses connect button
system --> server : connection request
server --> system : connection response
```

## Relations:
```@plantuml
:enter credentials:
if(correct) then (yes)
	:login:
else (no)
	:enter again:
::
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
