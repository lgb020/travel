# travel
一个基于Vue全家桶的简单旅游app

基于Vue(2.5) + vuex + vue-router + vue-axios + better-scroll + stylus + ES6 等开发的一款旅游 WebApp, UI参照去哪网旅行，REM适配常见移动端。

## 预览
动态图片加载会有点慢，请耐心等待...  

![首页](https://anqwjoe.github.io/travel/show/%E9%A6%96%E9%A1%B5.gif)
![城市列表](https://anqwjoe.github.io/travel/show/%E5%9F%8E%E5%B8%82%E5%88%97%E8%A1%A8.gif)
![景点详情](https://anqwjoe.github.io/travel/show/%E6%99%AF%E7%82%B9%E8%AF%A6%E6%83%85.gif)

#### 首页、菜单、推荐

![75AhX.jpg](https://s1.ax2x.com/2018/05/28/75AhX.jpg)
![751my.jpg](https://s1.ax2x.com/2018/05/28/751my.jpg)

#### 城市列表、搜索页面

![75NpB.jpg](https://s1.ax2x.com/2018/05/28/75NpB.jpg)
![75IDJ.jpg](https://s1.ax2x.com/2018/05/28/75IDJ.jpg)
![75tNl.jpg](https://s1.ax2x.com/2018/05/28/75tNl.jpg)

#### 景点详情、用户评论、轮播展示

![75Sd3.jpg](https://s1.ax2x.com/2018/05/28/75Sd3.jpg)
![75frK.jpg](https://s1.ax2x.com/2018/05/28/75frK.jpg)
![75ixG.jpg](https://s1.ax2x.com/2018/05/28/75ixG.jpg)
![75lop.jpg](https://s1.ax2x.com/2018/05/28/75lop.jpg)

## 开发目的
通过学习开发一个 基于Vue 全家桶简单项目，让自己更熟练的使用 Vue 全家桶、模块化开发、ES6 等等知识，提高自己的技术能力。

## 技术栈
> Vue：用于构建用户界面的 MVVM 框架

> vue-cli 是vue的脚手架工具，目录结构、本地调试、代码部署、热加载、单元测试。

> vue-router：为单页面应用提供的路由系统，使用了 Lazy Loading Routes 技术来实现异步加载优化性能

> vue-axios：服务器通讯，请求数据

> vuex：Vue 集中状态管理，在多个组件共享某些状态时非常便捷

> better-scroll：解决移动端各种滚动场景需求的插件，使移动端滑动体验更加流畅

> stylus：css 预编译处理器

> ES6：ECMAScript 新一代语法，模块化、解构赋值、Promise、Class 等方法非常好用

#### 工具

> iconfont ：阿里巴巴图标库

> fastclick ：消除 click 移动游览器 300ms 的延迟

> swiper awesome : 实现轮播滚动及列表拖动效果

## 实现功能

#### 首页

轮播图、图标菜单基于 ```swiper awesome``` 实现滚动拖动；

热销推荐及周末去哪模块的文字图片数据均使用 ```axios``` 获取自己模拟的数据

#### 城市选择
点击首页右上角进入城市选择，该页面使用了```better-scroll```模仿原生APP的拖动效果；

可在搜索框中直接输入拼音、汉字均可搜索，点击地点可直接切换至首页，使用了```localStorage``` 本地保存数据；

右侧字母分类点击或拖动可直达该首字母城市。

#### 景点详情页面

使用Vuex 进行了组件间的数据联动。景点画廊，评论图片使用 ```swiper awesome``` 实现 
菜单拖动的渐隐渐显，及CSS3过渡动画的结合使用等。


## 在开发过程中遇到的一些困难及解决方案

**1. 执行```npm start```弹出 ```stylus``` 报错的问题**

原因：package.json 缺失依赖，不能解析stylus

解决方法：执行 npm install stylus-loader css-loader style-loader --save

**2. 加载后无法滚动 ，刷新后可滚动**


情况一：当数据是动态渲染时，在没有渲染出来的情况会视为scollBox的高度为0，因此要在渲染完成后执行 better-scroll的refresh 操作。因为此时高度因为新数据发生改变，需要重置 better-scroll 

解决方法：

```
  this.$nextTick(()=>{
      if (!this.scroll) {
        this.scroll = new BScroll(this.$refs.rongqi, {
          click: true
        });
      } else {
        this.scroll.refresh();
      };
    });
```

情况二：以PC模式打开页面，按F12后切换移动端无法滚动。

解决方法：切换移动端后，按F5 以移动端模式重新加载即可。


**3. 每次切换路由时，Ajax 都会发送请求**

解决方法： 在App.vue 文件的 <router-view>标签外包裹一层 <keep-alive> ，下次请求时会将已存储的内容从内存中取出即可，实质是不再执行mounted 周期函数

**4. 拖动页面会互相影响其他页面的位置，解决滚动行为**

解决方法：参考https://router.vuejs.org/zh/guide/advanced/scroll-behavior.html

在router/index.js 文件中 routes内添加
```
scrollBehavior (to, from, savedPosition) {
  return { x: 0, y: 0 }
}
```
作用：每一次做页面切换时，让先进入的页面X轴为0 Y轴也为0，（始终回到最顶部）

**5. 打包后运行 index.html 网页一片空白**

解决方法：修改 config 文件夹下的index.js
设置assetsPublicPath: './'


# Build Setup

```
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build
```
