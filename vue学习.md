### 声明式渲染
```html
<div id="app">
    {{ message }}
</div>
var app = new Vue({
  el: '#app',
  data: {
    message: 'Hello Vue!'
  }
})
```
上面是一个简单到vue应用,div标签到内容与app.message到值绑定，通过修改app.message的值修改div标签的内容
```html
<div id="app">
  <span v-bind:title="message">
    鼠标悬停几秒钟查看此处动态绑定的提示信息！
  </span>
</div>
var app = new Vue({
  el: '#app',
  data: {
    message: '页面加载于 ' + new Date().toLocaleString()
  }
})
```
通过v-bind 绑定html标签到属性，通过修改app.message的值来修改绑定到html标签的属性值
### 循环和条件
```html
<div id="app">
  <p v-if="seen">现在你看到我了</p>
</div>
var app = new Vue({
  el: '#app',
  data: {
    seen: true
  }
})
```
通过v-if来控制html的结构是否显示
```html
<div id="app-4">
  <ol>
    <li v-for="todo in todos">
      {{ todo.text }}
    </li>
  </ol>
</div>
var app4 = new Vue({
  el: '#app-4',
  data: {
    todos: [
      { text: '学习 JavaScript' },
      { text: '学习 Vue' },
      { text: '整个牛项目' }
    ]
  }
})
```
通过v-for来快速对列表数据进行渲染
### 监听事件