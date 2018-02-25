# search

[![GPL-3.0](https://img.shields.io/badge/license-GPL--3.0-blue.svg)](LICENSE)
[![Build Status](https://travis-ci.org/game-helper/search.svg?branch=master)](https://travis-ci.org/game-helper/search)

基于搜索引擎的问答匹配度查询，暂时只使用了百度搜索

> 目前用于 [game-helper/weixin](https://github.com/game-helper/weixin) 答题类辅助没有正确答案时，提交匹配度最高的选项

## 安装

```bash
npm i game-helper/search
```

## 示例

```js
const search = require('search')

;(async () => {
  const {result, maxIndex} = await search({
    question: '《红楼梦》的作者是谁？',
    options: [
      '施耐庵',
      '吴承恩',
      '曹雪芹',
      '罗贯中'
    ],
    // engine: 'baidu' 
  })
  console.log(result) // [0, 0, 13，0] 数值越大的表示搜索结果越匹配，理论上该选项为正确答案的几率更高，但不保证 100% 正确
  console.log(maxIndex) // 2
})()
```

