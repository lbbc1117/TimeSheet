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
###Initialization options:
```javascript
options :
{
   data : {
       dimensions : ..., 
       colHead : ...,
       rowHead : ...,
       sheetHead : ...,
       sheetData : ...    
   },

   // optional options
   sheetClass : "",
   start : function(ev){...},
   end : function(ev){...},
   remarks : false
}
```

###To specify the row numbers and the column numbers:
```javascript
data : {
   dimensions : [2,3]  //[row,column]
}
```

###To specify the column headers:
"name" is to set the text shown in the header
"title" is to set the text shown when the header is hovered
"style" is css code to customize the style of the header
```javascript
data : {
   colHead : [
   {name:"name1",title:"",style:"width,background,color,font"},
   {name:"name2",title:"",style:"width,background,color,font"},...
   ]
}
```
Row headers shall be initialized the same way.

###To specify the sheet header:
"name" is to set the text shown in the header
"style" is css code to customize the style of the header
```javascript
data : {
   sheetHead : {name:"headName",style:"width,height,background,color,font"}
}
```

###To initialize the sheet data:
It is a 2D, row-major ordered array. The value of it's basic elements has to be 0 or 1.
```javascript
data : {
   sheetData : [[0,1,1,0,0],[...],[...],...]
}
```
