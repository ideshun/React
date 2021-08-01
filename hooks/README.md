# Hooks

### React Hook/Hooks是什么?

1. Hook是 React 16.8.0 版本增加的新特性/新语法
2. 可以让你在函数组件中使用 state 以及其他的 React 特性

### 三个常用的Hook

1. State Hook：`React.useState()`
2. Effect Hook：`React.useEffect()`
3. Ref Hook：`React.useRef()`

### State Hook

State Hook 让函数组件也可以有 state 状态，并进行状态数据的读写操作

#### 语法：

```
const [xxx, setXxx] = React.useState(initValue)
```

#### 参数：

第一次初始化指定的值在内部作缓存

#### 返回值：

包含2个元素的数组，第1个为内部当前状态值，第2个为更新状态值的函数

#### 2种写法：

`setXxx(newValue)`：参数为非函数值，直接指定新的状态值，内部用其覆盖原来的状态值
`setXxx(value => newValue)`：参数为函数，接收原本的状态值，返回新的状态值，内部用其覆盖原来的状态值

### Effect Hook

Effect Hook 可以让你在函数组件中执行副作用操作（用于模拟类组件中的生命周期钩子）

#### React 中的副作用操作/应用场景：

1. 发 ajax 请求数据获取
2. 设置订阅 / 启动定时器
3. 手动更改真实DOM

#### 语法和说明：

```
useEffect(() => { 
  // 在此可以执行任何带副作用操作
  return () => { // 在组件卸载前执行
    // 在此做一些收尾工作, 比如清除定时器/取消订阅等
  }
}, [stateValue]) // 如果指定的是[], 回调函数只会在第一次render()后执行
```

#### 可以把 useEffect Hook 看做如下三个函数的组合：

```
componentDidMount()
componentDidUpdate()
componentWillUnmount() 
```

### Ref Hook

Ref Hook 可以在函数组件中存储/查找组件内的标签或任意其它数据

#### 语法：

```
const refContainer = useRef()
```

#### 作用：

保存标签对象，功能与 `React.createRef()` 一样