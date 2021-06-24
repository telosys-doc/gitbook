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

