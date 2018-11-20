We have used CODEBEAT to analysis JavaScript projects and CodeFactor to analysis C# projects. Here comes the technical debt of JS first. As there are few projects written by js, the grade is high with 3.9/4.0 score. ![cbgpa](https://github.com/ruanti2018-1/zy1-monogame/blob/master/technicaldebt/CBGPA.png)
Complexity, Styles will show as follows, Duplications and Security are no results and no changes. ![complexity](https://github.com/ruanti2018-1/zy1-monogame/blob/master/technicaldebt/cbcmp.png) ![styles](https://github.com/ruanti2018-1/zy1-monogame/blob/master/technicaldebt/cbsty.png)
Quick Wins tells us the function is too long to cause some error in ```Documentation/Styles/MonoGame/js/sharpdoc.js.SplitPane```, Namespaces help us measure technical debt and find refactoring opportunities. ![qw](https://github.com/ruanti2018-1/zy1-monogame/blob/master/technicaldebt/QW.png) ![name](https://github.com/ruanti2018-1/zy1-monogame/blob/master/technicaldebt/Nam.png)

CodeFactor reveals the overall grade score of Monogame is 8.75/10 which means B+. There are 3400 issues and 1430 files to be analyzed.![cf](https://github.com/ruanti2018-1/zy1-monogame/blob/master/technicaldebt/CFGPA.png)
Six factors relates to program developing are showed now: 

Complexity(185) | Style(2150) | Compatibility(2) | Performance(70) | Maintainability(992) | Accessibility(1)
----|-------|-----|-------|-----|-----
 Low`153` | Multiple empty lines`1048` | Vendor-prefixed property without standard property`2` | Overqualified element`54` | Multiple statement in one line`456` | Use of outline:none`1`
 Low Total`17`| Empty line after{ `388` |    | Use of units of 0 value`16` |  Use of implied arithmetic operator precedence`400` |   
 Medium`8` | Empty line before} `360` |    |    | Type not in separate source file`55` |  
 Medium Total`5` |  Empty line at the end of file`252` |    |    | Unnecessary code`28` |  
 High Total`2` | Incorrect spacing around;`88` |    |   | Unnecessary ;`27` , Unused variable`13` |  
   \ | Empty line between chained statements`8` |    |    | Use readable conditions`7` |  
   \ | Empty line after documentation header`4` |    |   | Use of implied conditional operator precedence`2` |   
   \ | New line character in selector`1` |    |    | Multiple namespaces in source file`2` |  
   \ | Empty line at start of file`1` |    |    | Use of !important`1` |  
   \ |     |      |      | Use of read without -r`7` |   



