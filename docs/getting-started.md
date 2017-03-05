## Getting stared

---
This guide will help you set up your environment so you can start with using the plugin.

## Downloading the required files

---
Firstly, you'll need the server itself. The server can be found [here](http://forum.vc-mp.org/?board=4.0).
Next, you'll need to download the plugin. The plugin build can be found [here](http://dryback.xyz/sqmod/binaries/build_latest.7z).
If you are on Windows, you will need an extra DLL if you wish to use MySQL. If you're on a 32-bit system, you'll need to use [this](http://dryback.xyz/sqmod/binaries/dependencies/win32/mysql_32.7z) DLL, and if you're on a 64-bit system, you'll need to use [this](http://dryback.xyz/sqmod/binaries/dependencies/win64/mysql_64.7z) DLL.

## Setting up the server

---
You'll first need to create the `plugins` directory. Then, extract the contents of build_10.7z. You'll find 4 directories: `linux32`, `linux64`, `windows32` and `windows64`. Choose the appropriate directory, and copy the contents of the `standalone` folder to `plugins`.

## Setting up the server's configuration file

---
To let the server know that it needs to load the SqMod plugin, create a `server.cfg` file and copy-paste the following contents into it:

    plugins mod_squirrel64 mod_sqlite64 mod_mysql64 
If you want your server to run on a port other than 8192, add this line:

    port [port]
Change `[port]` to the port you want your server to run on.

## Setting up the plugin's configuration file

---
For the SqMod plugin to work, it needs a configuration file. Create a `SqMod.ini` file and copy-paste the following contents into it (courtesy iSLC):

    # Squirrel options
    [Squirrel]
    # Configure the virtual machine stack size
    StackSize=2048
    # Enable error handling by the plugin
    ErrorHandling=true
    # Allow the plug-in to load even if no scripts were loaded
    EmptyInit=false
    
    # Logging options
    [Log]
    ConsoleDebug=true
    ConsoleUser=true
    ConsoleSuccess=true
    ConsoleInfo=true
    ConsoleWarning=true
    ConsoleError=true
    ConsoleFatal=true
    LogFileDebug=false
    LogFileUser=true
    LogFileSuccess=true
    LogFileInfo=true
    LogFileWarning=true
    LogFileError=true
    LogFileFatal=true
    ConsoleTimestamp=false
    LogFileTimestamp=true
    #Filename=mymod%Y-%m-%d.log
    # How much to output to console at startup
    # 0 minimal, 1 show more, 2 show even more, 3 show even more
    VerbosityLevel=3
    
    # List of scripts to load
    # - Compile=path > Compile the script and execute after all scripts were compiled
    # - Execute=path > Compile the script and execute it immediately
    # - Section=name > Search for more scripts in a different section
    [Scripts]
    Execute=main.nut
    
    # Custom script options
    [Options]
    
This file should be very easy to edit on your own.

## Creating the script file

---
We have made our `SqMod.ini` file such that it loads `main.nut`. Create a file `main.nut`, and copy-paste the following contents into it:

    print("Hello world!");

## Cleaning up

---
By now, all your achives should be safe to clean up. You can now delete them.
