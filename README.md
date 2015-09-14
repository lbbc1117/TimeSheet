# TimeSheet
A jQuery plugin for time planning

## Get Start 
It is simple to use TimeSheet:

```HTML
<link rel="stylesheet" href="/your/path/to/TimeSheet.css" type="text/css" media="screen">
<script type="text/javascript" src="/your/path/to/jquery-1.11.3.min.js"></script>
<script type="text/javascript" src="/your/path/to/TimeSheet.js"></script>
<script type="text/javascript">
$(document).ready(function(){
        var sheet = $("#J_timedSheet").TimeSheet({
            data: {
                dimensions : [2,3],
                colHead : [{name:"00",title:"00:00-01:00"},{name:"01",title:"01:00-02:00"},{name:"02",title:"02:00-03:00"}],
                rowHead : [{name:"2015-09-01"},{name:"2015-09-02"}],
                sheetHead : {name:"日期\\时间"},
                sheetData : [[0,1,1],[1,1,1],[0,0,0]]
            }
        });
    });
</script>
```
