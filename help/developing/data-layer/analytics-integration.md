---
title: 使用Adobe用戶端資料層來整合核心元件和Adobe Analytics
description: 如何設定Adobe Analytics以註冊核心元件事件
translation-type: tm+mt
source-git-commit: f930a0d6004a29369b189137dd9c52e637ea3a61
workflow-type: tm+mt
source-wordcount: '1000'
ht-degree: 2%

---


# 使用Adobe用戶端資料層來整合核心元件和Adobe Analytics {#analytics-integration}

本檔案詳細說明如何設定以AEM、Adobe用戶端資料層、Adobe Launch和Adobe Analytics為基礎的端對端設定，以追蹤：

* 載入頁面時，儲存在Adobe用戶端資料層中的頁面ID
* 點按影像時儲存在Adobe用戶端資料層中的影像路徑

這會以核心元件為例，但可用於您自己的自訂元件。

##  步驟1 —— 在Adobe Analytics中建立報表套裝 {#create-report-suite}

若要匯整和分析資料，必須先建立報表套裝。

1. 前往 `https://analytics.adobe.com`.
1. 使用您的Adobe ID登入。
1. 按一下 **Analytics** 圖示。
1. 前往「管 **理員->報表套裝」**。
1. 按一 **下「建立新報表套裝」**。
1. 填寫表格：
   1. **報表套裝 ID**: `yourSuiteID`
   1. **網站標題**: `Your suite description`
   1. **時區**: 視情況而定
   1. **上線日期**: （視情況而定）
   1. **預計的每日頁面檢視次數**: 100或視情況而定
1. 按一 **下建立報表套裝**。

如果成功，您將會收到以下綠色訊息： `Report Suite <yourReportSuite> has been successfully created.`

## 步驟2 —— 顯示報表套裝 {#make-visible}

若要使用新的報表套裝，它必須可見。

