# 查詢聯單

## 1. 路徑

*hostname*/api/**Record/SheetApplys**

### 2. 參數

### ⅰ. Method

    GET

### ⅱ. header

    (待補)

### ⅲ. parameter

    (URI)
    Key : 聯單號碼或車牌

## 3. 呼叫示例

* 取得掃描記錄
> `http:// [hostname] /api/Record/SheetApply?searchKey=00650275`

## 4. 請求結果

依據呼叫端請求的聯單號碼或車牌，回傳指定聯單記錄。

***

資料結構

```csharp
    public struct SheetApply
    {
        /// <summary>
        /// 託運日期(yyyy-MM-dd)
        /// </summary>
        public string SendDateText;
        /// <summary>
        /// 聯單號碼
        /// </summary>
        public string SheetNumber;
        /// <summary>
        /// 車牌
        /// </summary>
        public string LicensePlate;
        /// <summary>
        /// 付款說明
        ///</summary>
        public string AmountDescription;
        /// <summary>
        /// 起站資訊
        /// </summary>
        public BeginLocation BeginLocation;
        /// <summary>
        /// 到站資訊
        /// </summary>
        public EndLocation EndLocation;
    }
```

## 5. 回應信息示例

```json
{
    "Code": 0,
    "Message": "",
    "Data": [
        {
            "SendDateText": "2018-02-27",
            "SheetNumber": "00650275",
            "LicensePlate": "MCP-0005",
            "AmountDescription": "付清",
            "BeginLocation": {
                "RouteTitle": "北花直達",
                "LocationTitle": "羅東站",
                "CustomAddress": ""
            },
            "EndLocation": {
                "RouteTitle": "縱貫直達",
                "LocationTitle": "新竹車站",
                "CustomAddress": ""
            }
        }
    ]
}
```
