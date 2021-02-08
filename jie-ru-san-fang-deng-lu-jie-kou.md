# 接入三方登录接口

**1 JS调用Native的方法授权登录**

说明：用户登录授权

```text
GameLoginSdk.gameLogin(params);
```

**参数说明:**

params为json字符串**（注意：param必须是字符串，不要传json对象，否则Native无法解析）**，包含以下参数

| 参数 | 类型 | 描述 |
| :--- | :--- | :--- |
| login\_type | string | 0表示Google登录/1表示Facebook登录 |

**2 Native回调JS的方法通知三方登录成功的方法：**

说明：用户授权三方登录成功后通知JS游戏端

`function loginSuccess(result){...}`

**参数说明:**

result为json字符串，若三方登录成功，包含以下参数

| 参数 | 类型 | 描述 |
| :--- | :--- | :--- |
| userid | string | 用户id |
| nickname | string | 用户昵称 |
| icon | string | 用户图像 |

