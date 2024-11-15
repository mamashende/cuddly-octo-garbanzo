查询资料可知，对上下文切换进行测量牵扯到大量底层原理，而且由于目前广泛都是多核多任务并行，任务调度规则引起的上下文切换不归律，使得上下文切换测量干扰非常多

要满足如下条件：在操作系统只有两个不同的任务作为负载的情况下在单个CPU核心上运行才能实现准确测量

参考资料如下：
https://zhou-yuxin.github.io/articles/2018/%E4%BD%BF%E7%94%A8rdtsc%E6%8C%87%E4%BB%A4%E8%BF%9B%E8%A1%8C%E6%97%B6%E9%92%9F%E5%91%A8%E6%9C%9F%E7%BA%A7%E6%B5%8B%E9%87%8F/index.html

https://github.com/jzplp/OSTEP-Answers/blob/main/Chapter-6/Chapter-6-Homework-Answers.md
（并不是特别认可这个答案，但是又想不到更好的解释）