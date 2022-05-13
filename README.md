# theme-next-calendar

简洁的hexo-next日历云插件, 在日历上显示提交标记

![](example.png)

### 安装

1. 首先安装hexo插件

```shell
npm install theme-next/theme-next-calendar
```

2. 在next主题配置文件`_config.yml`配置
```yaml
CloudCalendar:
  enable: true
  language: zh-CN
  single: true
  root: /calendar/
  calendarCdn: //cdn.jsdelivr.net/gh/theme-next/theme-next-calendar/calendar.min.js
  langCdn: //cdn.jsdelivr.net/gh/theme-next/theme-next-calendar/languages.min.js
  #disableSidebar: false
```

### 渲染日历

默认是在边栏中渲染, 当然也可以在任何位置显示, 只要`disableSidebar`禁用，并添加`sidebar.swig`中的代码至你希望的位置

### 自定义日历颜色

日历插件内各元素的颜色都是可定制的, 可以通过添加自定义样式覆盖`calendar.styl`中的定义来达到更好的效果.

### 说明

提取自`Landscape-F`主题, 修改后适配theme-next

### 更新

为了适配新版的Next主题，作了几处修改：
1. `calendar.swig`修改为`calendar.njk`，并且将里面的`{% if theme.CloudCalendar.enable %}{% endif %}`标签修改为`<div></div>`。
2. 将`sidebar.swig`修改为`sidebar.njk`,里面的文件保持不变。
3. 两个`.swig`已经修改为`.njk`，自然`index.js`里面的路径也要修改，修改如下：
```
 path.join(__dirname ,'sidebar.njk')
path.join(__dirname ,'calendar.njk')
```

Next-8.11.0版本实测可用。