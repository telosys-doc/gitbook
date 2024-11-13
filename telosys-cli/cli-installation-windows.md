# Installation on Windows

## Prerequisite

**Java 8 (or +)** must be installed, that's all.

You can check it with the command \
&#x20;   `X:\>`**`java -version`**

## Installation

### 1) Download

With your browser go to "[**Download**](https://www.telosys.org/download/telosys-cli/index.html)" page

Choose the "**Latest version**" and ckick "**Download**" button.

A ZIP file "telosys-cli-x.x.x-xxx.zip" will be downloaded.

### 2) Unzip

Copy the "zip file" in the directory where you want to install Telosys.

Use your favorite zip tool to unzip "telosys-cli-x.x.x-xxx.zip" in this directory (eg "Extract Here" )

### 3) Update 'PATH' environment variable

To be able to launch Telosys from any location, just add its directory to the "**PATH**".

* Open the Start Search, type in “**variable**”, \
  and choose “**Edit the system environment variables**”:
*   In the "**System Properties**" window :&#x20;

    click the "**Advanced**" tab,&#x20;

    then click the "**Environment Variables**" button.
*   In the "**Environment Variables**" window :&#x20;

    in the "**System variables**" section&#x20;

    select the "**Path**" variable and click the "**Edit**" button
* Add the **Telosys directory** in the **PATH** variable

### 4) Run Telosys

Now if the PATH variable is set correctly you can launch Telosys from any directory.

Open a command window ( open the Start Search and enter "**cmd**" )

Move to the directory where you want to use Telosys\
&#x20;   `X:\>`**`cd myproject`**

Launch Telosys-CLI using **`tt`** command (`tt.bat` )  \
&#x20;  `X:\myproject>`**`tt`**\
or **`telosys`** command (`telosys.bat`  since ver 4.2.0)\
&#x20;  `X:\myproject>`**`telosys`**

### 5) You can also create a shortcut on your desktop

For more convenience you can create a shortcut on the desktop

To launch Telosys in its own directory :  \
&#x20;   `X:\telosys-dir\tt.bat`

To launch Telosys in a specific directory (eg a project directory) use '**-h**' option : \
&#x20;   `X:\telosys-dir\tt.bat -h X:\myproject-dir`

You can use the "telosys.ico" file as the shortcut icon.
