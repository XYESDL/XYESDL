# 前端开发

## Node

pnpm
```vue
阿里镜像源
pnpm config set registry https://registry.npmmirror.com/
```

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