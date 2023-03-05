# ifreetime 爱阅书香
iOS爱阅书香TTS自建服务

## 本地/网络部署具硬TTS
https://github.com/wxxxcxx/ms-ra-forwarder

## Azure TTS 演示页面的接口
* 编辑编辑azure.php
* 更换API为你部署的网络地址：  CURLOPT_URL => '`http://127.0.0.1:3000/api/azure`'，并将`azure.php`扔到支持PHP的web网站

##  Edge 浏览器“大声朗读”接口
* 编辑ra.php
* 更换API为你部署的网络地址：  CURLOPT_URL => '`http://127.0.0.1:3000/api/ra`'，并将`ra.php`扔到支持PHP的web网站
* 如果azure接口抽风，请更换ra接口

## 多音字规则
可以尝试在`azure.php`里添加下面代码实现
在` <voice name="' . $voiceName . '"> `下一行添加代码：
`<lexicon uri="https://github.com/iranee/ifreetime/raw/main/lexicon.xml"/>`

## iOS端设置
1. 打开手机App，进入听书配置
2. 自定义语音库
3. 创建->高级自定义语音合成
* 名称：`任意`
* 合成字数：建议`200`
* 请求方式：`GET`
* 地址：`azure.php`网络地址，例如https://www.tts.com/azure.php 或者ra.php
* 参数->添加->请输入请求参数：`voiceName`，内容填自己想要的人声（参考`voiceName.txt`），例如`zh-CN-XiaoxiaoNeural`
* 参数->添加->请输入请求参数：`text`，内容填`%@`
* 解析字段->添加->请输入解析字段与规则：`playData`，内容填`ResponseData`
4. 测试发音，如果正确就ok了。
