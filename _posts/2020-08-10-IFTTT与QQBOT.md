---
layout:     post
title:      IFTTT与OtterBot联动
subtitle:   通过IFTTT订阅github，然后发送到QQ
date:       2020-08-10
author:     LittleNightmare
header-img: img/post-bg-ios9-web.jpg
catalog: true
tags:
    - QQ
    - IFTTT
---
# IFTTT 与 OtterBot联动
### OtterBot
通过[OtterBot](https://github.com/Bluefissure/OtterBot/wiki/Webhook)的Webhooks功能来接收来着IFTTT的消息。想想参考项目的[ACT联动](https://github.com/Bluefissure/OtterBot/wiki/ACT%E8%81%94%E5%8A%A8)部分来找到开启api的方法。
### IFTTT
[IFTTT](https://ifttt.com/)可以全程为“if this then that”，本质上来说，就是一个if判断，然后执行。由于OtterBot的Webhooks是参照Discord的接口，所以基本可以参考Discord的方法来用。这里举一个例子：
1. 首先在`This`选择你的触发条件，比方说RSS，或者Twitter。
2. 在`That`页面选择Webhooks，点击`Make a web request`
3. 这里会出现`URL`,`Method`,`Content Type`, 以及`Body`选项，其中`URL`参考ACT联动部分，`Method`选择Post，`Content Type`选择`application/json`
4. Body部分参考如下设置
```json
{
    "content":"发布新内容"
}
```
5. 当然不要忘记添加你选择`This`的`ingredient`添加到内容
6. 最后点击`Finsh`即刻

推荐测试一下，如果提示500错误可能是`Body`部分填写错误