#第1章 React简介

- React在每次请求后都会重新渲染整个页面

#第2章 JSX
    
- 子节点：React将开始标签和结束标签之间的所有子节点保存在this.props.children中.
- 非DOM属性：key, ref, dangerouslySetInnerHTML
	- ref: 允许父组件在render方法之外保持对子组件的一个引用
		```
		render: function () {
			return <div>
				<input ref="myInput" ..../>
			</div>;
		}
		```
		
		然后可以在组件的任何地方使用this.refs.myInput获取引用.

#第3章 组件的生命周期(P23)
	
- 实例化：
	- getDefaultProps
	- getInitialState
	
		每次创建实例时调用一次
	- componentWillMount
		
		在render方法调用之前最后一个可以修改state的方法
	- render
		- 只能通过this.props和this.state访问数据
		- 可以返回null、false或者任何React组件
		- 只能出现一个顶级组件(不能返回一组元素)
		- 不能改变组件的状态或者修改DOM的输出
	- componentDidMount
- 存在期：
	- componentWillReceiveProps
	- shouldComponentUpdate
	- componentWillUpdate
	- render
	- componentDidUpdate
- 销毁&清理期
	- componentWillUnmount