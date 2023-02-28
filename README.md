# gpt-wework
企业微信（客服）能力下的 GPT-3 微信机器人

![](https://raw.githubusercontent.com/razertory/statics/main/staic/1.jpeg)

​目前越来越多的人开始用 GPT-3 相关的产品协助自己的工作和学习，在微信上也有不少接入API的机器人。
不过目前而言，想拥有微信原生的体验，多数是基于浏览器模式下的微信号。这种做法有两个限制

用的微信号是能够登陆网页版微信的，这种号会越来越少，
一不注意就有封的风险，Kotaro 的朋友圈就已经出现号被封的情况了。


在各种尝试和实验下，我上线了一种基于企业微信客服的​做法。
- 能够媲美原生的体验：私聊，分享，翻译等等​。后期考虑加入群聊，如果有需要
- 技术上和微信解耦




## 操作流程
#### 注册并登陆企业微信后台
应用管理 - 微信客服
![](https://raw.githubusercontent.com/razertory/statics/main/staic/2.png)

#### 配置应用服务器
填写项目所在服务器的 host 以及 [main.go](./main.go) 的
`/wechat/check`

相关的参数参考[wechat.go](./service/wechat.go) 上方的参数
```
// 验证企业微信回调的token
var token = "token"

// 验证企业微信回调的key
var encodingAesKey = "encodingAesKey"

// 企业微信企业id 这个参数在企业微信后台的企业信息页
var corpid = "corpid"

// 企业微信secret 这个参数需要通过企业微信app发送
var corpsecret = "corpsecret"
```
注意，只有这些参数和企业微信`接收事件服务器`一致的时候，才能验证通过

![](https://raw.githubusercontent.com/razertory/statics/main/staic/4.png)
![](https://raw.githubusercontent.com/razertory/statics/main/staic/5.png)

#### 配置机器人
让客服机器人被API接管
![](https://raw.githubusercontent.com/razertory/statics/main/staic/6.png)



​





