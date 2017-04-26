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
