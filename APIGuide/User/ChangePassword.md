# 登入

## 1. 路徑

*hostname*/api/**User/ChangePassword**

## 2. 參數

### ⅰ. Method

    POST

### ⅱ. header

    (待補)

### ⅲ. parameter

    (BODY)
    ※以下資料是使用者修改密碼時產生的加密資料

```csharp
    public struct ChangePasswordRequest
    {
        /// <summary>
        /// 使用者帳號(加密)
        /// </summary>
        public string UserID;
        /// <summary>
        /// 使用者密碼(加密)
        /// </summary>
        public string Password;
        /// <summary>
        /// 使用者新的密碼(加密)
        /// </summary>
        public string NewPassword;
    }
```

## 3. 呼叫示例

* 密碼修改
 > `http:// [hostname] /api/User/ChangePassword`
 >
 >> ```json
 >> {
 >>     "UserID": "MiI3eiXMSULX3R8KL6KMEw==",
 >>     "Password":"ijzA15UdmuC1RmI7cUtMHw==",
 >>     "NewPassword":"sNuXwppgQM9i6NkUSRLr/g=="
 >> }
 >> ```

## 4. 請求結果

依據呼叫端給予的帳號資料，驗證完成後，將修改密碼成功/失敗訊息，回傳呼叫端。

***

```csharp
    public struct UserActionResponse
    {
        /// <summary>
        /// 使用者帳號(加密)
        /// </summary>
        public string UserID;
        /// <summary>
        /// 是否通過
        /// </summary>
        public bool Pass;
    }
```

## 5. 回應信息示例

```json
{
    "Code": 0,
    "Message": "",
    "Data": {
      "UserId": "MiI3eiXMSULX3R8KL6KMEw==",
      "Pass": true
    }
}
```
