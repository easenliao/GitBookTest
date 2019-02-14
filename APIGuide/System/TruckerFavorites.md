# 取得司機我的最愛更新資料

## 1. 路徑

*hostname*/api/**System/Truckers/FavoriteStation**

## 2. 參數

### ⅰ. Method

    GET

### ⅱ. header

    (待補)

### ⅲ. parameter

    (URI)
    DataVersion: 資料版本

## 3. 呼叫示例

* 取得全部資訊
> `http:// [hostname] /api/System/Truckers/FavoriteStation?DataVersion=0`

* 取得特定版本之後的資訊
> `http:// [hostname] /api/System/Truckers/FavoriteStation?DataVersion=636595678729700489`

## 4. 請求結果

依據呼叫端請求時給予的資料版本，與目前的資料版本做比對，凡有異動過司機站所關聯，會以司機為群組，重新將司機所擁有的整組站所關聯回傳。

***

資料結構

* TruckerStationData
  * DataVersion：資料版本，其值為更新時間的 Ticks 值
  * TruckerStations：有異動的司機資料
* TruckerStation
  * ID：司機鍵值
  * StationSNs：司機所擁有的站所鍵值

```csharp
    public struct TruckerStationData
    {
        public long DataVersion;
        public IEnumerable<TruckerStation> TruckerStations;
    }

    public struct TruckerStation
    {
        public string ID;
        public IEnumerable<int> StationSNs;
    }
```

## 5. 回應信息示例

```json
{
    "Code": 0,
    "Message": "",
    "Data":{
        "DataVersion": 636595703218851725,
        "TruckerStations":[
            {
                "Id": "0914099788",
                "StationSNs":[
                    253,
                    458,
                    789
                ]
            }
        ]
    }
}
```