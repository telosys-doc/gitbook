# Golang

**Golang** is supported since **version 3.3.0**

To define **Golang** as the **target language** in a template file :

```text
#set( $env.language = 'Go' )
```

The information below shows the behavior of the generator when Golang is the current target language.

## Types conversion 

The table below describes how model neutral types are automatically converted to Golang types with potential impact due to attribute annotations.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Model type</th>
      <th style="text-align:left">Go type</th>
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
      <td style="text-align:left"><b>byte <br />uint8</b>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>@UnsignedType</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">short</td>
      <td style="text-align:left"><b>int16 <br />uint16</b>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>@UnsignedType</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">int</td>
      <td style="text-align:left"><b>int32 <br />uint32</b>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>@UnsignedType</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">long</td>
      <td style="text-align:left"><b>int64<br />uint64</b>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>@UnsignedType</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">decimal</td>
      <td style="text-align:left"><b>float64</b>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">float</td>
      <td style="text-align:left"><b>float32</b>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">double</td>
      <td style="text-align:left"><b>float64</b>
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
      <td style="text-align:left"><b>time.Time</b>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">time</td>
      <td style="text-align:left"><b>time.Time</b>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">timestamp</td>
      <td style="text-align:left"><b>time.Time</b>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">binary</td>
      <td style="text-align:left"><b>[ ] byte</b>
      </td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>

### Annotations effects

* **@UnsignedType**  has effect only for **byte**, **short**, **int**, **long**
* **@ObjectType**  no effect
* **@NotNull**  no effect
* **@PrimitiveType**  no effect

### Specific types 

*  **$attribute.fullType** no effect \(always returns the standard Go type\)
*  **$attribute.simpleType** 

  no effect \(always returns the standard Go type\)

*  **$attribute.wrapperType**  no effect \(always returns the standard Go type\)

So, for **Golang** you can always use the basic "**$attribute.type**"

### See also

For more information about Golang types see :

* [https://golang.org/ref/spec\#Types](https://golang.org/ref/spec#Types)

## Literal values

### TRUE, FALSE, NULL

|   | Golang literal |
| :--- | :--- |
| TRUE | **true** |
|  FALSE | **false** |
|  NULL | **nil** |

### Generated literal values

Below some examples of literal values generated for each type :

<table>
  <thead>
    <tr>
      <th style="text-align:left">Model type</th>
      <th style="text-align:left">Golang type</th>
      <th style="text-align:left">Golang literal value</th>
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
        <p>byte</p>
        <p>uint8</p>
      </td>
      <td style="text-align:left"><b>1</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">short</td>
      <td style="text-align:left">int16
        <br />uint16</td>
      <td style="text-align:left"><b>1</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">int</td>
      <td style="text-align:left">int32
        <br />uint32</td>
      <td style="text-align:left"><b>100</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">long</td>
      <td style="text-align:left">int64
        <br />uint64</td>
      <td style="text-align:left"><b>1000</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">decimal</td>
      <td style="text-align:left">float64</td>
      <td style="text-align:left"><b>10000.77</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">float</td>
      <td style="text-align:left">float32</td>
      <td style="text-align:left"><b>1000.5</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">double</td>
      <td style="text-align:left">float64</td>
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
      <td style="text-align:left">time.Time</td>
      <td style="text-align:left"><b>nil</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">time</td>
      <td style="text-align:left">time.Time</td>
      <td style="text-align:left"><b>nil</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">timestamp</td>
      <td style="text-align:left">time.Time</td>
      <td style="text-align:left"><b>nil</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">binary</td>
      <td style="text-align:left">[ ] byte</td>
      <td style="text-align:left"><b>nil</b>
      </td>
    </tr>
  </tbody>
</table>



