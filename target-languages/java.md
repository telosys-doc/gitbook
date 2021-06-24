# Java

**Java** is the target language **by default**, so you don't have to define it explicitly. 

However, you can define it with the following instruction :

```text
#set( $env.language = 'Java' )
```



The information below shows the behavior of the generator when Java is the current target language.  


## Types conversion 

The table below describes how model neutral types are automatically converted to Java types with potential impact due to attribute annotations.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Model type</th>
      <th style="text-align:left">Java type</th>
      <th style="text-align:left">with annotation</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">string</td>
      <td style="text-align:left"><b>String</b>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">byte</td>
      <td style="text-align:left"><b>Byte<br />byte<br />byte</b>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>@NotNull
          <br />@PrimitiveType</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">short</td>
      <td style="text-align:left">
        <p><b>Short</b>
        </p>
        <p><b>short</b>
        </p>
        <p><b>short</b>
        </p>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>@NotNull
          <br />@PrimitiveType</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">int</td>
      <td style="text-align:left">
        <p><b>Integer<br />int</b>
        </p>
        <p><b>int</b>
        </p>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>@NotNull
          <br />@PrimitiveType</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">long</td>
      <td style="text-align:left">
        <p><b>Long</b>
        </p>
        <p><b>long</b>
        </p>
        <p><b>long</b>
        </p>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>@NotNull
          <br />@PrimitiveType</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">decimal</td>
      <td style="text-align:left"><b>BigDecimal</b>
      </td>
      <td style="text-align:left">
        <p></p>
        <p></p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">float</td>
      <td style="text-align:left">
        <p><b>Float</b>
        </p>
        <p><b>float</b>
        </p>
        <p><b>float</b>
        </p>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>@NotNull
          <br />@PrimitiveType</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">double</td>
      <td style="text-align:left">
        <p><b>Double</b>
        </p>
        <p><b>double</b>
        </p>
        <p><b>double</b>
        </p>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>@NotNull
          <br />@PrimitiveType</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">boolean</td>
      <td style="text-align:left">
        <p><b>Boolean</b>
        </p>
        <p><b>boolean</b>
        </p>
        <p><b>boolean</b>
        </p>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>@NotNull
          <br />@PrimitiveType</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">date</td>
      <td style="text-align:left"><b>Date</b>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">time</td>
      <td style="text-align:left"><b>Date</b>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">timestamp</td>
      <td style="text-align:left"><b>Date</b>
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

* **@UnsignedType**  no effect \(all numeric types are signed in Java\)
* **@ObjectType**  switches to the standard wrapper type for the current type  \(Byte, Short, Integer, Long, Float, Double, Boolean\)
* **@PrimitiveType**  switches to the primitive type if possible \(byte, short, int, long, float, double, boolean\)
* **@NotNull**  switches to primitive type if possible in order to avoid 'null' value

\*\*\*\*

### Specific types 

*  **$attribute.fullType**
  * for an "object type" returns the fully-qualified class name  \(java.lang.String,  java.lang.Integer,  java.math.BigDecimal, etc \)
  * for a "primitive type" returns the primitive type as is 

    \( int,  double,  etc \)
*  **$attribute.simpleType** 
  * for an "object type" returns the simple class name \( String,  Integer,  Double, etc \)
  * for a "primitive type" returns the primitive type as is

    \( int,  double,  etc \)
*  **$attribute.wrapperType**  returns the Java wrapper type class associtated with the current type \(Integer, Double, etc \)

