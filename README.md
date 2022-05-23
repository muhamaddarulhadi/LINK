## Training on RazorPage .Net6.0 and MongoDB

### Installer
* [.Net 6](https://dotnet.microsoft.com/en-us/download/dotnet/6.0)
* [VS Code](https://code.visualstudio.com/download)
* [C# Extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) for VS Code
* [C# Extensions](https://marketplace.visualstudio.com/items?itemName=kreativ-software.csharpextensions) for VS Code
* [SQL lite Extensions](https://marketplace.visualstudio.com/items?itemName=qwtel.sqlite-viewer) **(*JIKA MAHU*)**
* VS Code [Visual Theme](https://marketplace.visualstudio.com/items?itemName=zhuangtongfa.Material-theme) **(*JIKA MAHU*)**
* VS Code [Icon Theme](https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme) **(*JIKA MAHU*)**
* [MongoDB Community Edition](https://fastdl.mongodb.org/windows/mongodb-windows-x86_64-5.0.8-signed.msi)
* [MongoDB Shell](https://www.mongodb.com/try/download/shell)
* [MongoDB Compass](https://www.mongodb.com/try/download/compass)


### Reference
* [MongoDB](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-windows/)
* [MongoDB Compass](https://www.guru99.com/installation-configuration-mongodb.html)
* [MongoDB Shell](https://www.mongodb.com/docs/mongodb-shell/)
* [Web Api with MongoDB](https://docs.microsoft.com/en-us/aspnet/core/tutorials/first-mongo-app?view=aspnetcore-6.0&tabs=visual-studio-code)
* What is [BSON](https://www.mongodb.com/basics/bson#:~:text=BSON%20stands%20for%20Binary%20Javascript,binary%20formats%2C%20like%20Protocol%20Buffers.)
* [JSON and BSON](https://www.mongodb.com/json-and-bson)
* [Blazor CRUD with MongoDB](https://www.c-sharpcorner.com/article/blazor-crud-using-mongodb/)
* [Bypass CDN Link consist of @](https://stackoverflow.com/questions/67969553/how-to-get-cdn-with-in-it-in-cshtmlrazor-page)

***


### How to create RazorPage project

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

### Problem run RazorPage with debugging .Net6.0

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

***

### Install Package

1. Type on terminal
    
    ```console
    dotnet tool install --global dotnet-ef 
    ```

***

### Migrations Command **(ONLY FOR DEVELOPMENT ONLY)**

1. Create migrations
    
    ```console
    dotnet ef migrations add tbl_departments   
    ```
    Note: tbl_departments is migration name

2. Remove migrations
    
    ```console
    dotnet ef migrations remove
    ```
    
3. Execute migrations
    
    ```console
    dotnet ef database update
    ```

***

### Razorpage connection string using MongoDB  

1. Install this package using terminal
    
    ```console
    dotnet add package MongoDB.Driver
    ```
2. To use MongoDB on Entity Models

    ```c#
    using MongoDB.Bson;
    using MongoDB.Bson.Serialization.Attributes;
    ```

3. Edit appsettings.json, example :

    ```JSON
    "UMMDBConnection" : {
        "ConnectionString" : "mongodb://localhost:27017",
        "DatabaseName" : "UUMDB",
        "DepartmentCollectionName" : "Departments"
    },
    ```

***

### VS Code keyboard cheat sheet

1. [Shortcut Foo](https://www.shortcutfoo.com/app/dojos/vscode-win/cheatsheet)
2. [Keyboard shortcuts for Windows](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf)
