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

get uri param

add properties to payload

remove payload property

format date

format number

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
