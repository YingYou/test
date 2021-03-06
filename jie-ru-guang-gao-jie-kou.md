# 接入广告接口

* **1 js 回调Native的广告方法：**

  该方法用户js游戏展示广告（包括facebook及google的广告）

```text
ANDROID:   GoogleAdSdk.showWithAdType(params);

iOS:   GameFunction.showWithAdType(params);
```

 **参数说明:**

params为json字符串**（注意：param必须是字符串，不要传json对象，否则Native无法解析）**，包含以下参数

| 参数 | 类型 | 描述 |
| :--- | :--- | :--- |
| ad\_parent\_type | string |  广告类型（0表示google广告/1表示facebook广告） |
| ad\_type | string | 广告单元（0表示顶部横幅banner广告；1表示底部横幅banner；2表示插屏广告；3表示视频激励广告） |

**2 Native回调JS的方法：**

该方法是告诉js游戏展示的广告相关信息包括该广告单元的状态情况。

`function`adShowInfo`(result){...}`

**参数说明:**

result为json字符串，广告展示出后的回调结果，包含以下参数

| 参数 | 类型 | 描述 |
| :--- | :--- | :--- |
| ad\_parent\_type | string | 广告类型0是Google广告/1是Facebook广告 |
| ad\_type | string | 广告单元（参见方法1说明） |
| status | string | 广告单元的展示状态                                0是加载广告                                            1 是广告加载失败                                      3 是广告在屏幕打开                                  4 是广告关闭                                           5 是视频广告开始播放                           /6是视频广告播放完成                           /7视频广告触发奖励时                              /8广告离开应用程序时调用（例如，转到浏览器 |
| extradata | json | 额外信息主要针对激励视频广告类型 |
| amount | string | 奖品数量 |
| type | string | 奖品名字 |

