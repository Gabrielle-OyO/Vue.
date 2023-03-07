




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

📄  Generating README.md...

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

