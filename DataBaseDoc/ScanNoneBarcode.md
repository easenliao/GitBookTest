### ScanNoneBarcode 無條碼紀錄

```
名稱            數據類型     長度     對應資料
PK              INT         (11)    各資料主鍵Key
Type            INT         (11)    未載車原因
貼紙飛走 21/無貼紙標籤 20/無條碼 31/到站標示不清  32/龍頭鎖住 33
Datetime        VARCHAR     (17)    紀錄時間
DriverSN        INT         (11)    司機SN
BranchOfficeSN  INT         (11)    站所SN
Latitude        Double      ()      緯度
Longitude       Double      ()      經度
UUID            VARCHAR     (50)    無條碼紀錄UUID
Handing         INT         (11)    上下車(1上車)/(0下車)
```
