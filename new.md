#### 一、安装node、npm、vue-cli脚手架
#### 二、新建命令：vue init webpack my-project
1. ? Project name (my-project)        ------------项目名称
2. ? Project description (A Vue.js project)        ------------项目描述
3. Author (loktar <******@gmail.com>)        ------------项目创建者
4. ? Install vue-router? (Y/n)        ------------Yes
5. ? Use ESLint to lint your code? (Y/n)        ------------是否启用eslint检测规则
6. ? Set up unit tests (Y/n)        ------------是否安装单元测试
7. Setup e2e tests with Nightwatch? (Y/n)        ------------是否设置e2e测试
8. Should we run `npm install` for you after the project has been created? (recommended)        ------------是否需要运行"npm install"
9. $ cd my-project         ------------进入项目
10. $ npm install         ------------安装依赖
11. $ npm run dev         ------------项目运行
#### 三、设置网页title小图标
1. 将favicon.ico放到static文件夹下，在index.html中加入
```
<link rel="icon" href="./static/favicon.ico" type="image/x-icon">
```
2. 在build/webpack.dev.conf.js
```
new HtmlWebpackPlugin({
  filename: 'index.html',
  template: 'index.html',
  inject: true,
  favicon: path.resolve('favicon.ico')   // 加上这个
})
```
#### 四、使用sass
1. 运行命令 `$ npm install sass-loader node-sass vue-style-loader --D`
2. 打开build文件夹下面的webpack.base.config.js文件，在module理添加：
```
{ 
  test: /\.scss$/,
  loaders: ["style", "css", "sass"]
}
```
3. 使用：
```
<style lang="scss">
  $color: #333;
</style>
```
