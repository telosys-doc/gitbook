# Telosys editor configuration

To use VSCode as the default editor for all Telosys editing commands, simply configure the 'editor command' in the Telosys-CLI configuration file.

To do so edit the file "**telosys-cli.cfg**" located in the directory where Telosys-CLI is installed and set the "**EditorCommand**" parameter to the "_VSCode command_" ("code.exe").

Example:&#x20;

**`EditorCommand`**` ``=`` `**`C:/xxx/yyyy/Programs/Microsoft VS Code/Code.exe $FILE`**

Doing so, all editing commands "ee", "em", etc,  will open the file to edit in a VSCode page.



