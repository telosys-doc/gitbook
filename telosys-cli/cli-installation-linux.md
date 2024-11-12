# Installation on Linux

## Prerequisite

**Java 8 (or +)** must be installed, that's all.

You can check it with the command  `java -version`

## Installation

### 1) Download

With your browser go to "[**Download**](https://www.telosys.org/download/telosys-cli/index.html)" page

Choose the "Latest version" and ckick "Download" button.

A ZIP file "telosys-cli-x.x.x-xxx.zip" will be downloaded.

### 2) Unzip the file

Copy the “zip file” in the directory where you want to install Telosys.

Unzip the downloaded file :    \
    `unzip telosys-cli-x.x.x-xxx.zip`

Make the shell scripts "**`tt`**" and "**`telosys`**" executable    \
    `chmod 777 tt`\
    `chmod 777 telosys`

### 3) Update 'PATH' environment variable

To be able to launch Telosys from any location, just add its directory to the "**PATH**".  \
    `export PATH=$PATH:/path/to/telosys-dir`

### 4) Run Telosys

Now if the PATH variable is set correctly you can launch Telosys from any directory.

Move to the directory where you want to use Telosys     \
&#x20;   `cd myproject`

Launch Telosys-CLI with **`tt`** command or with **`telosys`** command (since ver 4.2.0)
