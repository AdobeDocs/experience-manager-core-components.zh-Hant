---
title: 使用Adobe用戶端資料層來整合核心元件和Adobe Launch
description: 如何設定Adobe Launch，以使用Adobe Launch註冊核心元件事件
translation-type: tm+mt
source-git-commit: f930a0d6004a29369b189137dd9c52e637ea3a61
workflow-type: tm+mt
source-wordcount: '1160'
ht-degree: 1%

---


# 使用Adobe用戶端資料層來整合核心元件和Adobe Launch {#launch-integration}

核心元件可透過Adobe用戶端資料層與Adobe Launch整合。 本檔案說明如何設定Adobe Launch，以追蹤影像元件的點按事件。

設定好後，當按一下核心影像元件時，Launch會在瀏覽器主控台中產生下列輸出。

![控制台輸出示例](/help/assets/launch-console-output.png)

## 啟動與AEM的整合 {#launch-aem}

第一個Adobe Launch必須與您的AEM網站整合。

### 步驟1 —— 在Adobe I/O中建立整合 {#create-io-integration}

首先登入Adobe I/O以開始設定整合。

1. 前往 `https://console.adobe.io`.
1. 使用您的Adobe ID登入。
1. 在「快速入門」區段中，按一下「 **建立整合」**。
1. Select **Access an API** and click **Continue**.
1. 在Adobe Experience Platform下 **方選取Experience Platform Launch API** ，然後按一下「 **繼續**」。

### 步驟2 —— 在AEM中建立IMS設定 {#ims-configuration}

在AEM中，您必須定義您在Adobe I/O中開始設定的整合。

1. 前往AEM首頁，按一下「 **工具->安全性-> Adobe IMS設定」**。
1. 按一下&#x200B;**建立**。
1. 身為 **Cloud Solution**，請選 **取Adobe Launch**。
1. 勾選 **建立新憑證**。
1. 輸入憑證的別名， **例如aem-launch-certificate**。
1. 按一 **下「建立憑證** 」，然後在快顯視窗中按一下「 **確定** 」以建立憑證。
1. 按一 **下「下載公開金鑰** 」，然後在快顯視窗中按一下「 **下載」**。

### 步驟3 —— 完成Adobe I/O配置 {#finish-io}

使用在AEM IMS設定中建立的憑證和金鑰，您就可以完成Adobe I/O設定。

