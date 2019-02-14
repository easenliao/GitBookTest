# 新增司機我的最愛站所

## 1. 路徑

*hostname*/api/**System/Truckers/FavoriteStation**

## 2. 參數

### ⅰ. Method

    POST

### ⅱ. header

    (待補)

### ⅲ. parameter

    (URI)

## 3. 呼叫示例

* 新增我的最愛站所
> `http:// [hostname] /System/Truckers/FavoriteStation/124`

## 4. 請求結果

依據呼叫端給予的資料，執行完成後(不論成功與否)，皆將資料內的鍵值回覆予呼叫端，呼叫端則依據回應訊息(ResponseCode)執行後續動作。

## 5. 回應信息示例

```json
{
    "Code": 0,
    "Message": "",
    "Data": 124
}
```