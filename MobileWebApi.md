<!-- # Web Api For Mobile (Client Request)

## 取得更新檔
### GET API/GetUpdata
```
String hwID               硬體ID
String appVer             APP版本
String token              驗證資訊
String appServiceVer      一般版/盤點機版本
```
## 以經緯度取得鄰近站所清單
### GET API/NearOffices
```
String token

String latitude           緯度
String longitude          經度
```
## 回報條碼異常
### PUT API/xxxxx
```
String token
String barcode

String uuID               單號
```
## 上傳條碼(上車/下車)
### POST [Frombody] API/xxxxx
```
String token
String barcode
String uuID
String latitude
String longitude

int operation             輸入方式
int officeID              站所ID
int handling              上/下車
String dateTime           時間
```

## 無條碼紀錄(上車/下車)
### POST [Frombody] API/xxxxx
```
String token
String barcode
String uuID
String latitude
String longitude
int operation         
int officeID              
int handling              
String dateTime          
```
## 上傳照片
### POST [From] API/xxxxx
```
String token
String barcode
String uuID
String latitude
String longitude
String dateTime

String base64photo 圖片字串
```
## 取得未載車原因清單
### GET API/xxxxx
```
String token
String dateTime
```
## 取得無貼紙標籤原因清單
### GET API/xxxxx
```
String token
String dateTime
```
## 取得聯單
### GET
```
String token
String uuID
```
## 掃描紀錄
### POST
```
String token
String barcode
String latitude
String longitude
String uuID
String dateTime
String officeID
``` -->
