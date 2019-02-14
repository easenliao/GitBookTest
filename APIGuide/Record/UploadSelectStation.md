# 上傳站所選擇記錄

## 1. 路徑

*hostname*/api/**Record/Locations**

## 2. 參數

### ⅰ. Method

    POST

### ⅱ. header

    (待補)

### ⅲ. parameter

    (BODY)
    ※以下資料皆是使用者當下操作時產生的資料

```csharp
    public struct LocationRecord
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
        public string selfKey;
        /// <summary>
        /// 選擇的站所鍵值
        /// 手動輸入的站所鍵值為0
        /// </summary>
        public int SelectedStationSN;
        /// <summary>
        /// 選擇的站所名稱
        /// </summary>
        public string SelectedStationTitle;
        /// <summary>
        /// 系統判斷站所鍵值
        /// </summary>
        public IEnumerable<int> AutoStationSNs;
        /// <summary>
        /// 座標位置
        /// </summary>
        public Coordinate Coordinate;
        /// <summary>
        /// 記錄時間(yyyyMMddHHmmssfff)
        /// </summary>
        public string RecordDateTime;
    }
```

## 3. 呼叫示例

* 上傳記錄
> `http:// [hostname] /api/Record/Locations`
>
>> ```json
>> {
>>     "ID": "4bf07297-65b2-45ca-b905-6fc6f2f39158",
>>     "Token": "fdsacxzvdafeqr",
>>     "UserID": "0914099788",
>>     "SelfKey": "124",
>>     "SelectedStationSN": 3568,
>>     "SelectedStationTitle": "台中西屯站",
>>     "AutoStationSNs":[
>>          12,
>>          6984,
>>          4258
>>     ],
>>     "RecordDateTime": "20180401124546548",
>>     "Coordinate":{
>>         "latitude": 23.697275,
>>         "longitude": 120.853412
>>     }
>> }
>> ```

## 4. 請求結果

依據呼叫端給予的資料，執行完成後(不論成功與否)，皆將資料內的鍵值回覆予呼叫端，若失敗，則重新上傳。

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
