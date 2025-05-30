---
title: 表單容器元件
description: 利用核心元件表單容器元件，可建立簡易提交表單。
role: Architect, Developer, Admin, User
exl-id: 552f9dd5-6a3a-42d9-9969-e62a1f36e811
source-git-commit: 6fbc781db555bc6abaed1d122a9a8756e3d53222
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 1%

---

# 表單容器元件 {#form-container-component}

利用核心元件表單容器元件，可建立簡易提交表單。

## 使用情況 {#usage}

表單容器元件可支援簡單的WCM表單，並使用巢狀結構來允許其他表單元件，藉以建立簡單的資訊提交表單和功能。

透過[設定對話方塊](#configure-dialog)，內容編輯者可以定義由表單提交所觸發的動作、應處理提交的URl，以及是否應觸發工作流程。 範本作者可使用[設計對話方塊](#design-dialog)定義允許的元件及其對應，類似於範本編輯器[&#128279;](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hant)中標準配置容器的設計對話方塊。

>[!NOTE]
>
>核心元件表單容器元件僅支援使用核心元件表單元件（按鈕、文字、隱藏等）。 不支援在核心元件表單容器中使用[基礎元件](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/siteandpage/default-components-foundation.html?lang=zh-Hant)表單元件（反之亦然）。

## 版本和相容性 {#version-and-compatibility}

表單容器元件的目前版本是v2，此版本隨2018年1月的核心元件2.0.0版的發佈引入，詳情請參閱本檔案。

下表詳細說明元件的所有支援版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service  |
|--- |--- |--- |---|---|
| v2 | 與<br>[版本2.17.4](/help/versions.md)和先前版本相容 | 相容 | 相容 | 相容 |
| [v1](/help/components/v1/form-container-v1.md) | 相容 | 相容 | - | 相容 |

如需核心元件版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 範例元件輸出 {#sample-component-output}

若要體驗表單容器元件並檢視其設定選項範例以及HTML和JSON輸出，請造訪[元件資料庫](https://adobe.com/go/aem_cmp_library_form_container_tw)。

## 技術細節 {#technical-details}

在GitHub[&#128279;](https://adobe.com/go/aem_cmp_tech_form_container_v2_tw)上可找到有關表單容器元件的最新技術檔案。

在[核心元件開發人員檔案](/help/developing/overview.md)中可找到有關開發核心元件的進一步詳細資料。

## 設定對話方塊 {#configure-dialog}

設定對話方塊可讓內容作者定義在提交元件時所採取的動作。

根據選取的&#x200B;**動作型別**，容器內的可用選項將會變更。 可用的動作型別為：

* [張貼表單資料](#post-data)
* [郵件](#mail)
* [存放區內容](#store-content)

無論型別為何，都有[一般設定](#general-settings)適用於每個動作。

### 張貼表單資料 {#post-data}

提交表單時，發佈表單資料動作型別會將提交的資料以JSON的形式，傳遞至協力廠商進行處理。

![在表單容器元件的編輯對話方塊中張貼表單資料選項](/help/assets/form-container-edit-post.png)

* **端點** — 將處理資料的完整HTTPS服務
* **錯誤訊息** — 提交失敗時顯示的訊息

>[!TIP]
>系統管理員可以調整其他逾時選項，以處理轉送的表單資料。 [如需詳細資訊，請參閱GitHub上的技術檔案。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/actions/rpc)

### 郵件 {#mail}

提交表單時，郵件動作型別會傳送電子郵件給指定的收件者。

表單容器元件的[編輯]對話方塊中的![郵件選項](/help/assets/form-container-edit-mail.png)

* **主旨** — 在提交表單時將傳送的電子郵件主旨
* **寄件者** — 在提交表單時將傳送之電子郵件的寄件者電子郵件地址
* **至** — 在提交表單時將收到電子郵件的收件者地址
   * 點選或按一下&#x200B;**新增**&#x200B;按鈕以新增其他地址
   * 點選或按一下&#x200B;**刪除**&#x200B;按鈕以移除電子郵件地址
* **副本** — 將接收在提交表單時傳送之電子郵件副本的收件者地址
   * 點選或按一下&#x200B;**新增**&#x200B;按鈕以新增其他地址
   * 點選或按一下&#x200B;**刪除**&#x200B;按鈕以移除電子郵件地址

### 存放區內容 {#store-content}

提交表單時，表單內容會儲存在指定的存放庫位置。

![在表單容器的編輯對話方塊中儲存內容選項](/help/assets/form-container-edit-store.png)

* **內容路徑** — 儲存所提交內容的內容存放庫路徑
* **檢視資料** — 點選或按一下以檢視以JSON格式儲存的提交資料
* **啟動工作流程** — 設定為在提交表單時啟動將儲存的內容作為承載的工作流程

>[!NOTE]
>
>為了簡化使用者資料的管理並強制分離關注點，通常不建議將使用者產生的內容儲存在存放庫中。
>
>改用[張貼表單資料](#post-data)動作型別將使用者內容傳遞給專用服務提供者。

### 一般設定 {#general-settings}

無論選取的動作型別為何，您一律可以定義感謝頁面。

![表單容器元件的「編輯」對話方塊中的一般選項](/help/assets/form-container-edit-general.png)

* **感謝您的頁面** — 完成表單提交後，系統會將使用者重新導向至指定的頁面。
   * 使用「選取」對話方塊可在AEM中選取資源。
   * 如果感謝頁面不在AEM中，請指定絕對URL。 非絕對URL將會詮釋為相對於AEM。
   * 留空可在提交後重新顯示表單。
* **ID** — 此選項可讓您控制HTML和[資料層](/help/developing/data-layer/overview.md)中元件的唯一識別碼。
   * 如果保留為空白，系統會自動為您產生唯一ID，並可透過檢查結果頁面找到該ID。
   * 若指定ID，作者應負責確認該ID為唯一ID。
   * 變更ID會對CSS、JS和資料層追蹤造成影響。

## 設計對話方塊 {#design-dialog}

設計對話方塊可讓範本作者為容器定義允許的元件及其對應，類似於範本編輯器[&#128279;](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hant)中標準配置容器的設計對話方塊。

### 樣式索引標籤 {#styles-tab}

表單容器元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
