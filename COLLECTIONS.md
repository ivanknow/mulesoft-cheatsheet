* map
```javascript

%dw 2.0
output application/json
---
["jose", "pedro", "mateo"] map (value, index) -> { (index) : value}

```

* filter
```j́avascript
[9,2,3,4,5] filter (value, index) -> (value > 2)
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
