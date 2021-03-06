---

copyright:
  years: 2017
lastupdated: "2018-03-14"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# 監視度量值

負載平衡器會監視下列度量值： 

* 傳輸量
* 作用中連線
* 連線速率

這些度量值會視覺化為可以選取**監視**標籤來檢視的圖形，而且可以透過程式設計方式將其用作時間序列資料點，方法為使用 `getListenerTimeSeriesData` API。

每個資料點都包含 UNIX Epoch 時間中的時間戳記，以及結束於該時間戳記之該時間間隔的度量值。使用者可以指定通訊協定，以及將在其間報告度量值的時間間隔。 

支援的通訊協定包括：

* HTTP
* HTTPS
* TCP

指定通訊協定會依該通訊協定過濾度量值。

比方說，如果未指定任何通訊協定，且度量值為*傳輸量*，則會報告所有通訊協定的總傳輸量。

如果通訊協定為 *HTTP*，則只會報告 HTTP 資料流量的傳輸量。

使用者也可以指定將在其間報告度量值的時間間隔。支援的時間間隔如下： 

* 1 小時
* 6 小時
* 12 小時
* 24 小時
* 1 週
* 2 週

對於每一個時間間隔，報告的資料點數目大略相同。  
比方說，如果間隔為 1 小時，則每一個資料點代表 5 分鐘的資料。

如果間隔為 2 週，則每一個資料點代表 24 小時的資料。

下表顯示如何從時間間隔衍生資料點：

| 時間間隔 | 資料點精準度 | 資料點數目 |                                                                                              
| ------------------------------------------ | --------------------------------------------------- | -------------------|
| 1 小時    | 5 分鐘 | 12   |
| 6 小時   | 30 分鐘 | 12  |
| 12 小時  | 1 小時 | 12 |
| 24 小時  | 2 小時 | 12 |
| 1 週    | 12 小時 | 12 |
| 2 週  | 24 小時 | 12 |

# 如何啟用度量值監視

若要擷取監視度量值，您必須鏈結 SoftLayer 帳戶與 Bluemix 帳戶。如需相關資訊，請參閱 [Softlayer 鏈結](https://console.bluemix.net/docs/account/softlayerlink.html#switching-to-ibmid)。
