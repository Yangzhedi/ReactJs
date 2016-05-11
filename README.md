# ReactjsDemo

最近在公司用react，心血来潮总结些工作中的demo，毕竟第一次写工程代码，心里还有些小激动呢~     ---2016/5/9

三组件互斥:https://github.com/Yangzhedi/ReactjsDemo/blob/master/%E4%B8%89%E7%BB%84%E4%BB%B6%E4%BA%92%E6%96%A5.html
就是在父组件中getInitialState设置三个子组件的mutexBoolean，
如果值为真，说明被选中，此组件可用；如果值为假，说明组件未被选中，上一次此组件的选择情况被清空，只保留值为真的组件选择情况。
然后再通过子组件每个input元素的点击事件调用父组件里的handleCheck函数来setState改变mutexBoolean。
改变mutexBoolean了之后，在componentWillReceiveProps和componentDidMount中调用每个子组件自有的checkedOrUn函数来设置每个子组件的checked属性。
从而达到控制三个组件之间互斥的关系。
因为demo中的input比较少，如果很多的话可以用事件代理来添加onChange事件。
