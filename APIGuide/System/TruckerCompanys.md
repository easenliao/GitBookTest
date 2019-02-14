# 取得司機廠商更新資料

## 1. 路徑

*hostname*/api/**System/Truckers/Company**

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
> `http:// [hostname] /api/System/Truckers/Company?DataVersion=0`

* 取得特定版本之後的資訊
> `http:// [hostname] /api/System/Truckers/Company?DataVersion=636595678729700489`

## 4. 請求結果

依據呼叫端請求時給予的資料版本，與目前的資料版本做比對，凡有異動過司機廠商關聯，會以司機為群組，重新將司機所擁有的整組廠商關聯回傳。

***

資料結構

* TruckerCompanyData
  * DataVersion：資料版本，其值為更新時間的 Ticks 值
  * TruckerCompanies：有異動的司機資料
* TruckerCompany
  * ID：司機鍵值
  * CompanySNs：司機所擁有的廠商鍵值

```csharp
    public class TruckerCompanyData
    {
        public long DataVersion;
        public IEnumerable<TruckerCompany> TruckerCompanies;
    }

    public class TruckerCompany
    {
        public string ID;
        public IEnumerable<int> CompanySNs;
    }
```

## 5. 回應信息示例

```json
{
    "Code": 0,
    "Message": "",
    "Data":{
        "DataVersion": 636595703218851725,
        "TruckerCompanies":[
            {
                "Id": "0914099788",
                "CompanySNs":[
                    1,
                    2,
                    3
                ]
            }
        ]
    }
}
```