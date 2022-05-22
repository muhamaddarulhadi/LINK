## LINK

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



### How to create project

1. Type this command on Terminal


    ```console 
    dotnet new webapp -o TestRazor -au individual
    ``` 

2. To run code
    
    ```console 
    code -r TestRazor
    ``` 
    



### Problem run with debugging .net6.0

1. Selepas selesai create project, run project fn+f5
2. Pilih .net5+ and netcore
    > ![image](https://user-images.githubusercontent.com/47632993/169677721-e83e5164-b87d-4eec-8432-1a0e8c3107a9.png)
3. file launch.json akan dipaparkan dan run lagi sekali projek
4. paparan ini akan muncul dan tekan butang yang dibulatkan
    > ![image](https://user-images.githubusercontent.com/47632993/169677792-b97e0fe3-54f0-4279-a143-fd7132fab634.png)
5. Tekan yang paling atas sekali
    > ![image](https://user-images.githubusercontent.com/47632993/169677806-a6aa8a5f-2e53-410a-a139-60d3bd381310.png)
6. Pilih .NetCore
    > ![image](https://user-images.githubusercontent.com/47632993/169677866-88c9e586-3fb6-4c8f-a4a1-dfa774be4dc2.png)
7. Buka file launch.json dan di line ini, ubah "< insert-target-framework-here >" kepada net6.0 dan "< insert-project-name-here >" kepada nama project iaitu TestRazor
8. Masukkan koma iaitu "," di sebelah "stopAtEntry": false
9. Masukkan code ini dibawah "stopAtEntry": false,
    
    ```JSON 
    "serverReadyAction": {
                "action": "openExternally",
                "pattern": "\\bNow listening on:\\s+(https?://\\S+)"
            },
    ```
10. Save project dan run lagi sekali
11. Browser akan buka projek secara automatik
