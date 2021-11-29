## 学习笔记

### Tictacoe
> 一字旗

疑问 
- dispaly:inline 默认baseline 对齐？  
- 三元表达式最佳实践
- let声明最佳实践
- 为啥要重新画一下
    - 如果不重新画多渲染多个cell

设计思路
- 先画出来
- 落子
- 判断是否赢了
- 初步的Ai，在快赢的时候提示
- 完美的Ai，怎么走才是最好的的选择
- 人机对战（机器走bestChoice）
- 换成1维数组试试

知识点
- 通过patter里面的数据的来渲染
- vertical-align 用在 inline, inline-block and table-cell elements， 默认baselline 对齐，
- 用1，2 代表你我方，用3来减就是对方，可以记录交替记录
- 用+=innerHtml的时候会把dom事件去掉
- for 循环 的标签语句：多层循环从内部直接跳转到外部循环
- 三元表达式最佳实践
- let声明最佳实践
- Tictaccoe 我们是递归全部的，很奢侈，因为它数据量不大，像真正的Ai都是有搜索深度的，不可能一下子搜索完
- 如果一开始走中间，对方走上下左右，肯定会输，走四个角一定会和
- 克隆用Object.create()比JSON序列化节省内存，但是只能保存一层数据

### 红绿灯 异步编程
> 红灯5秒，绿灯10秒，黄灯2秒，无限循环

疑问
- callback-hell 和 时间处理函数有啥关系？为啥时间处理函数处理红绿灯问题就是callback-hell了？
- async gennerator 是啥？
- for await of 是啥？

JavaScript 异步机制
- callBack
- Promise
    - 存在的意义是啥？比如红绿灯要换成手动的控制，如果用callback就会很麻烦，Promise就很简单，把事件单独抽离出来了
- Genereator
    - 诞生的时间略微早于Async/await，在没有Async之前，用yield来模拟，await，用同步的方式来写异步的代码，现在已经不推荐这样做了，早期人民的智慧
- Async/await
    - 是对Promise的支持和封装
    - 可以像同步代码一样去写异步代码



