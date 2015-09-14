# TimeSheet
A jQuery plugin for time planning

![](http://static.oschina.net/uploads/space/2015/0914/165147_Xtq0_1047422.png)  

## Get Start 
It is simple to use TimeSheet:

```javascript
// TimeSheet has to be binded on a TBODY element
var sheet = $("#aTbodyElement").TimeSheet({
    data: {
        dimensions : [2,3],
        colHead : [{name:"00",title:"00:00"},{name:"01",title:"01:00"},{name:"02",title:"02:00"}],
        rowHead : [{name:"2015-09-01"},{name:"2015-09-02"}],
        sheetHead : {name:"日期\\时间"},
        sheetData : [[0,1,1],[1,1,1],[0,0,0]]
    }
});
```

TimeSheet.js relies on jQuery, so jQuery must be included in your page before TimeSheet.js.

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

###Get the state of a single cell:
```javascript
/*
* 获取单元格状态
* @param cellIndex ：[1,2]
* @return : 0 or 1
* */
sheet.getCellState([0,0]);
```

###Get the states of a single row:
```javascript
/*
 * 获取某行所有单元格状态
 * @param row ：2
 * @return : [1,0,0,...,0,1]
 * */
sheet.getRowStates(2);
```

###Get the states of whole sheet:
```javascript
/*
 * 获取表格所有单元格状态
 * @return : [[1,0,0,...,0,1],[1,0,0,...,0,1],...,[1,0,0,...,0,1]]
 * */
sheet.getSheetStates();
```

###Set the remark text of a single row:
```javascript
/*
* 设置某行的说明文字
* @param row : 2,
* @param text : '说明'
* */
sheet.setRemark(2,"说明");
```

###Clean the sheet (set all cells to 0):
```javascript
sheet.clean();
```

###Disable the sheet:
```javascript
sheet.disable();
```

###Enable the sheet:
```javascript
sheet.enable();
```

###Check if the sheet is full:
```javascript
/*
* 判断表格是否所有单元格状态都是1
* @return ： true or false
* */
sheet.isFull();
```

## Example 
A file example.html is offered to show the main functions of TimeSheet.js. Just download this whole project and unzip it, and open this html file in your browser. 

