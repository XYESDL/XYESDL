# 表格数据请求
  后端配置数据库、开放响应接口
  前端配置跨域、生成请求接口、组件中导入调用接口

## 钩子函数
  onMounted 钩子，组件挂载后获取数据
  computed 是一个计算属性
  数据查找过滤:前端过滤、后端过滤

## 组件注册
```vue
  在使用<script setup>语法，不需要显式注册组件
  export const deletet = (id: number ) => {
    return http.request<any>("delete", baseUrlApi(`deletetable/${id}`));      //使用``反引号插值
  };
```

# 前端新建组件
  src/views/新建文件夹/index.vue组件，设置name名称
  router/modules/组件.ts 配置信息

# 前端请求方法
  src/api新建并导出请求方法
  views组件中导入使用方法

# node.js后端新建响应请求过程
  router/http.ts内新建对应请求响应方法，导出方法
  server.ts内引入方法，监听客户端请求处理


## 事件定义
  使用 function 关键字声明一个函数（如 function pcon() {...}）时，此函数会被定义在“函数作用域”内。这意味着它在整个脚本模块中任何地方都是可见的，即使它在代码中的后面被声明。
  使用 const 与箭头函数（如 const pcon = () => {...}）来声明，会将该函数定义在“块作用域”内。箭头函数还有其他几个特性，例如它不绑定自己的 this，它会捕获其创建时所处上下文的 this 值。

##### 





























# 全局构想


## 表格
    表格包含所有数据（产品、数量、图片、价格、官网链接）
    添加、删除、修改、导入、导出
    表格生成（数据快速选择、可自定义添加、）、导出到指定模板、

## 控制
    所有电脑开机
    tcp、udp设备自定义可控（音视频）