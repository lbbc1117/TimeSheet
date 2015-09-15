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
        sheetData : [[0,1,1],[1,1,1]]
    }
});
```

TimeSheet.js relies on jQuery, so jQuery must be included in your page before TimeSheet.js.

```HTML
<script type="text/javascript" src="/your/path/to/jquery-1.11.3.min.js"></script>
<script type="text/javascript" src="/your/path/to/TimeSheet.js"></script>
```

There is a css file TimeSheet.css, and it is necessary but can be partially customized to change the looking.

## Initialization
        
### Initial options:
```javascript
/*   TimeSheet should be binded on element TBODY, and its subelements have some default classes as follow:
*
*   sheetHead ---- class: .TimeSheet-head
*   colHead ---- class: .TimeSheet-colHead
*   rowHead ---- class: .TimeSheet-rowHead
*   cell ---- class: .TimeSheet-cell
*/
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
```javascript
data : {
    //"name" is to set the text shown in the header.
    //"title" is to set the text shown when the header is hovered.
    //"style" is css code to customize the style of the header.
   colHead : [
    {name:"name1",title:"",style:"width,background,color,font"},
    {name:"name2",title:"",style:"width,background,color,font"},...
   ]
}
```
Row headers shall be initialized the same way.

###To specify the sheet header:
```javascript
data : {
    //"name" is to set the text shown in the header.
    //"style" is css code to customize the style of the header.
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

###Add class to sheetHead:
```javascript
sheetClass : "userAddedClass"
```

###Specify a callback for starting selecting event:
```javascript
start : function(ev){
    //...
}
```

###Specify a callback for ending selecting event:
```javascript
/*
* @param ev 
* @param selectedArea : the index of the top-left cell and the bottom-right cell -- {topLeft:[0,1], bottomRight:[2,2]}
* */
end : function(ev, selectedArea){
    //...
}
```

###Init remarks area:
```javascript
remarks : {
    title : "说明",     // The remarks header
    default : "未设置"  // The default text of row remark
},
```


## API
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

###Get the default remark text:
```javascript
sheet.getDefaultRemark();
```

## Example 
A file example.html is offered to show the main functions of TimeSheet.js. Just download this whole project and unzip it, and open this html file in your browser. 

