# GoogleAuthenticator
GoogleAuthenticator

## Link

[Documents](https://stephen520.cn/blog/41)

## Use

### Step

1. `Google 商店` 或 `App Store` 下载 `Google Authenticator` APP
2. 扫描生成的二维码进行绑定
3. 在网页中输入APP中生成的临时code，提交验证

### Bind

```
$auth = new GoogleAuthenticator();
$secret = $auth->createSecret()

// 方法一、生成二维码URL，国内无法访问，不推荐使用
$qrcode = $auth->getQRCodeGoogleUrl($username, $secret);

// 方法二、生成验证码，然后手动生成二维码
$code = $auth->getCode($secret);
// 手动生成二维码，此处省略……
```

### Verify

```
$auth->verifyCode($secret, $_POST['code']);
```
