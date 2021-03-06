### Igloo
> Feel like home while working in SNOW ;)

Igloo provides an enviroment to carry out development (script related) on a servicenow instance from local machine using VS Code.

  - Import/Export scripts using handy shortcuts
  - Compare local code with that on local machine 
  - Traverse through included scripts smoother than ever ..!

##### How to configure

1. Install Igloo extension
2. Create a new folder for your application.
3. Create a file with name "iglooconfig.txt" with the following content
    ```
    {
        "url" : "<your instance URL>",
        "username" : "<username>",
        "password" : "<password>",
        "app_name" : "<Name of the application you want to manage"
    }
    ```
4. Open the folder in VS Code and verify the extension being loaded from the message "Igloo : active" in the status bar.
5. Use the shortcut key (Ctrl + Alt + a / ctrl + option + a) to pull all scripts of the application given in configuration, from the servicenow instance. The scripts will be stored in 'Servicenow' directory which will be auto-created in the working directory.

>Note : The extension will be activated only if the file "iglooconfig.txt" is present in the workspace.

##### Usage

```
Pull all the scripts from SNOW instance
Ctrl + Alt + a [Mac : ctrl + option + a]
Note : This command won't replace the already existing files (to avoid accident) but will download any files that exist on SNOW instance and not on local machine.
```

```
Export the script (currently open in editor) to SNOW instance
Crtl + Alt + e [Mac : ctrl + option + e]
You will be given a choice (a dropdown at top) to proceed with export action, to check the diff first or to abort the operation.
This will replace the code in script on SNOW instance with that in the script on the local machine.
```

```
Import the script (currently open in editor) from SNOW instance.
Crtl + Alt + i [Mac : ctrl + option + i]
You will be given a choice (a dropdown at top) to proceed with import action, to check the diff first or to abort the operation.
This will replace the code in local script with that fetched from SNOW instance.
```

```
Load refered or extended script (Similar to Goto-Definition)
Eg. var x = new SomeScript()
To view the SomeScript file, select text 'SomeScript' and press Ctrl + Alt  + f [Mac : ctrl + option + f]
```

```
Compare the script (currently open in editor) with that on SNOW Instance
Ctrl + Alt + d [Mac : ctrl + option + d]
Select one option from the dropdown to choose to compare local with remote or vice versa
It will give a diff between local and remote copies of the script
```

```
Tip : Have a look at the diff (ctrl + alt + d / ctrl + option + d) with remote file before importing or exporting scripts, to avoid accidential replacement of code.
```

>Note : The following type of scripts will be fetched and managed :
>1. Mid server script includes
>2. Script includes
>3. UI Actions
>4. Business rules
>5. Client Scripts
>6. Scheduled Script Executions

>Troubleshooting :
>If something goes terribly wrong and most functionalities stop working, try deleting the "Servicenow"
>folder and download again using ctrl + alt + a / ctrl + option + a
