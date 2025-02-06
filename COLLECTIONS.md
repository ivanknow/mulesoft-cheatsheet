* map
```javascript

%dw 2.0
output application/json
---
["jose", "pedro", "mateo"] map (value, index) -> { (index) : value}

```

* reduce

```j́avascript

%dw 2.0
var myNums = [1,2,3,4]
var myEmptyList = []
output application/json
---
{
   "sum" : myNums reduce ($$ + $),
   "concat" : myNums reduce ($$ ++ $),
   "emptyList" : myEmptyList reduce ($$ ++ $)
}
```
