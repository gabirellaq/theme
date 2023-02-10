# 切换主题方案

## 全局
给全局加上 `document.body.setAttribute('theme', 'dark');`，切换主题后无效刷新页面
```
body[theme=dark] {
  --bg-color: #000;
}

body[theme=light] {
  --bg-color: #fff;
}

body {
  background: var(--bg-color);
}
```

## 组件
使用css变量切换主题，这样的好处是只需要定义不同主题下的变量即可，主要样式只需要写一遍，建议开发组件时使用css变量
```
<Component class="component-class" theme={theme} />

// css style
.component-class[theme=light] {
  --bg-color: #f7f7f7;
  --text-color: #999;
}

.component-class[theme=dark] {
  --bg-color: #000;
  --text-color: #fff;
}

.component-class {
  background: var(--bg-color);
  color: var(--text-color)
}

```

## 第三方组件库
依据组件库本身提供的主题切换方式来实现，如果组件本身使用的是css变量，则只需要将变量更新即可，如果组件库本身使用的是其他变量，可以通过自定义主题功能定制好之后放置本地
