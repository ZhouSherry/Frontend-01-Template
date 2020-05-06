# 每周总结可以写在这里
事件循环
事件循环机制：要想在线程运行过程中，能接受并执行新的任务，就要采用事件循环机制。

消息队列
消息队列是一种数据结构，可以存放要执行的任务。它符合队列“先进先出”的特点，也就是说要添加任务的话，添加到队列的尾部；要取出任务的话，从队列头部去取。

宏任务
渲染事件（如解析 DOM、计算布局、绘制）；
用户交互事件（如鼠标点击、滚动页面、放大缩小等）；
JavaScript 脚本执行事件；
网络请求完成、文件读写完成事件。
微任务
异步回调的执行时机是在主函数执行结束之后、当前宏任务结束之前执行回调函数，这通常都是以微任务形式体现的。

微任务就是一个需要异步执行的函数，执行时机是在主函数执行结束之后、当前宏任务结束之前。

宏任务&微任务执行顺序 实验代码
代码
async function afoo() {
    console.log("-2")


    await new Promise(resolve => resolve());
    console.log("-1")
}


new Promise(resolve => (console.log("0"), resolve()))
    .then(() => (
        console.log("1"),
        new Promise(resolve => resolve())
            .then(() => console.log("1.5"))));


setTimeout(function () {
    console.log("2");

    new Promise(resolve => resolve()).then(console.log("3"))


}, 0)
console.log("4");
console.log("5");
afoo();
解析：
第一个宏任务：
3
入队 4
8
9
1
入队 2
4
入队 5
2
5
第二个宏任务：
6
入队 7
7
与ECMAScript相关的章节
RunJobs（P.104）