# 取得要更新的資源

## 1. 路徑

*hostname*/api/**System/Unities**

## 2. 參數

### ⅰ. Method

    GET

### ⅱ. header

    (待補)

### ⅲ. parameter

    無

## 3. 呼叫示例

* 取得全部資訊
> `http:// [hostname] /api/System/Unities`

## 4. 請求結果

呼叫端請求時，皆會收到目前各項資料表的最新版本。

***

資料結構

* UnityData
  * DataVersion：資料版本，其值為更新時間的 Ticks 值
* Unity
  * Table：資源表格名稱
  * DataVersion：資源表格更新時間的 Ticks 值

```csharp
    public struct UnityData
    {
        public long DataVersion;
        public IEnumerable<Unity> Unities;
    }

    public struct Unity
    {
        public string Table;
        public long DataVersion;
    }
```

## 5. 回應信息示例

```json
{
    "Code": 0,
    "Message": "",
    "Data":{
        "DataVersion": 636595596163288300,
        "Unities":[
            {
                "Table": "Category",
                "DataVersion": 636595596163248868
            },
            {
                "Table": "City",
                "DataVersion": 636595596163288158
            },
            {
                "Table": "Station",
                "DataVersion": 636595596163288286
            },
            {
                "Table": "TruckerStation",
                "DataVersion": 636595596163288293
            }
        ]
    }
}
```