# 上傳掃描記錄  

## 1. 路徑

*hostname*/api/**Record/Numbers**

## 2. 參數

### ⅰ. Method

    POST

### ⅱ. header

    (待補)

### ⅲ. parameter

    (BODY)
    ※以下資料皆是使用者當下操作(掃描、手動輸入)時產生的資料

```csharp
    public struct NumberRecord
    {
        /// <summary>
        /// 上傳記錄鍵值(UUID)
        /// </summary>
        public string ID;
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
        /// 聯單號碼
        /// </summary>
        public string Number;
        /// <summary>
        /// 站所鍵值
        /// </summary>
        public int StationSN;
        /// <summary>
        /// 記錄時間(yyyyMMddHHmmssfff)
        /// </summary>
        public string RecordDateTime;
        /// <summary>
        /// 記錄來源類型(11：掃描器 12：手動輸入 13：相機拍照)
        /// </summary>
        public int SourceKind;
        /// <summary>
        /// 裝卸類型(1：上車 2：下車)
        /// </summary>
        public int ShipKind;
        /// <summary>
        /// 座標位置
        /// </summary>
        public Coordinate Coordinate;
    }
```

## 3. 呼叫示例

* 上傳記錄
> `http:// [hostname] /api/Record/Numbers`
>
>> ```json
>> {
>>     "ID": "4bf07297-65b2-45ca-b905-6fc6f2f39158",
>>     "Token": "fdsacxzvdafeqr",
>>     "UserID": "0914099788",
>>     "SelfKey": "124",
>>     "Number": "00000000",
>>     "StationSN": 3568,
>>     "RecordDateTime": "20180401124546548",
>>     "SourceKind": 12,
>>     "ShipKind": 2,
>>     "Coordinate":{
>>         "latitude": 23.697275,
>>         "longitude": 120.853412
>>     }
>> }
>> ```

## 4. 請求結果

依據呼叫端給予的資料，執行完成後(不論成功與否)，皆將資料內的鍵值回覆予呼叫端，呼叫端則依據回應訊息(ResponseCode)執行後續動作。

***

資料結構

```csharp
    public struct RecordResponseApply
    {
        /// <summary>
        /// 上傳記錄鍵值(UUID)
        /// </summary>
        public string ID;
        /// <summary>
        /// APP內部自存鍵值
        /// </summary>
        public string SelfKey;
        /// <summary>
        /// 聯單起站
        /// </summary>
        public string BeginStation;
        /// <summary>
        /// 聯單訖站
        /// </summary>
        public string EndStation;
        /// <summary>
        /// 車牌號碼
        /// </summary>
        public string MotorPlate;
    }
```

## 5. 回應信息示例

```json
{
    "Code": 1102,
    "Message": "鍵值重覆",
    "Data":{
        "ID": "4bf07297-65b2-45ca-b905-6fc6f2f39158",
        "SelfKey": "124",
        "BeginStation": "",
        "EndStation": "",
        "MotorPlate": ""
    }
}
```
