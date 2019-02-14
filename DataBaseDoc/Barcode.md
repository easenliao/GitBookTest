### Barcode 條碼紀錄

```
名稱            數據類型     長度     對應資料
PK              INT         (11)    各資料主鍵Key
Datetime        VARCHAR     (17)    條碼紀錄時間
Barcode         VARCHAR     (10)    條碼
ShipMentApplySN INT         (11)    聯單SN
DriverSN        INT         (11)    司機SN
BranchOfficeSN  INT         (11)    站所SN
HwID            VARCHAR     (50)    設備ID
Latitude        Double      ()      緯度
Longitude       Double      ()      經度
Handing         INT         (11)    上下車(0下車)/(1上車)
IssueBarcode    INT         (11)    問題條碼
IssueOffice     INT         (11)    問題站所
BarcodeEdit     INT         (11)    條碼編輯
OfficeEdit      INT         (11)    站所編輯
UUID            VARCHAR     (50)    條碼紀錄UUID
Operation       TINYINT     (4)     掃描器(1自動)/(2手動)
TruckNum        VARCHAR     (50)    車牌

```
