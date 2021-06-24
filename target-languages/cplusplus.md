# C++

**C++** language is supported since **version 3.3.0**

To define **C++** as the **target language** in a template file :

```text
#set( $env.language = 'C++' )
```

The information below shows the behavior of the generator when C++ is the current target language.  


## Types conversion 

The table below describes how model neutral types are automatically converted to C++ types with potential impact due to annotations \(@UnsignedType, @NotNull, @PrimitiveType, @ObjectType\)

<table>
  <thead>
    <tr>
      <th style="text-align:left">Model type</th>
      <th style="text-align:left">C++ type</th>
      <th style="text-align:left">with annotation</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">string</td>
      <td style="text-align:left"><b>string</b>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">byte</td>
      <td style="text-align:left">
        <p><b>char</b>
        </p>
        <p><b>unsigned char</b>
        </p>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>@UnsignedType</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">short</td>
      <td style="text-align:left">
        <p><b>short</b>
        </p>
        <p><b>unsigned short</b>
        </p>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>@UnsignedType</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">int</td>
      <td style="text-align:left">
        <p><b>int</b>
        </p>
        <p><b>unsigned int</b>
        </p>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>@UnsignedType</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">long</td>
      <td style="text-align:left">
        <p><b>long</b>
        </p>
        <p><b>unsigned long</b>
        </p>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>@UnsignedType</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">decimal</td>
      <td style="text-align:left"><b>double</b>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">float</td>
      <td style="text-align:left"><b>float</b>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">double</td>
      <td style="text-align:left"><b>double</b>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">boolean</td>
      <td style="text-align:left"><b>bool</b>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">date</td>
      <td style="text-align:left"><b>std::tm</b>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">time</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">timestamp</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">binary</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>

### Annotations effects

* **@UnsignedType**  has effect only for **char**, **short**, **int**, **long**
* **@NotNull**  has no effect
* **@PrimitiveType** no effect
* **@ObjectType**  no effect

### Specific types 

*  **$attribute.fullType** no effect
*  **$attribute.simpleType**  no effect
*  **$attribute.wrapperType**  no effect

So, for **C++** you can always use "**$attribute.type**"  


## Literal values

### TRUE, FALSE, NULL

|   | C++ literal |
| :--- | :--- |
| TRUE | **true** |
|  FALSE | **false** |
|  NULL | **NULL** |

### Generated literal values

Below some examples of literal values generated for each type :

<table>
  <thead>
    <tr>
      <th style="text-align:left">Model type</th>
      <th style="text-align:left">C++ type</th>
      <th style="text-align:left">C++ literal value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">string</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"><b>&quot;AAA&quot;</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">byte</td>
      <td style="text-align:left">
        <p>char</p>
        <p>unsigned char</p>
      </td>
      <td style="text-align:left"><b>1</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">short</td>
      <td style="text-align:left">
        <p>short</p>
        <p>unsigned short</p>
      </td>
      <td style="text-align:left"><b>1</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">int</td>
      <td style="text-align:left">
        <p>int</p>
        <p>unsigned int</p>
      </td>
      <td style="text-align:left"><b>100</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">long</td>
      <td style="text-align:left">
        <p>long</p>
        <p>unsigned long</p>
      </td>
      <td style="text-align:left"><b>1000</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">decimal</td>
      <td style="text-align:left">double</td>
      <td style="text-align:left"><b>10000.77</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">float</td>
      <td style="text-align:left">float</td>
      <td style="text-align:left"><b>1000.5</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">double</td>
      <td style="text-align:left">double</td>
      <td style="text-align:left"><b>1000.66</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">boolean</td>
      <td style="text-align:left">bool</td>
      <td style="text-align:left"><b>true  </b>or <b>false</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">date</td>
      <td style="text-align:left">std::tm</td>
      <td style="text-align:left"><b>NULL</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">time</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"><b>NULL</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">timestamp</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"><b>NULL</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">binary</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"><b>NULL</b>
      </td>
    </tr>
  </tbody>
</table>

