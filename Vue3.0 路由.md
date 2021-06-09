# 三种模式
## 1、hash模式
（vue-router默认模式URL后面带#）使用URL的hash值来作为路由，支持所有浏览器 缺点：只能改变#后面的来实现路由跳转。

```
const router = createRouter({
  history: createWebHashHistory(),
  routes
})
```
## 2、history模式
（通过mode: 'history’来改变为history模式）HTML5 （BOM）History API 和服务器配置 缺点：怕刷新如果后端没有处理这个情况的时候前端刷新就是实实在在的请求服务器这样消耗的时间很多还很慢。

```
const router = createRouter({
  history: createWebHistory("admin"),
  routes
})
```
## 3、abstract模式
适用于所有JavaScript环境，例如服务器端使用Node.js。如果没有浏览器API，路由器将自动被强制进入此模式。

```
const router = createRouter({
  history: createMemoryHistory(process.env.BASE_URL),
  routes
})
```
![image](https://user-images.githubusercontent.com/7861157/121335088-ddc05900-c94c-11eb-914f-2cabd5de7206.png)
