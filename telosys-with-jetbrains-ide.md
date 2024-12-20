# Telosys with JetBrains IDE

For seamless integration of **Telosys** with a **JetBrains IDE** (IntelliJ, PyCharm, GoLand, PhpStorm, etc.), the simplest approach is to launch the telosys command in the IDE's integrated **terminal** and install the **plugin** that provides syntax highlighting for .entity files.



### 1 – Launching Telosys in the Terminal

**Prerequisite**: \
The **`telosys`** command must be accessible via the **`PATH`** (an environment variable of the shell you are using; see "Telosys installation" for details).

**Steps**:

* Open a new tab in the IDE's terminal with the shell of your choice (by default, the current directory is the root of the active project).&#x20;
* Launch Telosys from this shell: \
  Command: **`telosys`** (or **`tt`** for older versions). \
  Telosys starts in the current directory.
* Set the Telosys "home" directory with the command  **`h .`**&#x20;

**Note**: \
You can also launch Telosys with the -h . parameter so that the "home" directory is set immediately.\
Command:   **`telosys -h .`**&#x20;



### 2 - Terminal customization

You can also use the IDE settings to define Telosys as the terminal shell.

**Steps**:

* Open the "**Settings**" (Ctrl + Alt + S)
* Go to  "**Tools / Terminal**"
* Define Telosys as the default shell :&#x20;
  * Shell path:  **`aaa/bbb/ccc/telosys.bat -h .`**\
    (telosys command full path, with ".bat" extension on Windows)
  * Default tab name: **`Telosys`**



By doing so, Telosys will be launched by default every time a new tab is opened in the terminal ( for example by clicking on “**`+`**” or with "**`Ctrl+Shift+T`**" )



### 3 - Plugin installation

