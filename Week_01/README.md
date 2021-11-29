## 学习笔记
### 疑问
- dispaly:inline 默认baseline 对齐？
- 三元表达式最佳实践
- 为啥要重新画一下
- 

### Tictacoe
> 一字旗

设计思路
- 先画出来
- 落子
- 判断是否赢了
- 初步的ai预测，在快赢的时候提示

要点
- 通过patter里面的数据的来渲染
- vertical-align 用在 inline, inline-block and table-cell elements， 默认baselline 对齐，
- 用1，2 代表你我方，用3来减就是对方，可以记录交替记录
- 用+=innerHtml的时候会把dom事件去掉
- for 循环 的标签语句：多层循环从内部直接跳转到外部循环
