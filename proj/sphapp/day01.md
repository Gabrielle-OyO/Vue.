




初始化项目

C:\Repository\Vue\proj>vue create sphapp

Vue CLI v5.0.8
? Please pick a preset: Default ([Vue 2] babel, eslint)


Vue CLI v5.0.8
✨  Creating project in C:\Repository\Vue\proj\sphapp.
⚙️  Installing CLI plugins. This might take a while...


added 857 packages in 42s
🚀  Invoking generators...
📦  Installing additional dependencies...


added 92 packages in 8s
⚓  Running completion hooks...

📄
  Generating README.md...

🎉  Successfully created project sphapp.
👉  Get started with the following commands:

 $ cd sphapp
 $ npm run serve


C:\Repository\Vue\proj> cd sphapp

C:\Repository\Vue\proj\sphapp>npm run serve


 DONE  Compiled successfully in 9127ms                                                                          17:35:32


  App running at:
  - Local:   http://localhost:8080/
  - Network: http://10.66.98.213:8080/

  Note that the development build is not optimized.
  To create a production build, run npm run build.

  打开实时网页
  http://localhost:8080/

![image-20230306173945081](C:\Users\18377\AppData\Roaming\Typora\typora-user-images\image-20230306173945081.png)


1：vue-cli 脚手架初始化项目
node+webpack+淘宝镜像
node_modules文件夹：项目依赖文件夹
public：防止静态资源
src:源代码
    assets：多个组件公用的静态资源，在webpack打包时 会当作一个模块打包到js里
    components：非路由组件（全局组件）
    APP.vue：唯一的根组件
    main.js：程序入口组件

babell.config.js:配置文件（babel相关）
package.json文件：认为项目身份证，记录项目叫什么,项目中有哪些依赖、项目怎么运行
package-lock.json：缓存性文件

readme.md：说明


2.项目自动运行打开浏览器
  2.1更改---package.json文件以下内容 --open
    "scripts": {
      "serve": "vue-cli-service serve",
      "build": "vue-cli-service build",
      "lint": "vue-cli-service lint"
    },
    我修改了之后会报错 定位到 0.0.0.0:8080

  2.2关闭eslint校验功能
  声明变量未使用，可以关闭提示
  在文件vue.config.js下关闭eslint
  module.exports = {
  lintOnSave: false
}

  2.3 src文件夹简写方法，配置别名 @代表src文件夹,方便寻找
  "compilerOptions": {
    "target": "es5",
    "module": "esnext",
    "baseUrl": "./",
    "moduleResolution": "node",
    "paths": {
      "@/*": [
        "src/*"
      ]
    }
  },
  "exclude": [
    "node_modules",
    "dist"
  ]


3.项目路由分析
  vue-router
  前端路由：KV键值对
  key:URL(地址栏中的路径)
  value：相应的路由组件
  注意：项目上中下结构

  路由组件：
  Home首页组件、Search、login、refister组件
  非路由组件：
  Header（首页、搜索页）
  Footer（首页有，登录页没有）


4.完成非路由组件Header和Footer
  1静态页面书写
  2拆分组件
  3获取服务器数据动态展示
  4完成相应的动态业务逻辑

  注意：创建组件时： 组件结构+组件样式+图片资源
  注意：采用css还是less样式，浏览器不能识别less，需通过less less-loader进行处理less 把less样式换为css样式 浏览器才可以识别

  安装less：【@5版本】
  cnpm install --save less less-loader@6

  <!-- 
C:\Repository\Vue\proj\sphapp>cnpm install --save less less-loader@5
√ Linked 27 latest versions fallback to C:\Repository\Vue\proj\sphapp\node_modules\.store\node_modules
peerDependencies WARNING less-loader@5 requires a peer of less@^2.3.1 || ^3.0.0 but C:\Repository\Vue\proj\sphapp\node_modules\less was installed at less@4.1.3, packageDir: C:\Repository\Vue\proj\sphapp\node_modules\.store\less-loader@5.0.0\node_modules\less-loader
peerDependencies WARNING less-loader@5 requires a peer of webpack@^2.0.0 || ^3.0.0 || ^4.0.0 but C:\Repository\Vue\proj\sphapp\node_modules\webpack was installed at webpack@5.75.0, packageDir: C:\Repository\Vue\proj\sphapp\node_modules\.store\less-loader@5.0.0\node_modules\less-loader
√ Installed 2 packages on C:\Repository\Vue\proj\sphapp
√ All packages installed (27 packages installed from npm registry, used 3s(network 3s), speed 14.44KB/s, json 3(45.08KB), tarball 0B, manifests cache hit 24, etag hit 24 / miss 3)

dependencies:
+ less ^4.1.3
+ less-loader ^5.0.0
  
   -->

    注意：此时还是无法让组件识别less样式 需要在上腾娱乐标签上加lang=less
    <style scoped lang="less">

  4.1 使用组件的步骤（非路由组件）
  -创建或定义
  -引入
  -注册
  -使用

