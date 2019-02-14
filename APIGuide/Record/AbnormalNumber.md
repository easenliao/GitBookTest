# 回報掃描記錄異常(目前取消)

## 1. 路徑

*hostname*/api/**Record/Numbers/{id}/Abnormal**

## 2. 參數

### ⅰ. Method

    POST

### ⅱ. header

    (待補)

### ⅲ. parameter

    (URI)
    ID：上傳記錄鍵值(UUID)
***
    (BODY)
    ※以下資料皆是使用者當下操作時產生的資料

```csharp
    public struct AbnormalRecord
    {
        /// <summary>
        /// 授權碼
        /// </summary>
        public string Token;
        /// <summary>
        /// 使用者帳號
        /// </summary>
        public string UserID;
        /// <summary>
        /// APP內部自存鍵值
        /// </summary>
        public string SelfKey;
        /// <summary>
        /// 記錄時間(yyyyMMddHHmmssfff)
        /// </summary>
        public string RecordDateTime;
    }
```

## 3. 呼叫示例

* 上傳記錄
> `http:// [hostname] /api/Record/Numbers/4bf07297-65b2-45ca-b905-6fc6f2f39158/Abnormal`
>
>> ```json
>> {
>>     "Token": "fdsacxzvdafeqr",
>>     "UserID": "0914099788",
>>     "SelfKey": "124",
>>     "RecordDateTime": "20180401124546548"
>> }
>> ```

## 4. 請求結果

依據呼叫端給予的資料，執行完成後(不論成功與否)，皆將資料內的鍵值回覆予呼叫端，呼叫端則依據回應訊息(ResponseCode)執行後續動作。

***

資料結構

```csharp
    public struct RecordResponse
    {
        /// <summary>
        /// 上傳記錄鍵值(UUID)
        /// </summary>
        public string ID;
        /// <summary>
        /// APP內部自存鍵值
        /// </summary>
        public string SelfKey;
    }
```

## 5. 回應信息示例

```json
{
    "Code": 0,
    "Message": "",
    "Data":{
        "ID": "4bf07297-65b2-45ca-b905-6fc6f2f39158",
        "SelfKey": "124"
    }
}
```