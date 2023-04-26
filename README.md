# ifreetime 爱阅书香
iOS爱阅书香TTS自建服务

## 本地/网络部署具硬TTS
https://github.com/wxxxcxx/ms-ra-forwarder

##  Edge 浏览器“大声朗读”接口
* 编辑ra.php
* 更换API为你部署的网络地址：  CURLOPT_URL => '`http://127.0.0.1:3000/api/ra`'，并将`ra.php`扔到支持PHP的web网站


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
5. ra.php引用链接最好是HTTPS协议，并且有安装域名证书。