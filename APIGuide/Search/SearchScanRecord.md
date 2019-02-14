# 查詢掃描記錄

## 1. 路徑

*hostname*/api/**Record/Numbers**

## 2. 參數

### ⅰ. Method

    GET

### ⅱ. header

    (待補)

### ⅲ. parameter

    (URI)
    ScanDate：掃描日期

## 3. 呼叫示例

* 取得掃描記錄
> `http:// [hostname] /api/Record/Numbers?ScanDate=20180327`

## 4. 請求結果

依據呼叫端請求的日期，回傳指定日期的掃描記錄，其日期僅限七日內，若超過七日，則會回應無效參數。

***

資料結構

```csharp
    public struct ScanRecord
    {
        /// <summary>
        /// 聯單號碼
        /// </summary>
        public string Number;
        /// <summary>
        /// 站所名稱
        /// </summary>
        public string StationTitle;
        /// <summary>
        /// 記錄時間(yyyy-MM-dd)
        /// </summary>
        public string RecordDate;
        /// <summary>
        /// 裝卸類型(1：上車 2：下車)
        /// </summary>
        public int ShipKind;
    }
```

## 5. 回應信息示例

```json
{
    "Code": 0,
    "Message": "",
    "Data": [
        {
            "Number": "123456",
            "StationTitle": "台中振益",
            "RecordDate": "20180330101218278",
            "ShipKind": 0
        }
    ]
}
```