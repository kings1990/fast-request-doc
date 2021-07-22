# Fast Request

[![Jetbrains Plugins][plugin-img]][plugin]
![Version](https://img.shields.io/jetbrains/plugin/v/16988)
![Downloads](https://img.shields.io/jetbrains/plugin/d/16988)
[![QQ群](https://img.shields.io/badge/chat-QQ群-46BC99.svg?style=flat-square)](https://qm.qq.com/cgi-bin/qm/qr?k=1OEJ5QST4zoEUv0x0OvOmC3TUfAIZXAO)
[![Slack](https://img.shields.io/badge/Slack-%23Fast--Request-red)](https://fastrequest.slack.com)

[**Fast Request**](https://plugins.jetbrains.com/plugin/16988-fast-request) 是一个基于springmvc的帮助你快速生成**url**和**参数**的插件.同时也是一个http client工具

你只需要按一下快捷键,插件就会给你方法的url和参数,再点击发送请求即可完成http请求

目前插件对标的是[Paw](https://paw.cloud/)

如果你觉得本插件不错,请给个🌟Star吧,也欢迎提供优秀的PR

![example](./screenshot/example.gif)

- document
    * [中文文档](README.zh_CN.md)
    * [English Document](README.md)

QQ 群:754131222

## 0.安装

**插件市场安装**

- <kbd>Preferences(Settings)</kbd> > <kbd>Plugins</kbd> > <kbd>Browse repositories...</kbd> > <kbd>输入"Fast
  Request"</kbd> > <kbd>点击Install</kbd>

**手动安装:**

- 下载[`lastest plugin zip`][latest-release] -> <kbd>Preferences(Settings)</kbd> > <kbd>Plugins</kbd> > <kbd>Install
  plugin from disk...</kbd>

## 1.如何使用
```
Step1:点击配置添加项目名[如微信卡片]和环境名[如local、dev]
Step2:设置对应项目及环境的域名
Step3:打开工具窗口(右上角位置),选择当前项目想要启用的环境,并且点击开启复选框
Step4:点击在方法左侧的fastRequest的图标(自动生成参数和url)
Step5:点击发送请求按钮发送请求
```

![](./screenshot/howToUse.gif)

## 2.默认快捷键
推荐用法:点击图标
![](./screenshot/methodIcon.png)

[comment]: <> (也可通过IDEA快捷键设置修改)

[comment]: <> (|快捷键|作用域|说明|)

[comment]: <> (| --- | --- | --- |)

[comment]: <> (| <kbd> ctrl \ </kbd> | 方法&#40;光标放上面就行&#41; | 生成当前方法的url和请求参数 |)

[comment]: <> (如果它不起作用，您可以在Keymap中搜索<kbd>Generate URL and Param</kbd>并更改快捷键)

[comment]: <> (修改路径:<kbd>Preferences&#40;Settings&#41;</kbd> > <kbd>Keymap</kbd>)

[comment]: <> (另外的方法:<kbd>Code&#40;Toolbar&#41;</kbd> > <kbd>Generate</kbd> > <kbd>Generate URL and Param</kbd>)

## 3.配置及使用

### 3.1 公共配置
|配置名|描述|
| --- | --- |
|ProjectName|项目名,如user、order等,请确保必须先有一个project再添加env|
|Env|环境名,如local、develop、test、produce等|
|Domain|在表格中维护对应项目对应环境的域名|

![](./screenshot/commonConfig.png)

### 3.2 数据映射
|配置名|描述|
| --- | --- |
|Random String Length|随机出的字符串长度,默认为5|
|Custom Data Mapping|如果你想要一个类只解析自己想要的字段,那么你可以通过添加自定义的映射配置|
|Default Data Mapping|默认类型的关系映射,即类型转化为对应的值|

![](./screenshot/dataMapping.png)

#### 3.2.1 Custom Data Mapping
**Java Type**为对应的对象类型,必须是包含包名和类名,如`com.baomidou.mybatisplus.extension.plugins.pagination.Page`

**Default value**必须是json格式,如
```
{"size":10,"current":1}
```

### 3.3 其他配置

控制器上的url固定变量可以由配置替换,例如类控制器上url写法如下

```
@RequestMapping("/api/${api-module}/user")
@Controller
public class XxxController(){
  ...
}
```

实际的url是`/api/base/user`

那么可以通过以下配置来替换`${api-module}`变量
![](./screenshot/otherConfig.png)


## 4.类型ICON映射
图标和类型映射关系

|Icon|Type|
| --- | --- | 
|![](./screenshot/icon/array.svg)  |Array  |
|![](./screenshot/icon/object.svg) |Object |
|![](./screenshot/icon/number.svg) |Number |
|![](./screenshot/icon/string.svg) |String |
|![](./screenshot/icon/boolean.svg)|Boolean|
|![](./screenshot/icon/file.svg)|File|

## 5.支持作者
如果觉得插件很赞，为你节约了不少时间，那么就请作者喝杯咖啡吧~☕☕☕,非常感谢

| ![微信](./screenshot/pay/wechat.jpg) | ![支付宝](./screenshot/pay/alipay.png) |
| --- | --- |

## 6.FAQ
>问题1:关于控制台挡住工具窗口  
答:目前官方在工具窗口和控制台同时可见时,不支持工具窗口的显示优先于控制台,所以你只能通过调整[视图模式](https://www.jetbrains.com/help/idea/viewing-modes.html)
来控制,或者通过快捷键来快速隐藏和显示控制台(快捷键:view->toolWindow->run/debug可见快捷键)，使得工具窗口中的内容全部可见。当然你可以点击隐藏Request部分来看Response

>问题2:为啥插件没反应  
答:请优先按照第一章节介绍的使用步骤配置相关的配置,再点击图标

>问题3:点击图标后idea卡死  
>答:你设计的实体类嵌套递归,插件不支持

[latest-release]: https://github.com/kings1990/fast-request/releases/latest
[plugin]: https://plugins.jetbrains.com/plugin/16988
[plugin-img]: https://img.shields.io/badge/plugin-FastRequest-x.svg
