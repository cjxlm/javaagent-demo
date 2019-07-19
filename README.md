# javaagent-demo  java agent技术应用 性能监控 极简 例子


javaagent是JDK1.5添加的一个新特性，使用javaagent可以实现很多类似线上诊断方面的工具，因为它可以在不改源代码的基础上，动态修改代码的行为。


#方案1： 在方法执行 第一行和最后一行打印时间戳 计算方法耗时<br>
优点：理解简单 实现容易<br>
缺点：代码侵入高 不用时候需要删除 注释  有点傻<br>



#方案2： AOP  所有方法切面 执行 executeBefore 和  executeAfter 统一加入管理<br>
优点： 代码侵入性较低  实现比较容易<br>
缺点： 需要每个应用引入jar包或SDK，不能够方便实时移除,推广起来困难,大规模集群管理困难。<br>

#方案3：  java agent技术  程序运行前 classloader提前加载探针，在探针程序中运行期 获取所有方法 在方法执行前后打点<br>
优点: 代码零侵入 随时使用或卸载 方便大规模集群升级维护<br>
缺点：实现较困难<br>