1. 前往 `https://adminconsole.adobe.com`.
1. 使用您的Adobe ID登入。
1. 按一 **下Adobe Analytics - &lt;yourSite>卡**
1. 按一下 **Adobe Analytics - &lt;yourSite>連結**
1. 選擇「權 **限** 」頁籤
1. 按一下「 **報表** 套裝」列 **的「編輯」按鈕**
1. 按一下 **您在步驟1中建立的報表套** 裝的+按鈕 [，將其新增至「](#create-report-suite) 已包含權限項目」類別 **** 。
1. 按一下&#x200B;**「儲存」**。

## 步驟3 —— 將您的AEM網站與Adobe Launch整合 {#integrate-launch}

Launch必須與您的AEM網站整合，才能產生資料。

請依照「使用Adobe用戶 [端資料層來整合核心元件與Adobe Launch檔案」中的步驟](launch-integration.md) 。

## 步驟4 —— 在Adobe Launch中安裝及設定Adobe Analytics擴充功能 {#install-extension}

Adobe Analytics Extension可讓Analytics與Launch整合。

1. 在Adobe Launch中，選取您在步驟3中建立的新 [增屬性。](#integrate-launch)
1. 導覽至「擴充 **功能** 」標籤，然後選 **取「目錄」**。
1. 搜尋 **Adobe Analytics**。
1. 按一 **下安裝**。
1. 設定擴充功能。
   1. 輸入在 **步驟1中為適當環境建** 立的Analytics報表套裝ID [](#create-report-suite) 。
   1. 將字 **元集設** 定為UTF-8
1. 按一下「儲存」

## 步驟5 —— 在Adobe Launch中建立頁面ID的資料元素 {#create-data-element}

Launch中需要資料元素，才能追蹤頁面ID。

1. 在Adobe Launch中，選取在步驟3中建 [立的屬性。](#integrate-launch)
1. 選取「資 **料元素** 」標籤，然後按 **一下「新增資料元素**:
   1. **名稱**: `dl-page-id`
   1. **擴充功能**: **核心**
   1. **資料元素類型**: **自訂代碼**
1. 按一下「 **開啟編輯器」**
1. 在編輯器中，輸入代碼： `return adobeDataLayer.getState().page.id;`
1. 按一下&#x200B;**「儲存」**。
1. 按一 **下「儲存** 」以建立資料元素。

## 步驟6 —— 在Adobe Launch中建立規則以追蹤Analytics中的頁面ID {#track-page}

規則允許追蹤瀏覽屬性，例如Analytics中的頁面ID。

重複「使用 [Adobe用戶端資料層整合核心元件」和「Adobe Launch](launch-integration.md#launch-rule) 」檔案第5b部分的步驟，在Adobe Launch中新增下列規則：

* **名稱**: `track-dl-page-id`
* 事件：
   * **擴充功能**: **核心**
   * **事件類型**: **頁面底部**
* 動作1:
   * **擴充功能**: **Adobe Analytics**
   * **動作類型**: **設定變數**
   * **prop1**: `%dl-page-id%`
* 行動2:
   * **擴充功能**: **Adobe Analytics**
   * **動作類型**: **傳送信標**
   * 檢查 **s.t(): 將資料傳送至Adobe Analytics，並視為頁面檢視**

## 步驟7 —— 在Adobe Launch中建立規則以註冊影像點按事件 {#register-click}

規則允許追蹤瀏覽屬性，例如Analytics中的點按事件。

重複「使用 [Adobe用戶端資料層整合核心元件」和「Adobe Launch](launch-integration.md#launch-rule) 」檔案第5b部分的步驟，在Adobe Launch中新增下列規則：

* **名稱**: `register-dl-image-click`
* 事件：
   * **擴充功能**: **核心**
   * **事件類型**: **頁面底部**
* 動作1:
   * **擴充功能**: **核心**
   * **動作類型**: **自訂代碼**
   * 編輯器： 輸入下列程式碼

      ```
      var myListener = function(event) {
        _satellite.track('dlImageClicked', event.info.path);
      };
      adobeDataLayer.addEventListener('image clicked', myListener());
      ```

## 步驟8 —— 在Adobe Launch中建立規則以追蹤Analytics中的影像點按事件 {#track-click}

規則允許追蹤瀏覽屬性，例如Analytics中的點按事件。

重複「使用 [Adobe用戶端資料層整合核心元件」和「Adobe Launch](launch-integration.md#launch-rule) 」檔案第5b部分的步驟，在Adobe Launch中新增下列規則：

* **名稱**: `track-dl-image-click`
* 事件：
   * **擴充功能**: **核心**
   * **事件類型**: **直接呼叫**
   * **識別碼**: `dlImageClicked`
* 動作1:
   * **擴充功能**: **Adobe Analytics**
   * **動作類型**: **設定變數**
   * **prop2**: 設為 `%event.detail%`
* 行動2:
   * **擴充功能**: **Adobe Analytics**
   * **動作類型**: **傳送信標**
   * 檢查 **s.t(): 將資料傳送至Adobe Analytics，並視為頁面檢視**

## 步驟9 —— 將啟動程式碼發佈至您的網站 {#publish-launch}

若要在Launch中啟用這些規則和屬性的追蹤，必須發佈程式碼。

1. 在「 **Adobe Launch** 」標籤中，選取「 **Publishing** 」標籤。
1. 按一 **下「新增程式庫」**。
1. 在 **輸入** : `data-layer-analytics-1`.
1. 當「 **環境** 」選 **擇「開發（開發）**」。
1. 按一 **下「新增所有變更的資源」**。
1. 對於三個規則(`track-dl-page-id`和 `register-dl-image-click` 和 `track-dl-image-click`):
1. 選擇 **規則->規則->最新** ，然後單 **擊選擇並建立新修訂**。
1. 按一下&#x200B;**「儲存並為開發建立」**。

## 步驟10 —— 觸發您的頁面傳送資訊至Adobe Analytics {#trigger-page}

在此步驟中，您將安裝Chrome擴充 **功能Launch和DTM Switch**。 使用此擴充功能，您只需建立啟動程式碼並部署至開發環境。 不需要部署測試和生產環境。

1. 從Discovery安裝Chrome **擴充功能Launch和DTM Switch** 。
1. 按一下「 **啟動開關** 」圖示，並將「除錯」設 *為ON*。
1. 重新載入頁面 `http://<host>:<port>/content/core-components-examples/library/image.html`.
1. 開啟瀏覽器主控台，您會看到類似下列的內容。

![Analytics Console輸出](/help/assets/analytics-console-output.png)

>[!TIP]
>
>您也可以安裝 **Chrome的Experience Cloud Debugger** extension，以檢視Adobe Launch和Analytics的頁面相關特定資訊。

## 步驟11 —— 在Adobe Analytics中檢視追蹤資訊 {#view-info}

現在，您可以在Adobe Analytics中檢視您觸發的事件。

1. 前往 `https://analytics.adobe.com`.
1. 使用您的Adobe ID登入。
1. 按一下 **Analytics** 圖示。
1. 選擇「報 **表** 」標籤。
1. 在右上角的下拉式清單中，選取您在步驟1中建立的 [報表套裝。](#create-report-suite)
1. 在第一欄中，選取「 **自訂流量->自訂流量1-10 ->自訂分析1** 」，以檢視儲存在資料層中的追蹤頁面ID（路徑）。 它應該如下所示。

   ![自訂分析1](/help/assets/custom-insight-1.png)

1. 存取自 **訂分析2** ，以檢視儲存在資料層中的追蹤影像路徑。 它應該如下所示。

   ![自訂分析2](/help/assets/custom-insight-2.png)
