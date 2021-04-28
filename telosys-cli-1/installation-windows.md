---
title: Installation on Windows
weight: 8
---

# Installation on Windows

## Prerequisite

**Java 8 \(or +\)** must be installed, that's all.

You can check it with the command   
    `X:\> java -version`

## Installation

### 1\) Download

With your browser go to page [Telosys-CLI](http://www.telosys.org/cli.html)

Click on the button " **Download Telosys-CLI** " and choose the "Latest version"

A ZIP file "telosys-cli-x.x.x-xxx.zip" will be downloaded.

### 2\) Unzip

Copy the "zip file" in the directory where you want to install Telosys.

Use your favorite zip tool to unzip "telosys-cli-x.x.x-xxx.zip" in this directory \(eg "Extract Here" \)

### 3\) Update 'PATH' environment variable

To be able to launch Telosys from any location, just add its directory to the "**PATH**".

* Open the Start Search, type in “**variable**”,  and choose “**Edit the system environment variables**”:
* In the "**System Properties**" window : 

  click the "**Advanced**" tab, 

  then click the "**Environment Variables**" button.

* In the "**Environment Variables**" window : 

  in the "**System variables**" section 

  select the "**Path**" variable and click the "**Edit**" button

* Add the Telosys directory in the PATH variable

### 4\) Run Telosys

Now if the PATH variable is set correctly you can launch Telosys from any directory.

Open a command window \( open the Start Search and enter "**cmd**" \)

Move to the directory where you want to use Telosys  
    `X:\> cd myproject`

Launch Telosys-CLI with the **`tt`** command \( that is `tt.bat` \)   
   `X:\myproject> tt`

### 5\) You can also create a shortcut on your desktop

For more convenience you can create a shortcut on the desktop

To launch Telosys in its own directory :  `X:\telosys-dir\tt.bat`

To launch Telosys in a specific directory \(eg a project directory\) use '**-h**' option :   
    `X:\telosys-dir\tt.bat -h X:\myproject-dir`

You can use the "telosys.ico" file as the shortcut icon.

