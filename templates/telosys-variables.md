# Telosys variables

Telosys provides a set of predefined variables which can be used in all template files.

## Standard variables

Standard variables have predefined names, their values are either set by Telosys or can be defined in the project configuration.

### Special characters

These variables are used to simplify the writing of templates when certain special characters are required and are difficult to mix with Velocity syntax.

These variables should be considered as "constants" and used as such.

| Variable name | Variable value |
| :--- | :--- |
| **$DOLLAR** \(dollar character\) | **$** |
| **$SHARP** \(sharp character\) | **\#** |
| **$AMP** \(ampersand character\) | **&** |
| **$QUOT** \(double quotation mark\) | **"** |
| **$LT** \(less-than sign\) | **&lt;** |
| **$GT** \(greater-than sign\) | **&gt;** |
| **$LBRACE** \(left brace\) | **{** |
| **$RBRACE** \(right brace\) | **}** |
| **$NEWLINE** \(new line character\) | **\n** |
| **$TAB** \(tabulation character\) | **\t** |



### Project configuration

These variables are specific for each project. They can be defined in the project configuration file \( "telosys-tools.cfg" \)

All the project configuration variables are usable in both templates files \(".vm" files\) and bundle configuration file \("templates.cfg"\).

#### Directories

<table>
  <thead>
    <tr>
      <th style="text-align:left">Variable name</th>
      <th style="text-align:left">Configuration value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>$SRC</b>
      </td>
      <td style="text-align:left">
        <p>Directory where to generate <b>sources</b>
        </p>
        <p>e.g. &quot;src/main/java&quot;, &quot;src&quot;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>$RES</b>
      </td>
      <td style="text-align:left">
        <p>Directory where to generate <b>resources</b>
        </p>
        <p>e.g. &quot;src/main/resources&quot;, &quot;conf&quot;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>$WEB</b>
      </td>
      <td style="text-align:left">
        <p>Directory where to generate <b>web files </b>
        </p>
        <p>e.g. &quot;src/main/webapp&quot;, &quot;www&quot;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>$TEST_SRC</b>
      </td>
      <td style="text-align:left">
        <p>Directory where to generate <b>test sources</b>
        </p>
        <p>e.g. &quot;src/test/java&quot;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>$TEST_RES</b>
      </td>
      <td style="text-align:left">
        <p>Directory where to generate <b>test resources</b>
        </p>
        <p>e.g. &quot;src/test/resources&quot;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>$DOC</b>
      </td>
      <td style="text-align:left">Directory where to generate <b>documentation files</b>
        <br />e.g &quot;doc&quot;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>$TMP</b>
      </td>
      <td style="text-align:left">
        <p>Directory where to generate <b>temporary files</b> 
        </p>
        <p>e.g. &quot;tmp&quot;, &quot;temp&quot;</p>
      </td>
    </tr>
  </tbody>
</table>

**Packages**

Variables usable for target languages having a notion of "packages" or "modules" or "namespaces" \(Java, Golang, C\#, etc\)

| Variable name | Configuration value |
| :--- | :--- |
| **$ROOT\_PKG** | The root package  containing all other packages |
| **$ENTITY\_PKG** | The package containing the entities  classes or structures |

## Specific variables

xxxx

