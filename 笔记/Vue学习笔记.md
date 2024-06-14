# Vue学习

## 属性

1. v-bind 绑定数据
2. v-on  监听事件
3. v-model 双向绑定  `<input v-model="text" placeholder="helloworld">`
4. `v-if` 指令来有条件地渲染元素
5. v-for `<ul>  <li v-for="todo in todos" :key="todo.id">    {{ todo.text }}  </li> </ul>`
6. Computed

## Props

组件暴露属性给外部，类似于C#中的属性

`<Script>export default { props : { msg : String}}</Script>`

## Emits 

组件暴露事件给外部，类似于C#中的事件

`<script>export default {emits:['response']} created(){this.$emit ('response', 'hello from child')}</script>`

## Slots

除了通过 props 传递数据外，父组件还可以通过**插槽** (slots) 将模板片段传递给子组件：

## 监听事件

v-on 或者 @click

`<button v-on:click="handleMethod"/>  <button @click="handleMethod"/>` 



ref 被用来给元素或子组件注册引用信息， 引用信息将会注册在父组件的 $refs 对象上，如果是在普通的DOM元素上使用，引用指向的就是 DOM 元素，如果是在子组件上，引用就指向组件的实例。

$refs 是一个对象，持有已注册过 ref 的所有的子组件

## 文件作用

1. project/index.html  index.html 是该 Vite 项目的入口文件
2. project/src/main.js  是项目的入口文件，初始化 vue 实例，并引入所需要的插件。
3. project/src/App.vue  是项目的主组件，所有页面都是在该组件下进行切换的

## 单文件组件

一个vue文件就是一个单文件组件

## API风格

1. 选项式API  选项式 API 以“组件实例”的概念为中心 (即上述例子中的 `this`)
2. 组合式API  组合式 API 的核心思想是直接在函数作用域内定义响应式状态变量
