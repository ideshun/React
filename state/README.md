<!--
 * @Author: Deshun
 * @Date: 2021-07-30 17:29:34
 * @LastEditors: Deshun
 * @LastEditTime: 2021-07-30 17:44:11
 * @FilePath: \Study&Code\state\README.md
 * @Description: state 属性知识点
-->

## 理解
1. `state` 是组件对象最重要的属性，值是对象（可以包含多个 `key-value` 的组合）
2. 组件被称为"状态机”，通过更新组件的 `state` 来更新对应的页面显示（重新渲染组件）

## 注意
1. 组件中 `render` 方法中的 `this` 为组件实例对象
2. 组件自定义的方法中 `this` 为 `undefined` ，如何解决？
    1. 强制绑定 `this` ：通过函数对象的 `bind()`
    2. 箭头函数
3. 状态数据，不能直接修改或更新
