## TUTORIAL ON RazorPage .Net6.0

### Installer
* [.Net 6](https://dotnet.microsoft.com/en-us/download/dotnet/6.0)
* [VS Code](https://code.visualstudio.com/download)
* [C# Extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) for VS Code
* [C# Extensions](https://marketplace.visualstudio.com/items?itemName=kreativ-software.csharpextensions) for VS Code
* VS Code [Visual Theme](https://marketplace.visualstudio.com/items?itemName=zhuangtongfa.Material-theme) **(*JIKA MAHU*)**
* VS Code [Icon Theme](https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme) **(*JIKA MAHU*)**
* [MongoDB Community Edition](https://fastdl.mongodb.org/windows/mongodb-windows-x86_64-5.0.8-signed.msi)
* [MongoDB Shell](https://www.mongodb.com/try/download/shell)
* [MongoDB Compass](https://www.mongodb.com/try/download/compass)


### Reference
* [MongoDB](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-windows/)
* [MongoDB Compass](https://www.guru99.com/installation-configuration-mongodb.html)
* [MongoDB Shell](https://www.mongodb.com/docs/mongodb-shell/)

***

### How to create project

1. Type this command on Terminal to create a project with authentication

    ```console 
    dotnet new webapp -o TestRazor -au individual
    ``` 

2. To trust the code before run the project

    ```console 
    dotnet dev-certs https --trust
    ``` 

3. To run code
    
    ```console 
    code -r TestRazor
    ``` 

***

### Problem run with debugging .net6.0

1. After finish create project, click fn+F5 on keyboard
2. Choose .NET 5+ and NET Core
    > ![image](https://user-images.githubusercontent.com/47632993/169677721-e83e5164-b87d-4eec-8432-1a0e8c3107a9.png)
3. launch.json fail will be appeared and run the project again
4. This popup will be appeared. Click the circled button.
    > ![image](https://user-images.githubusercontent.com/47632993/169677792-b97e0fe3-54f0-4279-a143-fd7132fab634.png)
5. Click the "*Create task.json from template*"
    > ![image](https://user-images.githubusercontent.com/47632993/169677806-a6aa8a5f-2e53-410a-a139-60d3bd381310.png)
6. Choose .NET Core
    > ![image](https://user-images.githubusercontent.com/47632993/169677866-88c9e586-3fb6-4c8f-a4a1-dfa774be4dc2.png)
7. Open launch.json, on this line, change "*< insert-target-framework-here >*" to net6.0 and "*< insert-project-name-here >*" to project name such as TestRazor
8. Insert comma "," beside "stopAtEntry": false
9. Insert this code below "stopAtEntry": false,
    
    ```JSON 
    "serverReadyAction": {
                "action": "openExternally",
                "pattern": "\\bNow listening on:\\s+(https?://\\S+)"
            },
    ```
10. Save project and run it back
11. Project will be open automatically on browser
