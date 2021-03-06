### 笔试题
> Q：如何将纯文本转换成二维数组？
> 
> 文本数据：aaa bbb ccc ddd eee fff ggg hhh iii jjj kkk lll
> 
> 转换结果：
> aaa | bbb | ccc | ddd
>  -- | :--:| :--:| --:
> eee | fff | ggg | hhh
> iii | jjj | kkk | lll

> Q：如何实现table中的td异步添加，点击td时输出td中的内容？
>
> A：事件代理

> Q：原码／反码／补码 的含义和转换规则

> Q：实现一个Event类，包含 on, off, trigger, once 方法

> Q：Function.prototype.bind 函数实现

> Q：页面有：header，body，footer 三部分。header始终固定在顶部；当页面高度不够时，footer固定在页面底部；页面有滚动条时，footer在body下面且不固定。

> Q：格式化 1234567890.12 成：1，234，567，890.12。使用正则和非正则方式。
>
> A: 非正则：toLocalString

> Q：编程题：格式化时间戳。可扩展性强

### 面试题
> Q：React diff 算法以及diff算法会出现的问题

> Q：React组件设置key的作用

> Q：redux异步请求方案和原理：redux-thunk/redux-promise/redux-saga

> Q：http2.0 新特性介绍

> Q：http2.0比http1.x优势

> Q：nodeJs事件循环

> Q：函数柯里化：实现函数fn
>
> fn(1)(2)(3) -> 6
>
> fn([1,2])(3) -> 6
***
> Q：浏览器缓存相关：强缓存和协商缓存区别？主资源和派生资源有哪些？内存和磁盘中缓存的资源类型？内存缓存过期时间？
>
> 主资源：页面和下载的文件；派生资源：图片/样式/JS/字体。
> JS/字体/解码过后的图片缓存在内存中(需要重复执行)，css和未解码的图片缓存在磁盘中。
> 内存缓存中的内容缓存在进程中，关闭窗口就会释放，下次访问会先从磁盘中取，然后将其缓存在内存中。

> Q：模块化规范有哪些？
>
> A：CommonJS/AMD/CDM/ESModule

> Q：import和require的区别
> 
> A：import时编译时加载，require时运行时加载

> Q：webpack中hash种类以及各自的作用

> Q：用React封装一个通用 Text 组件，需要考虑那些细节

> Q：封装一个通用表单验证组件，使用策略模式
>
> ```
> validator.add(registerForm.userName, [{
>   strategy:’isNotEmpty’,
>   errorMsg:’用户名不能为空’
> }，{
>   strategy: 'minLength:6',
>   errorMsg:'用户名长度不能小于6位'
> }])
> validator.validate()
> // 检验不通过时输出错误信息
> ```

> Q：实现一个调度器：Scheduler。实现如下功能
> ```
> // 一开始，1、2两个任务进入执行
> // 500ms时，2完成，输出2，任务3进队
> // 800ms时，3完成，输出3，任务4进队
> // 1000ms时，1完成，输出1
> // 1200ms时，4完成，输出4
> const scheduler = new Scheduler(2)
> const timeout = (time) => new Promise(resolve => {
>   setTimeout(resolve, time)
> })
> const addTask = (time, order) => {
>    scheduler.add(() => timeout(time)).then(() => console.log(order));
> }
> addTask(1000, '1')
> addTask(500, '2')
> addTask(300, '3')
> addTask(400, '4')
> // output: 2 3 1 4
> ```