# 接入内购支付接口

**1 js 回调Native的调起内购支付方法：**

该方法调起支付页面

```text
StorePay.queryAppPayWithProductId(params);
```

**参数说明:**

params为json字符串**（注意：param必须是字符串，不要传json对象，否则Native无法解析）**，包含以下参数

| 参数 | 类型 | 描述 |
| :--- | :--- | :--- |
| productId | string |  产品ID（需在googlepay和appstore平台上填写获取的） |
| payload | string | 定义订单号 |

**2 Native回调JS的方法通知支付完成的方法：**

说明：当app支付完成后通知JS游戏端

`function`completeTransactionWithPurchase`(result){...}`

**参数说明:**

result为json字符串，若支付成功后，包含以下参数

| 参数 | 类型 | 描述 |
| :--- | :--- | :--- |
| payload | string | 订单号（JS可以比较前后订单是否一致。） |

