## 学习笔记
第四周：12.20-12.26

## 目录
- 1.html  字典树
- 2.thml  kmp 
- 3.html  
- 4.html 

## 字符串分析算法
> ll 和 正则前面都用过了，这节课主要学习 字典树，KMP，Willcard
- 字典树
    - 检查两个字符串是否完全匹配
    - 适用于大量高重复字符串的存储和分析,下面是字典树的数据结构
    ![图片](https://static01.imgkr.com/temp/aa9a9c2202cb4806abcbb1788fb04313.png)

    > [字典树，顾名思义，是关于“字典”的一棵树。即：它是对于字典的一种存储方式（所以是一种数据结构而不是算法）。这个词典中的每个“单词”就是从根节点出发一直到某一个目标节点的路径，路径中每条边的字母连起来就是一个单词](https://www.cnblogs.com/fusiwei/p/11972776.html)。
- KMP
    - 检查两个字符串是否部分匹配
    - 字符串中查找短字符串（模式）

    https://www.youtube.com/watch?v=dgPabAsTFa8  这个讲解的很好
    步骤
    - 写出所有的pat字符串前缀表  prfix table  
    - 计算最长公共前后缀（一定比当前字符串前缀表段）  
        - a b a b c（-1 0 0 1 2）
        - a a a a b(-1 0 1 2 3) 
            - a           0
            - a a         1   一定比当前字符串前缀表段小,所以不是2，下面一样
            - a a a       2
            - a a a a     3
            - a a a a b   0 
    ```
     let prefix = new Array(pattern.length).fill(0);
        let len = 0;
        let i = 1;
        while (i < pattern.length) {
            if (pattern[i] == pattern[len]) {
                len++;
                prefix[i] = len
                i++;
            } else {
                if (len > 0)
                    len = prefix[len - 1]
                else
                    // pre[i] = len;//这里估计可以去掉。因为一开始都填充0了
                    i++;
            }
        }
        console.log('prefix', prefix)
    ```
    - 最长公共前后缀调整，（最后一个不要，前面在 补个 -1，也是也可以看作每个字母往后移动一位，第一位补-1，代码实战2.html有个操作专门处理这块的）
    ```
     for (let i = 0; i < prefix.length; i++) {
            prefix[i] = prefix[i + 1]
        }
        prefix[0] = -1
    ```

- Wildcard
    - 包含通配符的字符串模式匹配
- 正则表达式
    - 字符串通用模式匹配
- 状态机
    - 通用的字符串分析
- LL/LR
    - 字符串多层次结构分析
