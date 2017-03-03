# Getting started
---
This is a simple guide to help you get started with your environment so you can start scripting.

# Downloading the required files
---
You need to download a few files to use this plugin. These instructions are for 64-bit systems.
If you're on a Linux system:
  You'll need to use these commands in the directory you want the server to be in.
  
    wget http://v04.maxorator.com/server/VCMP04_server_v22_linux64.zip
    7z -x VCMP04_server_v22_linux64.zip
    rm VCMP04_server_v22_linux64.zip
    chmod 774 mpsvrrel64
    mkdir plugins
    wget http://dryback.xyz/sqmod/binaries/build_10.7z
    7z -x build_10.7z
    rm build_10.7z
    mv linux64/standalone plugins
    
    echo "" > server.cfg
