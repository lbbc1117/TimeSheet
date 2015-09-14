# TimeSheet
A jQuery plugin for time planning

## Get Start 
It is simple to use TimeSheet:

```javascript
var sheet = $("#J_timedSheet").TimeSheet({
    data: {
        dimensions : [2,3],
        colHead : [{name:"00",title:"00:00-01:00"},{name:"01",title:"01:00-02:00"},{name:"02",title:"02:00-03:00"}],
        rowHead : [{name:"2015-09-01"},{name:"2015-09-02"}],
        sheetHead : {name:"日期\\时间"},
        sheetData : [[0,1,1],[1,1,1],[0,0,0]]
    }
});
```
