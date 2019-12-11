# wechat-sdk-ts

Weixin [JS-SDK](https://mp.weixin.qq.com/wiki?t=resource/res_main&amp;id=mp1421141115)

## SDK Version

1.4.0

## Install

```sh
npm install wechat-sdk-ts --save
```

### git install
```sh
npm install git+https://github.com/allscanner/wechat-sdk-ts.git --save
```

## How to Use

### TypeScript

```ts
// sometime you want import this module, eg. use this with webpack
import { scanQRCode } from 'wechat-sdk-ts';

scanQRCode({
	needResult: 0,
	scanType: ['qrCode'],
	success(res) {
		console.log(res);
	}
});
```

or, you could add this module in your tsconfig.json

```json
{
	"compilerOptions": {
		"types": [
			"wechat-sdk-ts"
		]
	}
}
```

then use it freely.

```ts

jWeixin.scanQRCode({
	needResult: 0,
	scanType: ['qrCode'],
	success(res) {
		console.log(res);
	}
});

// sometimes you must use WeixinJSBridge, like wexin paying
WeixinJSBridge.invoke("getBrandWCPayRequest", {}, (res) => {
});
```

### javascript

**You will need this only if you would like get your project packed.**

```js
const wx = require('wechat-sdk-ts');
wx.scanQRCode({
	needResult: 0,
	scanType: ['qrCode'],
	success(res) {
		console.log(res);
	}
});
```

## Others

### ts Error

If you get this Error:
`[ts] Initializers are not allowed in ambient contexts.`

Try add `"skipLibCheck": true` to `compilerOptions` in file `tsconfig.json`.

Good luck!
