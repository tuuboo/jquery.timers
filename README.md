# jquery.timers
jQuery Timers is a high level abstraction of setTimeout and setInterval. It links into the jQuery chain so you can apply timers to elements directly in your code, leading to much more intuitive timer-based code. It also adds numerous advanced features such as labelling of timers and abstracted timer ids.

```javascript
/*************************************************************
*   everyTime(时间间隔, [定时器名称], 函式名称, [次数限制], [等待函式程序完成])
*************************************************************/ 
//每1秒执行函式test() 
function test(){ 
   //do something... 
} 
$('body').everyTime('1s',test); 
 
//每1秒执行 
$('body').everyTime('1s',function(){ 
//do something... 
}); 
 
//每1秒执行，并命名定时器名称为A 
$('body').everyTime('1s','A',function(){ 
//do something... 
}); 
 
//每20秒执行，最多5次，并命名定时器名称为B 
$('body').everyTime('2das','B',function(){ 
//do something... 
},5); 
 
//每20秒执行，无限次，并命名定时器名称为C 
//若时间间隔抵到，但函式程序仍未完成则需等待执行函式完成后再继续计时 
$('body').everyTime('2das','C',function(){ 
    //执行一个会超过20秒以上的程序 
},0,true); 
 
/***********************************************************
*   oneTime(时间间隔, [定时器名称], 呼叫的函式)
***********************************************************/ 
//倒数10秒后执行 
$('body').oneTime('1das',function(){ 
//do something... 
}); 
 
//倒数100秒后执行，并命名定时器名称为D 
$('body').oneTime('1hs','D',function(){ 
//do something... 
}); 
 
/************************************************************
* stopTime ([定时器名称], [函式名称])
************************************************************/ 
//停止所有的在$('body')上定时器 
$('body').stopTime (); 
 
//停止$('body')上名称为A的定时器 
$('body').stopTime ('A'); 
 
//停止$('body')上所有呼叫test()的定时器 
$('body').stopTime (test); 
```
