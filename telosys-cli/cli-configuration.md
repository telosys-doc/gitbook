# CLI configuration

The configuration of Telosys-CLI is defined in the file **`telosys-cli.cfg`**.  This file is located in the directory where Telosys-CLI has been installed.  It can be edited with any text editor.

For now, this file simply allows you to define a **specific external editor** that will be launched  for all "edit" commands (eg "eb", "ecfg", etc.)

Telosys-CLI comes with its own text editor, but this editor is quite basic and requires a graphical interface (eg GNOME or KDE for Linux). So you might prefer to set another text editor.

Telosys allows you to define a command to launch your favorite text editor :      "Visual Source Code", "Atom", "Sublime Text", "Notepad++", etc

## Text editor configuration

Use the **`EditorCommand`** propterty to define the command that will be launched by Telosys-CLI.

The value is the OS command to execute to launch the editor. If the executable file is accessible via the "PATH", you can use it as a simple command (without full path). Otherwise, you need to find where the editor is installed and use the full path.

The variable **`$FILE`** is used to represent the file to edit.

### Examples

**Visual Studio Code** ( executable file is "code" )

```
EditorCommand = code $FILE
EditorCommand = D:/Tools/Microsoft VS Code/code.exe $FILE 
```

**Atom editor** ( executable file is "atom" )

```
EditorCommand = atom $FILE
EditorCommand = D:/Tools/atom/atom.exe $FILE
```

**Sublime Text** ( executable file is "subl" )

```
EditorCommand = subl $FILE
EditorCommand = D:/Tools/SublimeText/subl.exe $FILE
```

**Notepad++** ( executable file is "notepad++" )

```
EditorCommand = notepad++ $FILE
EditorCommand = C:/Program Files (x86)/Notepad++/notepad++.exe $FILE
```

**Linux Mint editors**

```
EditorCommand = /usr/bin/xed $FILE
EditorCommand = /usr/bin/gnome-terminal -e "vi $FILE"
EditorCommand = /usr/bin/gnome-terminal -e "nano $FILE"
```

**Linux Lubuntu editors**

```
EditorCommand = /usr/bin/leafpad $FILE & 
EditorCommand = /usr/bin/lxterminal -e "vi $FILE"
EditorCommand = /usr/bin/lxterminal -e "nano $FILE"
```
