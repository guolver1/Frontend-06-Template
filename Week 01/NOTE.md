#学习笔记
##1. TicTacToe
- **text-align: center;** 水平居中
- 合适的**line-height** 垂直居中,影响的是行高
###元素垂直居中
- **vertical-align:baseline**是以文字基线为准对齐的<br />**vertical-align:middle**就不存在元素的留白问题了
###一维数组的clone
Object.create()
##2.异步编程
###三种异步处理机制
- callback  ——可能导致callback hell，嵌套
- Promise  ——链式表达式的方式<br />
（1）Promise.all 同时等待多个Promise<br />
（2）Promise.race竞争关系，并行执行，一个回来了就结束
- async/await (基于Promise)<br/>
可以等待Promise的结束


