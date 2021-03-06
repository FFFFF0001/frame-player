# frame-player

[![License MIT](https://img.shields.io/npm/l/frame-player.svg)](https://github.com/zhuweiyou/frame-player/blob/master/LICENSE)
[![NPM Version](https://img.shields.io/npm/v/frame-player.svg)](https://www.npmjs.com/package/frame-player)
[![NPM Download](https://img.shields.io/npm/dt/frame-player.svg)](https://www.npmjs.com/package/frame-player)

图片序列帧播放器，代替 gif、video 播放

## Install

- 本地
```bash
npm i -S frame-player
```

```js
import FramePlayer from 'frame-player'

const framePlayer = new FramePlayer(options)
```

- CDN
```html
<script src="//unpkg.com/frame-player"></script>
```

## Example

https://zhuweiyou.github.io/frame-player/

## API
- [class: FramePlayer(options)](#class-frameplayeroptions)
  - [FramePlayer.version](#frameplayerversion)
  - [event: 'loading'](#event-loading)
  - [event: 'ready'](#event-ready)
  - [event: 'play'](#event-play)
  - [event: 'update'](#event-update)
  - [event: 'stop'](#event-stop)
  - [framePlayer.on(event, fn)](#frameplayeronevent-fn)
  - [framePlayer.play([desc])](#frameplayerplaydesc)
  - [framePlayer.stop([frame])](#frameplayerstopframe)
  - [framePlayer.frame](#frameplayerframe)
  
### class: FramePlayer(options)
- `options` <[Object]> 
  - `canvas` <[string]|[HTMLCanvasElement]> 画布选择器 | 画布对象。默认 `"canvas"`
  - `width` <[number]> 绘制宽度（当设置了 css width 时，作为绘制比例）
  - `height` <[number]> 绘制高度（当设置了 css height 时，作为绘制比例）
  - `images` <[Array]<[string]>> 图片路径数组
  - `fps` <[number]> 帧率。默认 `24`
  - `loop` <[number]> 循环播放次数。`-1` 为无限循环，默认 `0` 不循环
  - `alternate` <[boolean]> 是否轮流反向播放，配合 `loop` 使用才有效果。默认 `false`
  - `transparent` <[boolean]> 图片是否透明，`true` 每次绘制前清空画布。默认 `false`
  - `autoPlay` <[boolean]> 是否自动播放，`true` 会在图片 [ready](#event-ready) 后立即播放。默认 `false`

#### FramePlayer.version
- returns: <[number]> 获取当前版本号

#### event: 'loading'
- `options` <[Object]>
  - `count` <[number]> 加载完成的图片数量
  - `total` <[number]> 图片总数

正在加载图片的事件，可用于画面上显示加载进度

#### event: 'ready'
所有图片加载完成的事件

#### event: 'play'
开始播放的事件

#### event: 'update'
- `options` <[Object]>
  - `frame` <[number]> 当前帧索引
  - `times` <[number]> 当前循环次数
  - `desc` <[boolean]> 当前是否反向播放

播放每一帧的事件

#### event: 'stop'
停止播放的事件

#### framePlayer.on(event, fn)
- `event` <[string]> 事件名
- `fn` <[function]> 回调函数

事件监听

#### framePlayer.play([desc])
- `desc` <[boolean]> 是否反向播放。默认 `false`

播放动画，将从之前 [stop()](#frameplayerstopframe) 的位置继续播放，默认从 `0` 开始

#### framePlayer.stop([frame])
- `frame` <[number]> 停止的帧索引。默认 `当前播放索引`

停止播放，也可以传入 frame 跳帧到指定位置

#### framePlayer.frame
- returns: <[number]> 获取当前播放帧索引

[Object]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object "Object"
[string]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#String_type "String"
[HTMLCanvasElement]: https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement "HTMLCanvasElement"
[Image]: https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/image "Image"
[number]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#Number_type "Number"
[Array]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array "Array"
[boolean]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#Boolean_type "Boolean"
[function]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function "Function"

