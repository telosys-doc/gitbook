---
title: Installation on Linux
weight: 10
---

# Installation on Linux

## Prerequisite

**Java 8 \(or +\)** must be installed, that's all.

You can check it with the command  `java -version`

## Installation

### 1\) Download

With your browser go to page [Telosys-CLI](http://www.telosys.org/cli.html)

Click on the button " **Download Telosys-CLI** " and choose the "Latest version"

A ZIP file "telosys-cli-x.x.x-xxx.zip" will be downloaded.

Or if you prefer to use the command line :        `wget http://www.telosys.org/download/telosys-cli/telosys-cli-x.x.x-xxx.zip`

### 2\) Unzip the file

Copy the “zip file” in the directory where you want to install Telosys.

Unzip the downloaded file :        `unzip telosys-cli-x.x.x-xxx.zip`

Make the shell script "tt" executable        `chmod 777 tt`

### 3\) Update 'PATH' environment variable

To be able to launch Telosys from any location, just add its directory to the "**PATH**".       `export PATH=$PATH:/path/to/telosys`

### 4\) Run Telosys

Now if the PATH variable is set correctly you can launch Telosys from any directory.

Move to the directory where you want to use Telosys        `cd myproject`

Launch Telosys-CLI with the **`tt`** command \( that is `tt` shell script \)        `tt`

