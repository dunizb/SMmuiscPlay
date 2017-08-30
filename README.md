# 极简模式JavaScript音乐播放器组件

## 特点
- 极简（无花俏布局和样式）
- 小巧（117行js代码）
- 无依赖（无CSS、图片等依赖）
- 可定制（自定义设置）

## 它能做什么？
- [X] 控制音乐状态（播放、暂停）
- [X] 灵活的音乐资源配置（当个、多个）
- [X] 自动音乐列表（无选择列表、有列表）
- [X] 可指定播放器所在容器（元素、页面）
- [X] 可指定播放器所在容器位置（顶、左、右、下）
- [X] 可自动加载音乐资源并播放（浏览器、微信网页等）
- [X] 可自定义播放器皮肤（按钮、列表）
- [X] 极简小巧（无图片资源、无CSS样式文件加载）
- [X] 更友好的用户体验（手机、PC）

## 场景

适合手机页面，H5活动页，微信页面等的音乐播放支持

## 使用

构造器：`SMmuiscPlay(options)`

示例演示页面：index.html

## options选项

**el [必须]** 

指定播放器所在容器（元素、页面）,不指定则默认挂载在`body`上
```js
SMmuiscPlay({
    el: "app",
    audioUrl: "muisc/xxxx.mp3",
    animaClass: "muiscIconRotate"
});
```

**audioList [必须]**

音乐列表（无选择列表、有列表）,单个歌曲会隐藏音乐列表
- title: 音乐名称
- source: 音乐地址

```js
SMmuiscPlay({
    el: "app",
    audioList:"./music/独角戏.mp3",
});
```
或
```js
SMmuiscPlay({
    el: "app",
    audioUrl: [
        {
            title: "aaaaaa",
            source: "muisc/aaaaaa.mp3"
        },
        {
            title: "bbbbbb",
            source: "muisc/bbbbbb.mp3"
        }
    ]
});
```

**animaClass [必须]**

定义音乐图标旋转动画

定义动画：
```css
@keyframes muiscIconRotate{
    from{transform: rotate(0deg);}
    to{transform: rotate(360deg);}
}
```
设置`animaClass`
```js
SMmuiscPlay({
    el: "app",
    audioUrl: "muisc/xxxx.mp3",
    animaClass: "muiscIconRotate"
});
```

**position**

播放器位置，CSS定位  
```js
SMmuiscPlay({
    el: "app",
    position: "top:10px;left:10px",//左上角
    audioUrl: "muisc/xxxx.mp3"
});
```

**buttonImgSrc**

音乐播放按钮图片,强烈建议使用SVG图片
```js
SMmuiscPlay({
    el: "app",
    buttonImgSrc: "icon.png",
    position: "top:10px;left:10px",//左上角
    audioUrl: "muisc/xxxx.mp3"
});
```

**htmls**

自定义
```js
SMmuiscPlay({
    el: "app",
    buttonImgSrc: "icon.png",
    position: "top:10px;left:10px",//左上角
    htmls: "<div>....<div>"
    audioUrl: "muisc/xxxx.mp3"
});
```

## 更新

**2017.08.30**
升级 0.0.1 => 0.0.2

音乐播放图标
- 默认使用SVG格式
- 需要自己设置图标的旋转动画 

样例，可直接拷贝到页面：
```css
@keyframes muiscIconRotate{
    from{transform: rotate(0deg);}
    to{transform: rotate(360deg);}
}
```
然后添加`animaClass`属性：
```js
SMmuiscPlay({
    el: "app",
    audioUrl: "muisc/xxxx.mp3",
    animaClass: "muiscIconRotate"
});
```