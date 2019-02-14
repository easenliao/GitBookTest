# 登入

## 1. 路徑

*hostname*/api/**User/SignIn**

## 2. 參數

### ⅰ. Method

    POST

### ⅱ. header

    (待補)

### ⅲ. parameter

    (BODY)
    ※以下資料是使用者登入時產生的加密資料

```csharp
    public struct SignInRequest
    {
        /// <summary>
        /// 使用者帳號(加密)
        /// </summary>
        public string UserID;
        /// <summary>
        /// 使用者密碼(加密)
        /// </summary>
        public string Password;
    }
```

## 3. 呼叫示例

* 帳號登入
> `http:// [hostname] /api/User/SignIn`
>
>> ```json
>> {
>>     "UserID": "MiI3eiXMSULX3R8KL6KMEw==",
>>     "Password": "ijzA15UdmuC1RmI7cUtMHw=="
>> }
>> ```

## 4. 請求結果

依據呼叫端給予的帳號資料，驗證完成後，將登入成功/失敗訊息，回傳呼叫端。

***

```csharp
    public struct SignInResponse
    {
        /// <summary>
        /// 使用者帳號(加密)
        /// </summary>
        public string UserID;
        /// <summary>
        /// 是否通過
        /// </summary>
        public bool Pass;
        /// <summary>
        /// 驗證碼(加密)
        /// </summary>
        public string Token;
    }
```

## 5. 回應信息示例

```json
{
    "Code": 0,
    "Message": "",
    "Data":{
        "UserID": "MiI3eiXMSULX3R8KL6KMEw==",
        "Pass": true,
        "Token": "lyrVq5kLCG1SG7MMeqbHKRD77A2X2V1fyrpm6dnwYL5bdQKI/jGN3P0G7qDR88bzNy8GcCrSxFM3uYRUbG8P2A=="
    }
}
```
