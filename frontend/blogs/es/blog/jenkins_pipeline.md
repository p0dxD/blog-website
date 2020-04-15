---
name: 'jenkins_pipeline'
title: Creando un Jenkins Enterprise pipeline
author: Jose Rodriguez
date: Abril 09 2020
id: 'jenkins_pipeline'
description: |
  En este tutorial demuestro la manera de como crear un pipeline simple que se puede usar en proyectors personales o extendido de manera que puede ser usado en corporaciones. Se mantiene en conciencia la seguridad, extensibilidad y la simplicidad. 
---

1. [ Description. ](#desc)
2. [ Usage tips. ](#usage)

<a name="desc"></a>
## 1. Descripcion

Algun texto

<a name="usage"></a>
## 2. Como usarse

```javascript
module.exports = {
  chainWebpack(config){
    config.module.rule('md')
      .test(/\.md/)
      .use('vue-loader')
      .loader('vue-loader')
      .end()
      .use('vue-markdown-loader')
      .loader('vue-markdown-loader/lib/markdown-compiler')
      .options({
        raw: true
      })
  }
}
```