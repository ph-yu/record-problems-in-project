## 1. cmd命令行中yarn、live-server报错：不是内部或外部命令，也不是可运行的程序。
> 问题过程：
> 1. nodejs和npm版本没问题，在cmd中输入 `node -v` 和 `npm -v`  
> ![image](https://user-images.githubusercontent.com/30620472/228486934-7c4d3a65-bf1f-4f69-96ca-a502db3ed6eb.png)  
> 系统环境变量也设置了  
> ![image](https://user-images.githubusercontent.com/30620472/228488645-c33c4444-ffdf-4a8f-a721-0146220a8670.png)
> 2. 发现npm文件夹下是空的，路径：`C:\Users\Administrator\AppData\Roaming\npm`，真正有用的应该是这样  
> ![image](https://user-images.githubusercontent.com/30620472/228489618-3c9b1c2a-48be-4878-954a-17bba8e670f2.png)  
> 无论我执行多少次`npm install -g`都没有用，这些包都被安装到了`C:\Program Files\nodejs\node_global\node_modules`  
> 参考链接1：[关于npm prefix](https://qa.1r1g.com/sf/ask/2275850811/)  
> 参考链接2：[修改 npm 全局包的默认安装路径](https://zhuanlan.zhihu.com/p/469626943)  



## 2. vite+vue3项目中使用tailwindcss未生效的问题
1. 入口文件引入
> 
     @tailwind base; 
     @tailwind components;
     @tailwind utilities;

2. tailwind.config.js文件中
>
     module.exports = {
      content: ['./index.html', './src/**/*.{vue, js, jsx, ts, tsx}']
     }
  
 **要把vue格式的文件配置进去**，否则vue文件中是不会引入tailwindcss的
  
