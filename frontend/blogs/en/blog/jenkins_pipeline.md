---
name: 'jenkins_pipeline'
title: Creating Jenkins Enterprise pipeline
author: Jose Rodriguez
date: April 09 2020
id: 'jenkins_pipeline'
description: |
  In this walkthrough I will go over what is necesary to create a simple pipeline that can be used for personal projects or extended for enterprises keeping in mind security, extensivility and simplicity. 
---

1. [ Description. ](#desc)
2. [ Usage tips. ](#usage)

<a name="desc"></a>
## 1. Description

sometext

<a name="usage"></a>
## 2. Usage tips

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