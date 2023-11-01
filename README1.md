# pdf-mozilla

### 使用 mozilla 的 pdfjs 构建版本

所以不需要安装任何东西，整个构建版本的包大约在16M左右，但实际使用时，首次需要加载的资源大概在2M左右

![](/src/assets/pdf_1.png)
![](/src/assets/pdf_2.png)


### 迁出方式

- 将 `public/pdfjs` 文件夹整体放到项目中
- 前端组件位置 `src/components/pdfMoz.vue`
- 使用参照 `src/views/HomeView.vue`


### 需要注意的是 `src/components/pdfMoz.vue` 中

```js
data () {
  return {
    baseUrl: 'pdfjs/web/viewer.html?',
    fullPath: 'pdfjs/web/viewer.html'
  }
},

// 这里的两个路径跟随项目而定 （前面要不要加 /, 或者 /项目部署路径/ 等）
```