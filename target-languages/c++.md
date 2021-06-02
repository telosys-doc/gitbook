# C++

C++ language is supported since version : **3.3.0**

To define **C++** as the target language in a template file :

```text
#set( $env.language = 'C++' )
```

The information below shows the behavior of the generator when 'C++' is the current target language.  


## Types conversion 

The table below describes how model neutral types are automatically converted to C++ types with potential impact due to annotations \(@UnsignedType, @NotNull, @PrimitiveType, @ObjectType\)

<table>
  <thead>
    <tr>
      <th style="text-align:left">Model type</th>
      <th style="text-align:left">Default</th>
      <th style="text-align:left">
        <p>@UnsignedType</p>
        <p>@NotNull</p>
      </th>
      <th style="text-align:left">
        <p>@PrimitiveType</p>
        <p>@ObjectType</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">string</td>
      <td style="text-align:left"><b>string</b>
      </td>
      <td style="text-align:left">string (U)
        <br />string (N)</td>
      <td style="text-align:left">
        <p>string (P)</p>
        <p>string (O)</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">byte</td>
      <td style="text-align:left"><b>char</b>
      </td>
      <td style="text-align:left">
        <p>unsigned char (U)</p>
        <p>char (N)</p>
      </td>
      <td style="text-align:left">
        <p>char (P)</p>
        <p>char (O)</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">short</td>
      <td style="text-align:left"><b>short</b>
      </td>
      <td style="text-align:left">unsigned short (U)</td>
      <td style="text-align:left">short</td>
    </tr>
    <tr>
      <td style="text-align:left">int</td>
      <td style="text-align:left"><b>int</b>
      </td>
      <td style="text-align:left">unsigned int (U)</td>
      <td style="text-align:left">int</td>
    </tr>
    <tr>
      <td style="text-align:left">long</td>
      <td style="text-align:left"><b>long</b>
      </td>
      <td style="text-align:left">unsigned long (U)</td>
      <td style="text-align:left">long</td>
    </tr>
    <tr>
      <td style="text-align:left">decimal</td>
      <td style="text-align:left"><b>double</b>
      </td>
      <td style="text-align:left">double (U)</td>
      <td style="text-align:left">double</td>
    </tr>
    <tr>
      <td style="text-align:left">float</td>
      <td style="text-align:left"><b>float</b>
      </td>
      <td style="text-align:left">float (U)</td>
      <td style="text-align:left">float</td>
    </tr>
    <tr>
      <td style="text-align:left">double</td>
      <td style="text-align:left"><b>double</b>
      </td>
      <td style="text-align:left">double (U)</td>
      <td style="text-align:left">double</td>
    </tr>
    <tr>
      <td style="text-align:left">boolean</td>
      <td style="text-align:left"><b>bool</b>
      </td>
      <td style="text-align:left">bool (U)</td>
      <td style="text-align:left">bool</td>
    </tr>
    <tr>
      <td style="text-align:left">date</td>
      <td style="text-align:left"><b>std::tm</b>
      </td>
      <td style="text-align:left">std::tm (U)</td>
      <td style="text-align:left">std::tm</td>
    </tr>
    <tr>
      <td style="text-align:left">time</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">timestamp</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">binary</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>



### Simpletype and full type

|  Model type |  Simple type |  Full type |
| :--- | :--- | :--- |
| string | string | string |
| byte | char | char |
| byte | unsigned char | unsigned char |
| short | short | short |
| short | unsigned short | unsigned short |
| int | int | int |
| int | unsigned int | unsigned int |
| long | long | long |
| long | unsigned long | unsigned long |
| decimal | double | double |
| float | float | float |
| double | double | double |
| boolean | bool | bool |
| date | std::tm | std::tm |
| time |  |  |
| timestamp |  |  |
| binary |  |  |

### Remarks

The type conversion has an impact on :

*  $attribute.type
*  $attribute.fullType
*  $attribute.simpleType
*  $attribute.wrapperType
*  $attribute.isPrimitiveType\(\)

'@UnsignedType' has effect only for char, short, int, long

'@NotNull' has no effect  
'@PrimitiveType' has no effect  
'@ObjectType' has no effect  


## Literals

### TRUE, FALSE, NULL

|   | Generated  |
| :--- | :--- |
| TRUE | **true** |
|  FALSE | **false** |
|  NULL | **NULL** |

### Examples of generated literals

|  Model type |  Language type |  Language full type |  Language literal value example |
| :--- | :--- | :--- | :--- |
| string | string | string | "AAA" |
| byte | char | char | 1 |
| byte | unsigned char | unsigned char | 1 |
| short | short | short | 1 |
| short | unsigned short | unsigned short | 1 |
| int | int | int | 100 |
| int | unsigned int | unsigned int | 100 |
| long | long | long | 1000 |
| long | unsigned long | unsigned long | 1000 |
| decimal | double | double | 10000.77 |
| float | float | float | 1000.5 |
| double | double | double | 1000.66 |
| boolean | bool | bool | true |
| date | std::tm | std::tm | NULL |
| time |  |  | NULL |
| timestamp |  |  | NULL |
| binary |  |  | NULL |

