# ResponseMessage

作用於伺服器接收請求並完成後，將回傳一組訊息(含請求結果)予呼叫端

## 規格

回應信息內含三個資訊

* 回應代碼
* 附加訊息
* 請求結果

```csharp
    public struct APIResponse<T>
    {
        public APIResponseCode Code;
        public string Message;
        public T Data;
        // 略 … …
    }
```

### 1. 回應代碼 (APIResponseCode)

用以說明 API 完成請求的狀態

| Code | Text  | Descript |
| ---: | :---- | :---- |
|    0 | 成功 | 正確完成呼叫端請求 |
|  101 | 沒有請求結果 | 完成呼叫端請求，但該請求沒有任何結果 |
|  201 | 請求參數空白 | 至少需要一個有效參數，詳細狀況需視各 API 而定 |
|  301 | Header 失效 | 檢查 Http Request Header 資料時，有不符或遺漏 |
|  351 | 操作錯誤 | 執行呼叫端的請求時，因不明原因發生例外錯誤 |
| 1101 | 資料重覆 | 欲存入資料庫的資料已存在 |
| 1102 | 鍵值重覆 | 欲存入資料庫的鍵值已存在，存入的資料與相同鍵值的資料不同 |

### 2. 附加訊息

用以補充 API 完成請求的訊息

### 3. 請求結果

呼叫端取用的結果