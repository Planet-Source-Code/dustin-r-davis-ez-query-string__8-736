<div align="center">

## EZ Query string


</div>

### Description

I'm used to ASP so whaen i want to knwo the value of a variabl ein the querystring, i can just type in x = request.querystring("Name"). Well, now i made a function similar to this, it makes finding variables in the querystring Easy!
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Dustin R Davis](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/dustin-r-davis.md)
**Level**          |Beginner
**User Rating**    |3.0 (18 globes from 6 users)
**Compatibility**  |PHP 4\.0
**Category**       |[System Services/ Functions](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/system-services-functions__8-23.md)
**World**          |[PHP](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/php.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/dustin-r-davis-ez-query-string__8-736/archive/master.zip)

### API Declarations

I used some methods found on other submissions for query strings.


### Source Code

```
//main php file
include("querystring.php");
global $QUERY_STRING;
global $QS;
   //initialize Querystring
   $QS = Get_Query_String($QUERY_STRING);
   //get the variable
   $x = Get_QS("x",$QS);
   //print the variable!
   echo "x=".$x;
//querystring.php
<?php
function Get_Query_String($strQS) {
  $par = split("&",$strQS);
   for($i=0;$i<count($par);$i++) {
	  list($xQS[$i][0],$xQS[$i][1]) = split("=",$par[$i]);
   }
   return $xQS;
}
function Get_QS($varName,$QS_Array) {
	for($i=0;$i<count($QS_Array);$i++) {
    if($QS_Array[$i][0]==$varName) {
    	return $QS_Array[$i][1];
    }
  }
  return "";
}
?>
```

