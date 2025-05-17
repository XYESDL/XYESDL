# 前端开发

## [Node](https://nodejs.org/zh-cn)

### [pnpm](https://pnpm.io/zh/)

设置阿里镜像源
```vue
pnpm config set registry https://registry.npmmirror.com/
```

## Vue3

### 表格数据请求

```vue
  后端配置数据库、开放响应接口
  前端配置跨域、生成请求接口、组件中导入调用接口
  ```

### 钩子函数

```vue
  onMounted 钩子，组件挂载后获取数据
  computed 是一个计算属性
  数据查找过滤:前端过滤、后端过滤
```

### 组件注册

### 生命周期



## Midway框架

### 

```vue
  Controller（控制器）
    处理HTTP请求，是API接口的入口
    接收前端请求参数
    调用Service层处理业务逻辑
    返回处理结果给前端

  Entity（实体）
    定义数据库表结构，映射数据库表
    定义表字段及其类型
    设置字段的验证规则
    定义字段的默认值
    配置字段的索引

  Service（服务）
    处理业务逻辑
    处理数据验证
    调用数据库操作
    处理事务
```
