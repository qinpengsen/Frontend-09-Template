## 学习笔记
第三周：12.13-12.19

## 目录
- 1.html  词法分析器实战代码
- 2.thml  词法分析器可以循环,完成异步的形式，yield
- 3.html  语法分析 - 乘法
- 4.html  语法分析 - 四则运算, 模拟代码执行过程，先分词，在构造成树形结构，最后解析执行。

## 背景
- 学习对字符串的处理，之前都是低级处理，现在学习编译原理里面的高级处理
## 知识点
**代码执行过程**
- 计算机对代码先分词，然后把分的词 根据语法定义 变成树形结构（AST），最后解析执行树形结构。

**AST**
- AST 抽象语法树，构建抽象语法树的过程又叫做语法分析

**语法分析算法**
- llr 算法，词法分析的另一种算法
- ll  （left left 算法）  从左到右扫描，从左到右规并，用的这个算法

**token**
- 有意义的输入，空格换行等不是token

## 四则运算 - 实战

**词法定义**
下面这就是词法分析
- TokenNumber: 1 2 3 4 5 6 7 8 9 0 . 的组合
- Operator:+ - * / 之一
- Whitespace:<sp>
- LinTeminator:<lf><cr>

**语法定义**
> 下面使用产生式来定义的语法，EOF （End of file） 表示终结的场景
- Terminalsymbol 终结符，直接从词法里面扫描出来的，就是上面定义的词法，比如 下面的number 和 Operetor
- Noneterminalsymbo 非终结符，由终结符组成，需要进步分析成终结符

```
表达式
<Expression>::
<AdditiveExpression><EOF>

加法
<AdditiveExpression>::<MultiplicativeExpression>｜
<AdditiveExpression><+><MultiplicativeExpression>｜<AdditiveExpression<-><MultiplicativeExpression>

乘法
<MultiplicativeExpression>::<Number>｜
<MultiplicativeExpression><*><Number>｜<MultiplicativeExpression></><Number>
```

