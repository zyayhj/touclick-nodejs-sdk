##点触验证码 Nodejs SDK

#### DEMO

DEMO ：[http://github.com/touclick/captcha-demo/](https://github.com/touclick/captcha-demo/tree/master/nodejs-demo "nodejs-demo")

#### 安装

```bash
$ npm install --save touclick-nodejs-sdk
```

#### 如何使用

1. 引用：

	```javascript
	var tc = require("touclick-nodejs-sdk");
	```

2. 初始化

	```javascript
	/**
	 * @param pubkey 公钥
	 * @param prikey 私钥
	 * 公钥、私钥，在http://admin.touclick.com 注册以获取公钥和私钥
	 */
	tc.init(pubkey,prikey);
	```

3. 二次验证

	```javascript
	/**
	 * @param token 二次验证口令，单次有效
	 * @param checkAddress 二次验证地址，二级域名
	 * @param checkCode 校验码，开发者自定义，一般采用手机号或者用户ID，用来更细致的频次控制
	 */
	tc.check(token, checkAddress, checkCode);
	```

##### LOG4JS

默认日志输出为ERROR，可以通过修改环境变量 `LOG4JS_LEVEL`，更改日志输出等级

日志输出路径是 `logs/touclick.log`

```javascript
var logger = log4js.getLogger('touclick'),
log4jsLevel = process.env.LOG4JS_LEVEL ||'ERROR';
logger.setLevel(log4jsLevel);
```

#### 