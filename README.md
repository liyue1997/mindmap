<img src="./public/mindmap.jpg" width="300"/>

# 思维导图Vue2组件
[![NPM version](https://img.shields.io/npm/v/@sunxy98/mindmap)](https://www.npmjs.com/package/@sunxy98/mindmap)
[![NPM monthly downloads](https://img.shields.io/npm/dm/@sunxy98/mindmap)](https://www.npmjs.com/package/@sunxy98/mindmap)
[![NPM total downloads](https://img.shields.io/npm/dt/@sunxy98/mindmap)](https://www.npmjs.com/package/@sunxy98/mindmap)

> Mark and Rossee基于@hellowuxin/mindmap优化改进，并依据开源政策向大家分享。
> 一个由[MindNode](https://mindnode.com)启发的思维导图Vue组件，基于d3.js实现。
> 
> 目前实现的功能有基本的编辑、拖移、缩放、撤销、上下文菜单、折叠...
> 
> 新增功能包括：换肤、拖拉组件实现缩放

## 安装

```sh
npm install @sunxy98/mindmap
```

## PROPS

| Name        | Type   | Default   | Description |
| ---         | ---    | ---       |-------------|
| v-model     | Array  | undefined | 设置思维导图数据    |
| width       | Number | 100%      | 设置组件宽度      |
| height      | Number | undefined | 设置组件高度      |
| xSpacing    | Number | 80        | 设置节点横向间隔    |
| ySpacing    | Number | 20        | 设置节点纵向间隔    |
| strokeWidth | Number | 4         | 设置连线的宽度     |
| draggable   | Boolean| true      | 设置节点是否可拖拽   |
| theme       | Boolean| true      | 是否显示换肤按钮    |
| gps         | Boolean| true      | 是否显示居中按钮    |
| fitView     | Boolean| true      | 是否显示缩放按钮    |
| showNodeAdd | Boolean| true      | 是否显示添加节点按钮  |
| keyboard    | Boolean| true      | 是否响应键盘事件    |
| contextMenu | Boolean| true      | 是否响应右键菜单    |
| zoomable    | Boolean| true      | 是否可缩放、拖移    |
| showUndo    | Boolean| true      | 是否显示撤销重做按钮  |
| download    | Boolean| true      | 是否显示下载按钮    |

## 事件

| Name           | arguments | Description                    |
| ---            | ---       | ---                            |
| updateNodeName | data, id  | 更新节点名称时，传入节点数据和节点id |
| click          | data, id  | 点击节点时，传入节点数据和节点id    |

## 样例

```html
<template>
  <mindmap v-model="data"></mindmap>
</template>

<script>
import mindmap from '@sunxy98/mindmap'

export default {
  components: { mindmap },
  data: () => ({
    data: [{
      "name":"如何学习D3",
      "children": [
        {
          "name":"预备知识",
          "children": [
            { "name":"HTML & CSS" },
            { "name":"JavaScript" },
            ...
          ]
        },
        {
          "name":"安装",
          "_children": [
            { "name": "折叠节点" }
          ]
        },
        {
          "name":"进阶",
          "left": true
        },
        ...
      ]
    }]
  })
}
</script>
```

## 键盘事件

<kbd>⇥ tab</kbd>、<kbd>⏎ enter</kbd>、<kbd>⌫ backspace</kbd>、<kbd>⌘ cmd</kbd>+<kbd>z</kbd>、<kbd>⌘ cmd</kbd>+<kbd>y</kbd>

## 交互逻辑

**鼠标**：space+左键移动、右键菜单、ctrl+滚轮缩放、左键选中

**触控板**：双指滚动移动、双指菜单、双指捏合缩放、单指选中

## 待解决

- [ ] 导出多种格式
- [ ] 设置节点的宽高
- [ ] 多个根节点
