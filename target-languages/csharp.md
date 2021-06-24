# C\#

To define **C\#** as the **target language** in a template file :

```text
#set( $env.language = 'C#' )
```

The information below shows the behavior of the generator when C\# is the current target language.  


## Types conversion 

The table below describes how model neutral types are automatically converted to C\# types with potential impact due to attribute annotations.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Model type</th>
      <th style="text-align:left">C# type</th>
      <th style="text-align:left">with annotation</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">string</td>
      <td style="text-align:left"><b>string <br />String</b>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>@ObjectType</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">byte</td>
      <td style="text-align:left"><b>sbyte <br />byte <br />SByte</b>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>@UnsignedType
          <br />@ObjectType</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">short</td>
      <td style="text-align:left"><b>short <br />ushort <br />Int16</b>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>@UnsignedType</p>
        <p>@ObjectType</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">int</td>
      <td style="text-align:left"><b>int <br />uint <br />Int32</b>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>@UnsignedType</p>
        <p>@ObjectType</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">long</td>
      <td style="text-align:left">
        <p><b>long</b>
        </p>
        <p><b>ulong</b>
        </p>
        <p><b>Int64</b>
        </p>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>@UnsignedType</p>
        <p>@ObjectType</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">decimal</td>
      <td style="text-align:left">
        <p><b>decimal</b>
        </p>
        <p><b>Decimal</b>
        </p>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>@ObjectType</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">float</td>
      <td style="text-align:left"><b>float<br />Single</b>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>@ObjectType</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">double</td>
      <td style="text-align:left"><b>double<br />Double</b>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>@ObjectType</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">boolean</td>
      <td style="text-align:left"><b>bool<br />Boolean</b>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>@ObjectType</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">date</td>
      <td style="text-align:left"><b>DateTime</b>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">time</td>
      <td style="text-align:left"><b>DateTime</b>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">timestamp</td>
      <td style="text-align:left"><b>DateTime</b>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">binary</td>
      <td style="text-align:left"><b>byte [ ]</b>
      </td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>

### Annotations effects

* **@UnsignedType** has effect only for **byte**, **short**, **int**, **long**
* **@ObjectType** switches to **.Net types**  \( System.Int64, System.Boolean, etc\)
* **NotNull** has no effect
* **@PrimitiveType** has no effect

