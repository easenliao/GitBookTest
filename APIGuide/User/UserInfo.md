# 使用者資訊

## 1. 路徑

*hostname*/api/**User**

## 2. 參數

### ⅰ. Method

    GET

### ⅱ. header

    (待補)

### ⅲ. parameter

    (URI)
    id：帳號(加密)

## 3. 呼叫示例

* 查詢使用者資訊
> `http:// [hostname] /api/User?id=MiI3eiXMSULX3R8KL6KMEw==`

## 4. 請求結果

依據呼叫端請求的帳號，回傳指定的帳號資料，若查無帳號則回應無效。

***

```csharp
    public struct UserInfo
    {
        /// <summary>
        /// 使用者帳號(加密)
        /// </summary>
        public string UserID;
        /// <summary>
        /// 使用者名稱(加密)
        /// </summary>
        public string UserName;
        /// <summary>
        /// 身分(加密)
        /// </summary>
        public string RoleTitle;
    }
```

## 5. 回應信息示例

```json
{
    "Code": 0,
    "Message": "",
    "Data": {
        "UserID": "MiI3eiXMSULX3R8KL6KMEw==",
        "UserName": "AFZl1Xx7xLLhKV/CZTI10A==",
        "RoleTitle": "yhUTwWQQzw/xKXalrCC45w=="
    }
}
```
