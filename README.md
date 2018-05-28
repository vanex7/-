# unnamed
这个仓库是用来存放一些临时或者一直不知道答案或者原理的问题，这些问题是在做程序开发过程中，或者其浏览其他博客的过程中发现的。
现在把他们记录下来，只是为了让自己能够走得快一些。
另外，也会有写一些关于职业的东西吧。

最后说下为什么用readme写，因为博客广告太多，看得太累，记事本只能本地看，究极原因是这个有逼格，能看diff（这难道不是最佳理由吗？）
这个文件理论上是不会分页的，想写什么写什么
偶尔中英文混杂，随意吧

### 1.What's JIT [ref](http://blog.reverberate.org/2012/12/hello-jit-world-joy-of-simple-jits.html)
### 2.Why JIT does't work on iOS
### 3.在Cocos-lua中的class是怎么实现通过.new方法可以创建多个实例的? [answer](/answer/%233.md)
### 4.What's means 'Context' in program? [answer](/answer/%234.md)
### 5.In url %23 == \#
### 6.是否可以有这样一个表示方式： 2^0 2^1 2^2 2^3 分别表示4中通道， 给定一个方法， 这个方法接受所有可通过通道的可能性的综合，并且通过输入的值分析并且打印出。
```lua
local m = {}
m.enum = {one = 2^0, two = 2^1, three = 2^3}

function m:test(value)
  --[[
    期望这里输出value 所对应的若干个enum值
    比如这个value是由几个 n个one + n个two + n个three 组成的 （n==0 or n==1）
  ]]
end

-- test
m:test(m.enum.one)
m:test(m.enum.one + m.enum.two)
m:test(m.enum.one + m.enum.three)
m:test(m.enum.one + m.enum.one) -- 可以暂不支持这样的
```


### 7.UDID Unique Device Identifier

### 8. MAC Media Access Control

### 9. Lua 中10进制，16进制互相转换（不考虑效率）
16 -> 10 print(string.format("%d", '0xf'));
10 -> 16 print(string.foramt("%x", '16'));
