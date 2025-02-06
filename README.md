# mulesoft-cheatsheet
* Get a Query Parameter:
```javascript
%dw 2.0
output application/json
import * from dw::util::Values
var queryParams = attributes.queryParams
---
queryParams.<paramName>

```

* Get a URI Parameter

```javascript
%dw 2.0
output application/json
var uriParams = attributes.uriParams
---
uriParams.<paramName>


```

* Add a Property to a Payload:
  
```javascript
%dw 2.0
output application/json
var originalPayload = payload
---
originalPayload ++ { newProperty: "value" }

```

* Remove a Property from a Payload:
 ```javascript
%dw 2.0
output application/json
var originalPayload = payload
---
originalPayload - "propertyName"

```
* Match command

 ```javascript
value match {
  case (<name>:) <condition> -> <routing expression>
  case (<name>:) <condition> -> <routing expression>
  else -> <when none of them matched>
}


```

* Format Date

 ```javascript

%dw 2.0
output application/json
import * from dw::core::Dates
var input = { date: "2025-02-05" }
---
{
  formattedDate: input.date as Date {format: "yyyy-MM-dd"} as String {format: "dd/MM/yyyy"}
}

 ```

 ```javascript

%dw 2.0
output application/json
import * from dw::core::Dates
var currentDate = now()
---
{
  formattedCurrentDate: currentDate as String {format: "dd-MM-yyyy"}
}


 ```
 ```javascript
%dw 2.0
output application/json
import * from dw::core::Dates
var input = { date: "05-Feb-2025" }
---
{
  formattedDate: input.date as Date {format: "dd-MMM-yyyy"} as String {format: "yyyy/MM/dd"}
}
 ```

Format number

 ```javascript
%dw 2.0
output application/json
import * from dw::core::Numbers
var number = 1234567.89
---
{
  formattedNumber: format(number, "###,###.##")
}

 ```
 ```javascript
%dw 2.0
output application/json
import * from dw::core::Numbers
var number = 1234.56
---
{
  formattedCurrency: format(number, "$###,###.00")
}

 ```
 ```javascript
%dw 2.0
output application/json
import * from dw::core::Numbers
var number = 42
---
{
  formattedWithLeadingZeros: format(number, "000000")
}

 ```
 ```javascript
%dw 2.0
output application/json
import * from dw::core::Numbers
var number = 0.85
---
{
  formattedPercentage: format(number * 100, "##0.00") ++ "%"
}

 ```


format 2 number after comma or dot

implode array

split array

get property with p() function

get property with {} notation

concat strings

set HTTP  status

setup security properties

use secure::

encrypt and decript with java

remove all nulls from payload

dataweave external file

map

flat

redux

isEmpty

sizeOf

default

optional query param
```ruby

```
