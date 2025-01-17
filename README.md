# AsoulCnkiFrontEndV3

![index](markdown/index.png)

对原本的枝网前端进行重构和迁移

现阶段，枝网仍使用原本 Vue2.0 的版本，迁移完成前，旧版前端也会继续实装新功能

**待迁移完成后更换新版本并停止维护旧版本**

## 迁移描述

1. 从 Vue2 迁移到 Vue3 + TS
2. 打包工具更换为 Vite
3. 使用 WindiCSS 重构样式
4. 重新调整部分样式，重点是夜间模式配色

## 如何贡献

先 fork 项目到您的 GitHub 账户，然后再 clone，开新分支并发起 PR

## 当前进度

### Check页
  基本迁移完成，目前移除了Result，改为一键清空文本框

#### 新特性
  1. 一键清除文本框

#### 待实装新特性
  1. 支持查看自己的查询历史，并可以清空(使用localStorage)

#### 其他
  只需要在 ElDialog 的标签上添加 `width="none"` 就可以禁用 Element-Plus 默认添加的 width

### Rank页
  1. 页面基本重构完成
  2. 添加页码切换功能

#### 新特性
  1. 页码切换悬浮屏幕右侧
  2. 使用方向键 `←` `→` 翻页

#### 尚未完成的部分

  1. 待添加条件筛选组件在顶部框显示当前筛选的条件
  2. 待修复条件筛选组件和换页组件冲突产生的BUG

### Result页
  尚未迁移。

  由于用户使用次数较少，新版本可能会移除该功能

## 其他

1. <del>目前 Element-Plus 没有局部引入，构建后体积较大，后续配置局部引入</del>(已完成)
      
      备忘: 目前使用的组件 
      - ElCheckBox
      - ElDialog
      - ElCarousel
      - ElCarouselItem

2. 接口文档参见[这里](https://github.com/ASoulCnki/ASoulCnkiBackend/blob/master/api.md)

## 项目结构

```
src 源码目录
├── api          调用后端API，使用await
│   ├── check    查重API
│   └── rank     作文展API
├── assets       资源文件
│   ├── css      样式和字体文件
│   └── images   图片文件
├── components   组件
│   ├── activity 活动相关组件(彩蛋)
│   ├── check    主站(查重)组件
│   ├── public   公共组件(小作文组件，友情链接，顶部通知栏，侧边栏跑马灯，用户协议)
│   ├── rank     作文展组件
│   └── result   查重结果页组件
├── libs         库文件夹，目前只有 Element-Plus
├── pages        页面文件夹(Check, Rank)
├── router       前端路由(目前未根据组件拆分)
└── utils        工具函数(时间格式转换等)
    ├── article  小作文组件的支持函数(重复区间标记, 文本链接转换）
    ├── check    check页支持函数(数据格式转换, 判别是否为字符画)
    ├── rank     rank页支持函数(待添加过滤器相关方法)
    └── storage  封装localStorage属性
```

utils 部分功能待添加单元测试？

## 安装

```bash
npm i
```

## 运行 && 打包

### 启动开发机

```bash
npm run dev
```

### 构建

```bash
npm run build
```

### 本地预览构建产物

```bash
npm run serve
```