1. 依照步驟1返回Adobe I/O [主控台。](#create-io-integration)
1. 在「建 **立新的整合** 」視窗中，輸入名稱和說明，例如 **AEM Launch資料層**。
1. 在「 **公開金鑰憑證**」下，上傳您在步驟2中建立 [的憑證。](#ims-configuration)
1. 選取「 **啟動——產品」(Launch - Prod)配置檔案**。
1. Click **Create integration**.
1. 按一 **下「繼續」以取得整合詳細資訊**。 您稍後將需要這些詳細資訊，才能在AEM例項中完成IMS設定。

### 步驟4 —— 完成IMS設定 {#finish-ims}

透過Adobe I/O整合詳細資訊，您可以完成AEM IMS設定。

1. 在AEM標籤中，在步驟2的 **Adobe IMS Technical Account Configuration** ( [Adobe IMS技術帳戶設定)標籤](#ims-configuration) 中，按一下 **「**&#x200B;下一步」。
1. 輸入Adobe Launch的標 **題，例如IMS設定**。
1. 在Adobe I/O標籤中，複製 **API金鑰（用戶端ID）**。
1. 在「AEM」標籤中，將先前複製的金鑰貼入「 **API金鑰」欄位**。
1. 在Adobe I/O中，按一下「擷 **取用戶端密碼** 」並加以複製。
1. 在「AEM」標籤中，將它貼入「用戶 **端密碼** 」欄位。
1. 在Adobe I/O標籤中，選取 **JWT** 標籤並複製URL，例如 `https://ims-na1.adobelogin.com`。
1. 在「AEM」索引標籤中，將URL貼入「授 **權伺服器** 」欄位。
1. 在「Adobe I/O」標籤中，複製JWT裝載（大括弧之間的代碼）。
1. 在「AEM」索引標籤中，將它貼入「裝 **載** 」欄位。
1. 按一 **下「建立** 」，在AEM中建立IMS設定。

### 步驟5a —— 在Adobe Launch中建立屬性 {#create-property}

屬性定義Launch可注入至您網站的功能。

1. 請至Adobe Launch `https://launch.adobe.com`。
1. 使用您的Adobe ID登入。
1. 按一 **下新屬性**。
1. 輸入名稱，例如「啟 **動AEM資料層」**。
1. 輸入您的網域。
1. 按一下&#x200B;**「儲存」**。

### 步驟5b —— 在啟動中建立規則 {#launch-rule}

使用您建立的屬性，您可以定義規則，此規則指定動作發生時應發生的事項。

1. 按一下步驟5 [Launch AEM Data Layer中新增](#create-property)**的屬性**。
1. 選擇「規 **則** 」標籤，然後 **按一下「建立新規則」**。
1. 輸入名稱，例如按 **一下影像**。
1. 按一下「 **事件** 」下方的 **+按鈕**。
1. 選擇 **作為****副檔名，**&#x200B;按一下 **Core Event Enter Image**************-Event Core Image-As Extension(Core Event Enter Image-As Lexter As CSS selector)。
1. 按一下 **保留變更**。
1. 按一下「 **動作」** 下方的 **+按鈕**。
1. 選擇 **Core** as **Extension**, **Code Custom Code** as Custom Editor and Click Action ******** and Open Editor type。
1. 在編輯器中，輸入以下代碼： `console.log("DOM click event tracked by Launch for image: ", event.target.src);`
1. 按一下&#x200B;**「儲存」**。
1. 按一下 **保留變更**。
1. 按一 **下「儲存** 」以建立新規則。

### 步驟6 —— 發佈啟動規則 {#publish-rule}

若要讓新規則可供您的AEM網站使用，您必須發佈它。

1. 在「 **Adobe Launch** 」標籤中，選取「 **Publishing** 」標籤。
1. 按一 **下「新增程式庫」**。
1. 根據需 **要輸入** Name（名稱）, **例如demo-1**。
1. 適 **合環境** ，例如 **開發（開發）**。
1. 按一下 **添加資源**。
1. 選擇 **規則-> image-click ->最新** ，然 **後按一下選擇並建立新修訂**。
1. 按一下&#x200B;**「儲存並為開發建立」**。
1. 在快顯功能表中，按一下「 **套用更新」並繼續**。
1. 建立程式庫時，按一下省略號圖示，並選取「 **送出以供核准」**。
1. 在彈出式按一下「 **提交**」。
1. 按一下省略號圖示，然後選取「 **建立階移」**。
1. 建置完成後，按一下省略號圖示並選取「核准 **發佈」**。
1. 在彈出式按一下「 **核准**」。
1. 按一下省略號圖示，然後選 **取「建立與發佈至生產」**。
1. 在彈出式按一下「 **發佈**」。

### 步驟7 —— 啟用網站的雲端設定 {#enable-configurations}

若要使用整合，它必須在AEM中指派為雲端設定。

1. 在AEM主控台中，按一下「 **工具」->「一般」->「設定瀏覽器」**。
1. 檢查核心 **元件示例** ，然後按一下 **屬性**。
1. 勾選「雲 **端設定」** ，然後按 **一下「儲存並關閉」**。

### 步驟8 —— 在AEM中建立與您網站的啟動整合 {#create-launch-integration}

AEM必須具備Launch整合才能與Launch搭配運作

1. 在AEM主控台中，按一 **下「工具」->「雲端服務」->「Adobe Launch Configurations**」。
1. 選擇「 **核心元件範例」** ，然後按一 **下「建立」**。
1. 輸入標 **題** ，例如 **啟動設定**。
1. 選擇您在步驟4中建立的IMS [設定。](#finish-ims)
1. 視 **情況** ，選擇公司。
1. As **Property** ，選擇在步驟5中建立的新增 [Launch屬性。](#create-property)
1. 將「在作 **者上加入生產程式碼** 」滑桿移至右側，然後按「下 **一步」**。
1. 按一下&#x200B;**下一步**。
1. 按一下&#x200B;**下一步**。
1. 按一下&#x200B;**建立**。

### 步驟9 —— 將您的AEM網站連線至Launch整合 {#connect-aem}

AEM若要使用Launch整合，必須將其指派為雲端設定。

1. 在AEM主控台中，按一下「 **網站** 」並檢查 **核心**&#x200B;元件網站。
1. 按一 **下屬性**。
1. 選擇「高 **級** 」頁籤。
1. 在「 **雲端設定**」中，選取「核心元 **件範例」** ，然後按一 **下「選取**」。
1. Click **Save &amp; Close**.

### 步驟10 —— 確認啟動邏輯已套用至頁面 {#verify-launch}

測試目前的步驟是否成功。

1. 以預覽模式開啟核心元件庫的「影像」頁面： `http://<lhost&gt;:<port&gt;/editor.html/content/core-components-examples/library/page-authoring/image.html`
1. 按一下影像，並確認訊息已 `A Core Image was clicked` 顯示在瀏覽器主控台中。

## 啟動與AEM和資料層的整合 {#data-layer-launch}

現在已設定AEM與Launch的整合，我們可以與資料層整合。

### 步驟1 —— 在Adobe Launch中建立規則 {#create-rule}

重複步驟5 [中的步驟](#launch-rule) ，使用下列值在Adobe Launch中新增規則。

* 名稱: `image-click-data-layer`
* 事件：
   * 擴充功能： 核心
   * 事件類型： DOM就緒
* 動作:
   * 擴充功能： 核心
   * 動作類型： 自訂代碼
   * 程式碼：

      ```
        function onImageClick(event) {
          console.log("Data layer click event tracked by Launch for image: " + event.info.path);
          console.log("dataLayer.getState(): ", adobeDataLayer.getState()); 
        }
        adobeDataLayer.addEventListener('image clicked', onImageClick);
      ```

### 步驟2 —— 發佈啟動規則，讓它可供您的AEM網站使用 {#publish-rule-2}

重複步驟6 [中的步驟](#publish-rule) ，以發佈新規則。

### 步驟3 —— 確認啟動邏輯已套用至頁面 {#verify}

1. 以預覽模式開啟核心元件庫的「影像」頁面： `http://<host&gt;:<port&gt;/editor.html/content/core-components-examples/library/page-authoring/image.html`
1. 按一下影像，並確認下列訊息已顯示在瀏覽器主控台中：

   ![資料層控制台輸出](/help/assets/data-layer-console-output.png)
