---
title: react
date: 2018-06-01 16:48:25
tags:
---

### create-react-app 弹出配置文件
```bash
npm run eject
```

### 配置scss
```bash
首先将你的文件名称改成scss结尾的文件
然后安装依赖 npm install sass-loader node-sass --save-dev
找到webpack.config.dev.js文件和webpack.config.prod.js文件
将module配置项的最后一项配置改成如下
{
    loader: require.resolve('file-loader'),
    // Exclude `js` files to keep "css" loader working as it injects
    // it's runtime that would otherwise processed through "file" loader.
    // Also exclude `html` and `json` extensions so they get processed
    // by webpacks internal loaders.
    exclude: [/\.js$/, /\.html$/, /\.json$/,/\.scss$/],
    options: {
         name: 'static/media/[name].[hash:8].[ext]',
    },
},
{
    test: /\.scss$/,
    loaders: ['style-loader', 'css-loader', 'sass-loader'],
}
到此，配置完毕，记得两个文件都要改
```