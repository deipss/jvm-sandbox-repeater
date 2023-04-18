# 源码阅读
## repeater-aide
> 用于对象比对的辅助代码
## repeater-client
> 将spring中应用上下文进行引用复制，保存在自定义的SpringContextContainer对象中
## repeater-console-service
> 提供回放记录的查询、保存、回放功能
## repeater-console-start
> 对repeater-console-service中的接口进行调用，提供对外的web接口
## repeater-module
- 实现对jvm-sandbox的扩展
- 心跳的上报
- spring初始化拦截器，agent启动模式下拦截记录beanNameDefa和bean，用作回放
- 回放时，路由的隔离
    - com.alibaba.jvm.sandbox.repeater.module.classloader.PluginClassRouting
- jar文件的循环依赖检查
- module的加载
    - com.alibaba.jvm.sandbox.repeater.module.RepeaterModule
## repeater-plugin-api
- 定义本地回放的domain类
- 定义 invocation 录制的行为接口，如上报
- 定义 invocation 的 domain 类
    - com.alibaba.jvm.sandbox.repeater.plugin.domain.RepeaterConfig 基础配置项
- 定义 invocation 插装的一些配置
## repeater-plugin-core
- 被录制数据的上报
- 定时查询上报数据的规则
- 本地回放时，类的加载路由
    - com.alibaba.jvm.sandbox.repeater.plugin.core.impl.AbstractInvokePluginAdapter
- 上报数据的装配
    - ApacheHttpClientListenerEventListener
## repeater-plugins
> 各类组件的实现