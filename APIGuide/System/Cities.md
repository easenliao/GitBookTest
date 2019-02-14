# 取得縣市資料

## 1. 路徑

*hostname*/api/**System/Cities**

## 2. 參數

### ⅰ. Method

    GET

### ⅱ. header

    (待補)

### ⅲ. parameter

    無

## 3. 呼叫示例

* 取得全部資訊
> `http:// [hostname] /api/System/Cities`

## 4. 請求結果

呼叫端請求時，會收到全部的資訊，該項資訊幾乎不會異動。

***

資料結構

* CityData
  * DataVersion：資料版本，其值為更新時間的 Ticks 值
* City
  * SN：鍵值
  * Title：名稱
  * Seq：City 排序
* Area
  * SN：鍵值
  * Title：名稱
  * Seq：Area 排序

```csharp
    public struct CityData
    {
        public long DataVersion;
        public IEnumerable<City> Cities;
    }

    public struct City
    {
        public int SN;
        public string Title;
        public int Seq;
        public IEnumerable<Area> Areas;
    }

    public struct Area
    {
        public int SN;
        public string Title;
        public int Seq;
    }
```

## 5. 回應信息示例

```json
{
    "Code": 0,
    "Message": "",
    "Data": {
        "DataVersion": 636595013817220049,
        "Cities": [
            {
                "Sn": 3,
                "Title": "臺北市",
                "Seq": 1,
                "Areas": [
                    {
                        "Sn": 1,
                        "Title": "中正區",
                        "Seq": 1
                    },
                    {
                        "Sn": 2,
                        "Title": "大同區",
                        "Seq": 2
                    }
                ]
            },
            {
                "Sn": 4,
                "Title": "新北市",
                "Seq": 2,
                "Areas": [
                    {
                        "Sn": 20,
                        "Title": "萬里區",
                        "Seq": 1
                    },
                    {
                        "Sn": 21,
                        "Title": "金山區",
                        "Seq": 2
                    }
                ]
            }
        ]
    }
}
```