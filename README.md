# Fugle Realtime API

Fugle Realtime API 是由時報資訊與[Fugle](https://www.fugle.tw/) 技術團隊開發提供，詳細文件請參閱[Intraday](./INTRADAY.md)。  
即時行情資料來源為臺灣證券交易所、臺灣期貨交易所及財團法人中華民國證券櫃檯買賣中心。請您詳閱相關使用[規範與聲明](https://github.com/fortuna-intelligence/fugle-realtime-docs#Statement-中文使用規範與聲明)。

* [Price](#price)
* [Libraries](#libraries)
* [More Information](#more-Informatio)
* [Contact Fugle](#contact-Fugle)
* [Statement](#Statement)

## Price
|  | Demo | 富果帳戶[如何取得](https://www.fugle.tw/events/trade-landing-page/) |
|:--|:--|:--|
| Request / min | 60 | 60 |
| Websocket limit | 1 | 5 |
| Content | only 2884(玉山金) | 上市股票 <br/> 上櫃股票 <br/> 興櫃股票 <br/> 指數 <br/> ETF <br/> 權證 <br/> ETN |
| Price |  free |  free |

## Libraries
| language | github  |
|:---|:---|
| Node.js | [fugle-realtime-node](https://github.com/fugle-dev/fugle-realtime-node)  |
| Python | [fugle-realtime-python](https://github.com/fugle-dev/fugle-realtime-python)  |
| Python Demo | [fugle-realtime-demo](https://github.com/fugle-dev/fugle-realtime-demo/) |


## Unofficial & Community Libraries

以下清單所列項目來自技術社群夥伴，而非由 Fugle 富果團隊開發或維護，因此官方無法提供支援或維護，也並未審閱其內容，亦不能提供擔保或推薦。 請您自行判斷其提供的資訊，並自行承擔使用後所生之任何風險與損失。

| language | github  |
|:---|:---|
| Ruby | [elct9620/fugle-api](https://github.com/elct9620/fugle-api) |
| Rust | [tommady/fugle-rs](https://github.com/tommady/fugle-rs) |


## More Information
* [Index ID List](https://developer.fugle.tw/document/indexIdList)
* [Realtime Status](https://developer.fugle.tw/document/status)


## Contact Fugle
* [Telegram](https://t.me/fugle_realtime_api)
* [Form](https://www.fugle.tw/contact)
* [service@fugle.tw](mailto:service@fugle.tw)


## Statement 中文使用規範與聲明
1. 透過本服務取得之行情資料僅供參考，成交值及成交量不含零股及鉅額交易，使用者依本資料交易發生交易損失需自行負責。
2. 時報資訊與群馥科技對資料內容錯誤、更新延誤或傳輸中斷不負任何責任。您應對您所為之任何金融或投資決策自行負責。
3. 使用者應遵守[臺灣證券交易所股份有限公司交易資訊使用管理辦法](http://www.selaw.com.tw/LawArticle.aspx?LawID=G0100124)、[臺灣期貨交易所股份有限公司交易資訊使用管理辦法](http://www.selaw.com.tw/LawArticle.aspx?LawID=G0101422)、[財團法人中華民國證券櫃檯買賣中心有價證券交易資訊使用管理辦法](http://www.selaw.com.tw/LawArticle.aspx?LawID=G0100766)、各資訊來源提供者所定之資訊使用相關規範及智慧財產權相關法令，如有盜接、轉接交易資訊，或以其他方式出售、出租、轉讓、再授權交易資訊，或將交易資訊另行取樣並編製指數、其他衍生性商品或將之傳送予第三人，應負違約及侵權之相關民、刑事責任。
4. 使用者須遵守臺灣證券交易所「[交易資訊使用管理辦法](https://www.twse.com.tw/downloads/zh/products/regulation_use.pdf)」等交易資訊管理相關規定，所有資訊以臺灣證券交易所公告資料為準。

provided by [Fugle](https://www.fugle.tw/)
