# 取得廠商更新資料

## 1. 路徑

*hostname*/api/**System/Companies**

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
> `http:// [hostname] /api/System/Companies?DataVersion=0`

* 取得特定版本之後的資訊
> `http:// [hostname] /api/System/Companies?DataVersion=636595678729700489`

## 4. 請求結果

依據呼叫端請求時給予的資料版本，與目前的資料版本做比對，整理兩者有差異的部份。

***

資料結構

* CompanyData
  * DataVersion：資料版本，其值為更新時間的 Ticks 值
  * IncreasedInstances：新增或內容有修改的站所資料
  * RemovedKeys：標示為移除的站所資料鍵值
* Company
  * SN：鍵值
  * Kind: 廠商類型
  * Title：名稱

```csharp
    public struct CompanyData
    {
        public long DataVersion;
        public IEnumerable<Company> IncreasedInstances;
        public IEnumerable<int> RemovedKeys;
    }

    public struct Company
    {
        public int SN;
        public string Kind;
        public string Title;
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
                "Kind": "類型一",
                "Title": "廠商名稱一"
            },
            {
                "Sn": 2139,
                "Kind": "類型二",
                "Title": "廠商名稱二"
            }
        ],
        "RemovedKeys":[]
    }
}
```