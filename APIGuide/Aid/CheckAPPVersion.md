# 檢查 APP 版本

## 1. 路徑

*hostname*/api/**System/GetApKVersion**

## 2. 參數

### ⅰ. Method

    GET

### ⅱ. header

    (待補)

### ⅲ. parameter

    (URI)
    ApkVersionCode：Apk 版本序

## 3. 呼叫示例

> `http:// [hostname] /api/System/GetApKVersion?ApkVersionCode=3`

## 4. 請求結果

比對呼叫端傳送的 Apk Code，來判斷是否需要更新，若要更新，則回傳完整資訊，。

***

資料結構

```csharp
    public struct ApkVersion
    {
        /// <summary>
        /// Apk 版本序
        /// </summary>
        public int VersionCode;
        /// <summary>
        /// Apk 版本名稱
        /// </summary>
        public string VersionName;
        /// <summary>
        /// Apk 檔案路徑
        /// </summary>
        public string FileUrl;
    }
```

## 5. 回應信息示例

```json
{
    "Code": 0,
    "Message": "",
    "Data":{
      "VersionCode": "2",
      "VersionName": "1.1.1",
      "FileUrl": "http://xxx.hostname.com/filename.apk"
    }
}
```
