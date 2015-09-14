# TimeSheet
A jQuery plugin for time planning

## Get Start 
It is simple to use TimeSheet:

```javascript
var sheet = $("#J_timedSheet").TimeSheet({
    data: {
        dimensions : [2,3],
        colHead : [{name:"00",title:"00:00"},{name:"01",title:"01:00"},{name:"02",title:"02:00"}],
        rowHead : [{name:"2015-09-01"},{name:"2015-09-02"}],
        sheetHead : {name:"日期\\时间"},
        sheetData : [[0,1,1],[1,1,1],[0,0,0]]
    }
});
```

TimeSheet.js relies on jQuery, so Jquery must be included in your page before TimeSheet.js.

```HTML
<script type="text/javascript" src="/your/path/to/jquery-1.11.3.min.js"></script>
<script type="text/javascript" src="/your/path/to/TimeSheet.js"></script>
```

There is a css file TimeSheet.css, and it is not a must when using TimeSheet.js. One can customize the style of sheets by their own css code.

## API
Initialization options:
```javascript
opt :
{
   data : {
        // [rows numbers, columns numbers] 
       dimensions : [7,8],  
       // 
       colHead : [{name:"name1",title:"",style:"width,background,color,font"},...]
       rowHead : [{name:"name1",title:"",style:"height,background,color,font"},{name:"name2",title:"",style:"height,background,color,font"},...]
       sheetHead : {name:"headName",style:"width,height,background,color,font"}
       sheetData : [[0,1,1,0,0],[...],[...],...]    sheet数据，二维数组，行主序，索引(a,b),a-行下标，b-列下标，每个cell只有0,1两态，与dimensions对应
   },

   sheetClass : "",
   start : function(ev){...}
   end : function(ev){...}
   remarks : false
}
```
