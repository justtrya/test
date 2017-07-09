# meta基础知识

1. H5页面窗口自动调整到设备宽度，并禁止用户缩放页面


   ```html
   <meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
   ```

2. 忽略将页面中的数字识别为电话号码

   ```html
   <meta name="format-detection" content="telephone=no" />
   ```

3. 忽略Android平台中对邮箱地址的识别

   ```html
   <meta name="format-detection" content="email=no" />
   ```

4. 当网站添加到主屏幕快速启动方式，可隐藏地址栏，仅针对ios的safari

   ```html
   <!-- ios7.0版本以后，safari上已看不到效果 --> 
   <meta name="apple-mobile-web-app-capable" content="yes" />
   ```

5. 将网站添加到主屏幕快速启动方式，仅针对ios的safari顶端状态条的样式

   ```html
   <!-- 可选default、black、black-translucent --> 
   <meta name="apple-mobile-web-app-status-bar-style" content="black" />
   ```

6. 向搜索引擎说明你的网页的关键词

   ```html
   <meta name="keywords" content="">
   ```

7. 告诉搜索引擎你的站点的主要内容

   ```html
   <meta name="description" content="">
   ```

8. 告诉搜索引擎你的站点的制作的作者

   ```html
   <meta name="author" content="your name">
   ```

   ​

---



##  ios系统中元素被触摸时产生的半透明灰色遮罩怎么去掉？

ios用户点击一个链接，会出现一个半透明灰色遮罩, 如果想要禁用，可设置`-webkit-tap-highlight-color`的`alpha`值为0，也就是属性值的最后一位设置为0就可以去除半透明灰色遮罩

```css
a,button,input,textarea{
  -webkit-tap-highlight-color: rgba(0,0,0,0;)
}
```

---

