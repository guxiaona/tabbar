# tabbar

> A Vue.js project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```
## tabbar组件实现

### 1.实现方法
自定义MainTabBar组件，在App中使用，设置相关的样式。
### 2.自定义TabBar
显示的内容由外界决定，定义插槽，flex布局平分TabBar。
### 3.自定义TabBarItem，传入图片和文字
定义TabBarItem，并且定义两个插槽：图片、文字。

给两个插槽外层包装div，用于设置样式。填充插槽。
### 4.TabBarItem绑定路由数据
安装路由
```
npm install vue-router —save
```
完成router/index.js的内容，以及创建对应的组件。

main.js中注册router。

App中加入组件。
### 5.传入点击之后的图片
定义另外一个插槽，插入active-item-icon的数据。

通过监听点击item跳转到对应路由，并且动态决定isActive。

监听item的点击，通过this.$router.replace()替换路由路径。
```
methods: {
    itemClick() {
      this.$router.replace(this.path);
    },
  },
```
通过v-if/v-else来决定显示对应的item-icon/active-item-icon。
通过封装新的计算属性来判断是否是active。
```
isActive() {
      return this.$route.path.indexOf(this.path) !== -1;
    },
```
封装新的计算属性动态计算active样式。
```
activeStyle() {
      return this.isActive ? { color: this.activeColor } : {};
    },
```

