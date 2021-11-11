#### 一、main.ts

1.注册了一个全局格式化的时间组件，然后就可以用$filters来调用

2.注册vuex的store ，有2个初始值的变量

3.setupStore()初始化store数据

4.注册router，在router的index中路由守卫，拿不到token都去login页面

5.注册ElementPlus配置国际化



#### 二、login.vue

login.vue包含了3个登录相关的页面组件login-panel,login-account,login-phone.

1.login-panel中点击登录，调用login-account的loginAction方法，loginAction又调用vuex的login/accoutLoginActuon方法

参数就是账户密码。

2.accoutLoginActuon登录逻辑

- 请求后台登录accountLoginRequest，成功返回token，本地缓存一份token，store里存一份token
- 请求以后使用的下拉框数据，entireDepartment，entireRole，entireMenu
- 请求用户信息userInfo
- 根据role的id请求菜单信息userMenus     ？？？？？？？？？？？？？
- 跳转到首页main











