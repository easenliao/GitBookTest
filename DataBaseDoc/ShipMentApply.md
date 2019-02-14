### 聯單紀錄

```
SN              INT         (11)    聯單主鍵Key
ShipMentApplySN INT         (11)    聯單SN
ApplyType       INT         (11)    聯單類型
ApplyDateTime   VARCHAR     (17)    聯單入單時間
SendDateTime    VARCHAR     (17)    託運開始時間
StartDateTime   VARCHAR     (17)    開始時間
StopDateTime    VARCHAR     (17)    結束時間
SheetNumber_Sys VARCHAR     (20)
SheetNumberSN   INT         (11)    條碼紀錄SN
SheetNumber     VARCHAR     (20)    條碼
SourceType_Sour INT         (11)
SourceType_Dest INT         (11)
TableSN_Sour    INT         (11)    起站SN
TableSN_Dest    INT         (11)    到站SN
FactorSN_Sour   INT         (11)
FactorSN_Dest   INT         (11)
CustTitle_Sour  VARCHAR     (50)
CustTitle_Dest  VARCHAR     (50)
SenderName      VARCHAR     (50)    寄車人姓名
Sender_Tel      VARCHAR     (50)    寄車仁電話
Receiver_Name   VARCHAR     (50)    收車人姓名
Receiver_Tel    VARCHAR     (50)    收車人電話
ItemType        INT         (11)    車種類型
LicensePlate    VARCHAR     (100)   車牌
MotorBrand      VARCHAR     (50)    機車品牌
CC              VARCHAR     (50)    CC數
Color           VARCHAR     (50)    顏色
Qty             INT         (11)    包裝方式
SpecialMotorcycleSN INT     (11)    特殊車種SN
IsAssign        INT         (11)    
Amount          DECIMAL     (10,0)  金額
Amount_Collate  DECIMAL     (10,0)  點收金額
Amount_Take     DECIMAL     (10,0)  實收金額
IsCOD           INT         (11)    是否到付
IsPack          INT         (11)    是否包裝
DistcountType   INT         (11)    折扣類型
Remark          VARCHAR     (200)   備註
Comment         VARCHAR     (200)   意見
Status          INT         (11)
AccountStatus   INT         (11)
IsSelfSend      INT         (11)
IsOrderCar      INT         (11)
IsCheckSheetNum INT         (11)
IsInvalid       INT         (11)
InvalidType     INT         (11)
IsCompany_Sour  INT         (11)
IsCompany_Dest  INT         (11)
IsReceiver      INT         (11)
IsBack          INT         (11)
IsDel           INT         (11)
```
