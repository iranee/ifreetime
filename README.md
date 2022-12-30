# ifreetime
爱阅书香iOS资料

## 本地/网络部署具硬TTS
https://github.com/wxxxcxx/ms-ra-forwarder

## 设置azure.php
更换API的为你部署的网络地址：  CURLOPT_URL => '`http://127.0.0.1:3000/api/azure`'，并将`azure.php`扔到支持PHP的web网站

## 多音字规则
如果没有过多要求，建议删除`azure.php`里的`<lexicon uri="https://github.com/iranee/ifreetime/raw/main/lexicon.xml"/>`

## iOS端设置
1. 打开手机App，进入听书配置
2. 自定义语音库
3. 创建->高级自定义语音合成

请求方式：`GET`

地址：`azure.php`网络地址，例如https://www.tts.com/azure.php

参数->添加->请输入请求参数：`voiceName`，内容填自己想要的人声（参考`voiceName.txt`），例如`zh-CN-XiaoxiaoNeural`

参数->添加->请输入请求参数：`text`，内容填`%@`

4. 解析字段->添加->请输入请求参数：`playData`，内容填`ResponseData`
5. 测试发音，如果正确就ok了。建议先删除多音字规则那部分测试。
