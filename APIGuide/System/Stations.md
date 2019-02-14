# 取得站所更新資料

## 1. 路徑

*hostname*/api/**System/Stations**

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
> `http:// [hostname] /api/System/Stations?DataVersion=0`

* 取得特定版本之後的資訊
> `http:// [hostname] /api/System/Stations?DataVersion=636595678729700489`

## 4. 請求結果

依據呼叫端請求時給予的資料版本，與目前的資料版本做比對，整理兩者有差異的部份。

***

資料結構

* StationData
  * DataVersion：資料版本，其值為更新時間的 Ticks 值
  * IncreasedInstances：新增或內容有修改的站所資料
  * RemovedKeys：標示為移除的站所資料鍵值
* Station
  * SN：鍵值
  * OfficeTitle：站名
  * Storetitle：店名
  * CitySN：縣市鍵值
  * AreaSN：行政區域鍵值
  * Address：地址
  * Coordinate：座標位置
  * IsOnlyPayOff： true 表示不可到付
  * IsNotUnload： true 表示只收不下

```csharp
    public struct StationData
    {
        public long DataVersion;
        public IEnumerable<Station> IncreasedInstances;
        public IEnumerable<int> RemovedKeys;
    }

    public struct Station
    {
        public int SN;
        public string OfficeTitle;
        public string StoreTitle;
        public int CitySN;
        public int AreaSN;
        public string Address;
        public Coordinate Coordinate;
        public bool IsOnlyPayOff;
        public bool IsNotUnload;
    }
```

## 5. 回應信息示例

```json
{
    "Code": 0,
    "Message": "",
    "Data":{
        "DataVersion": 636595678729700489,
        "IncreasedInstances":[
            {
                "Sn": 374,
                "OfficeTitle": "南投信義站",
                "StoreTitle": "李王順車業",
                "CitySN": 10,
                "AreaSN": 178,
                "Address": "南投縣信義鄉明德街19號",
                "Coordinate":{
                    "Latitude": 23.697275,
                    "Longitude": 120.853412
                },
                "IsOnlyPayOff": true,
                "IsNotUnload": false
            },
            {
                "Sn": 2139,
                "OfficeTitle": "南投士林站",
                "StoreTitle": "士林車業(舊:江北)",
                "CitySN": 10,
                "AreaSN": 168,
                "Address": "南投縣南投市彰南路一段637號",
                "Coordinate":{
                    "Latitude": 23.896209,
                    "Longitude": 120.6867858
                },
                "IsOnlyPayOff": true,
                "IsNotUnload": false
            }
        ],
        "RemovedKeys":[]
    }
}
```