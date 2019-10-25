# vue-sprite
vue端应用雪碧图配置汇总 vue2.0 vue-cli 2.+ webpack
##  webpack插件  webpack-spritesmith
* step1: 安装插件    npm i webpack-spritesmith

* step2: 配置webpack   在webpack.base.conf.js中 引入插件 const WebpackSpritesmithPlugin = require('webpack-spritesmith')
```js
plugins: [
    new WebpackSpritesmithPlugin({
      src: {
        cwd: path.join(__dirname, '../src/assets/img/icon'), // 目标路径
        glob: '*.png' // 匹配图片格式
      },
      target: {
        image: path.join(__dirname, '../src/assets/sprites/sprite.png'), 生成雪碧图的存放地址
        css: path.join(__dirname, '../src/assets/sprites/sprites.css')
      },
      apiOptions: {
        cssImageRef: './sprite.png' background: url地址
      },
      spritesmithOptions: {
        algorithm: 'top-down',
        padding: 5
      }
    })
  ],
