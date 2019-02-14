# 上傳定位資訊

## 1. 路徑

*hostname*/api/**Location/Coordinate**

## 2. 參數

### ⅰ. Method

    POST

### ⅱ. header

    (待補)

### ⅲ. parameter

    (BODY)

```csharp
    public struct CoordinateRecord
    {
      /// <summary>
      /// 使用者帳號
      /// </summary>
      public string UserID;
      /// <summary>
      /// 記錄時間(yyyyMMddHHmmssfff)
      /// </summary>
      public string RecordDateTime;
      /// <summary>
      /// 座標位置
      /// </summary>
      public Coordinate Coordinate;
    }
```

## 3. 呼叫示例

* 上傳記錄
> `http:// [hostname] /api/Location/Coordinate`
>
>> ```json
>> {
>>     "UserID": "0914099788",
>>     "RecordDateTime": "20180401124546548",
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
    public struct CoordinateRecord
    {
      /// <summary>
      /// 使用者帳號
      /// </summary>
      public string UserID;
      /// <summary>
      /// 記錄時間(yyyyMMddHHmmssfff)
      /// </summary>
      public string RecordDateTime;
      /// <summary>
      /// 座標位置
      /// </summary>
      public Coordinate Coordinate;
    }
```

## 5. 回應信息示例

```json
{
    "Code": 0,
    "Message": "",
    "Data": {
        "UserID": "0914099788",
        "RecordDateTime": "20180401124546548",
        "Coordinate": {
            "Latitude": 23.697275,
            "Longitude": 120.853412
        }
    }
}
```
