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
