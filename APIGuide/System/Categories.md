# 取得代碼選項資料

## 1. 路徑

*hostname*/api/**System/Categories**

## 2. 參數

### ⅰ. Method

    GET

### ⅱ. header

    (待補)

### ⅲ. parameter

    無

## 3. 呼叫示例

* 取得全部資訊
> `http:// [hostname] /api/System/Categories`

## 4. 請求結果

呼叫端請求時，會收到全部的資訊，該項資訊很少異動。

***

資料結構

* CategoryData
  * DataVersion：資料版本，其值為更新時間的 Ticks 值
* Category
  * Key：鍵值
  * Title：名稱
* CategoryCode
  * Key：鍵值
  * Title：名稱
  * Seq：Code 排序

```csharp
    public struct CategoryData
    {
        public long DataVersion;
        public IEnumerable<Category> Categories;
    }

    public struct Category
    {
        public string Key;
        public string Title;
        public IEnumerable<CategoryCode> CategoryCodes;
    }

    public struct CategoryCode
    {
        public string Key;
        public string Title;
        public int Seq;
    }
```

## 5. 回應信息示例

```json
{
    "Code": 0,
    "Message": "",
    "Data":{
        "DataVersion": 636595558971000776,
        "Categories":[
            {
                "Key": "01",
                "Title": "無貼紙標籤原因",
                "CategoryCodes":[
                    {
                        "Key": "0101",
                        "Title": "貼紙飛走",
                        "Seq": 1
                    },
                    {
                        "Key": "0102",
                        "Title": "無使用條碼貼紙",
                        "Seq": 2
                    }
                ]
            },
            {
                "Key": "02",
                "Title": "未載車原因",
                "CategoryCodes":[
                    {
                        "Key": "0201",
                        "Title": "無條碼",
                        "Seq": 1
                    },
                    {
                        "Key": "0202",
                        "Title": "到站標識不清",
                        "Seq": 2
                    },
                    {
                        "Key": "0203",
                        "Title": "龍頭鎖住",
                        "Seq": 3
                    },
                    {
                        "Key": "0204",
                        "Title": "未簽同意書",
                        "Seq": 4
                    }
                ]
            }
        ]
    }
}
```