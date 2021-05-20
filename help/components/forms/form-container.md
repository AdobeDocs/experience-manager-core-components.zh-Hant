---
title: 表單容器元件
description: 核心元件表單容器元件可建立簡單的提交表單。
role: Architect, Developer, Administrator, Business Practitioner
exl-id: 552f9dd5-6a3a-42d9-9969-e62a1f36e811
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 1%

---

# 表單容器元件{#form-container-component}

核心元件表單容器元件可建立簡單的提交表單。

## 使用狀況 {#usage}

表單容器元件支援簡單的WCM表單，並使用巢狀結構允許其他表單元件，以建立簡單的資訊提交表單和功能。

透過使用[設定對話方塊](#configure-dialog)，內容編輯器可定義表單提交所觸發的動作、應處理提交的URl，以及是否應觸發工作流程。 範本作者可使用[設計對話方塊](#design-dialog)來定義允許的元件及其對應，類似於範本編輯器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)中[標準版面容器的設計對話方塊。

>[!NOTE]
>
>核心元件表單容器元件僅支援使用核心元件表單元件（按鈕、文字、隱藏等）。 不支援在核心元件表單容器內使用[foundation元件](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/default-components-foundation.html)表單元件（反之亦然）。

## 版本和相容性{#version-and-compatibility}

表單容器元件的目前版本為v2，此版本於2018年1月隨核心元件2.0.0版推出，本檔案將加以說明。

下表詳細說明所有支援的元件版本、與元件版本相容的AEM版本，以及舊版檔案的連結。

| 元件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service  |
|--- |--- |--- |---|
| v2 | 相容 | 相容 | 相容 |
| [v1](/help/components/v1/form-container-v1.md) | 相容 | 相容 | - |

如需核心元件版本和版本的詳細資訊，請參閱檔案[核心元件版本](/help/versions.md)。

## 元件輸出示例{#sample-component-output}

若要體驗表單容器元件，並查看其設定選項以及HTML和JSON輸出的範例，請造訪[元件程式庫](https://adobe.com/go/aem_cmp_library_form_container)。

## 技術詳細資訊{#technical-details}

如需表單容器元件[的最新技術檔案，請參閱GitHub](https://adobe.com/go/aem_cmp_tech_form_container_v2)。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。

## 配置對話框{#configure-dialog}

「設定」對話方塊可讓內容作者定義提交元件時要採取的動作。

根據所選&#x200B;**動作類型**，容器內的可用選項將更改。 可用的動作類型為：

* [貼文表單資料](#post-data)
* [郵件](#mail)
* [存放區內容](#store-content)

無論類型為何，都有[一般設定](#general-settings)套用至每個動作。

### 貼文表單資料{#post-data}

提交表單時，貼文表單資料動作類型會將提交的資料以JSON形式傳遞至協力廠商以進行處理。

![表單容器元件的編輯對話方塊中的「貼文表單資料」選項](/help/assets/form-container-edit-post.png)

* **端點**  — 將處理資料的完全限定HTTPS服務
* **錯誤訊息**  — 如果提交失敗，則顯示訊息

>[!TIP]
>系統管理員可以調整其他逾時選項來處理轉送的表單資料。 [如需詳細資訊，請參閱GitHub的技術檔案。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/actions/rpc)

### 郵件 {#mail}

提交表單時，郵件動作類型會傳送電子郵件給指定的收件者。

![表單容器元件的編輯對話方塊中的郵件選項](/help/assets/form-container-edit-mail.png)

* **主旨**  — 表單提交時所傳送之電子郵件的主旨
* **寄件者**  — 表單提交時要傳送之電子郵件的寄件者電子郵件地址
* **收件者**  — 表單提交時會收到電子郵件的收件者地址
   * 點選或按一下&#x200B;**Add**&#x200B;按鈕以新增其他位址
   * 點選或按一下&#x200B;**Delete**&#x200B;按鈕以移除電子郵件地址
* **CC**  — 收件者的地址，將收到表單提交時寄送之電子郵件的副本
   * 點選或按一下&#x200B;**Add**&#x200B;按鈕以新增其他位址
   * 點選或按一下&#x200B;**Delete**&#x200B;按鈕以移除電子郵件地址

### 存放區內容 {#store-content}

提交表單時，表單的內容將儲存在指定的儲存庫位置。

![在「表單容器」的編輯對話方塊中儲存內容選項](/help/assets/form-container-edit-store.png)

* **內容路徑**  — 儲存已提交內容的內容存放庫路徑
* **檢視資料**  — 點選或按一下，以JSON形式檢視儲存的已提交資料
* **開始工作流程**  — 設定以在表單提交時將儲存的內容作為裝載來開始工作流程

>[!NOTE]
>
>為了更簡單地管理使用者資料，並強制分散關注點，一般不建議將使用者產生的內容儲存在存放庫中。
>
>請改用[貼文表單資料](#post-data)動作類型，將使用者內容傳遞至專用的服務提供者。

### 一般設定 {#general-settings}

無論選取的動作類型為何，都可以一律定義感謝頁面。

![「表單容器元件」的編輯對話方塊中的一般選項](/help/assets/form-container-edit-general.png)

* **感謝頁面**  — 表單提交完成後，系統會將使用者重新導向至指定頁面。
   * 使用「選擇」對話框在AEM中選擇資源。
   * 如果感謝頁面不在AEM中，請指定絕對URL。 非絕對URL會相對於AEM來解譯。
   * 留空可在提交後重新顯示表單。
* **ID**  — 此選項可控制HTML和資料層中元件的唯一 [識別碼](/help/developing/data-layer/overview.md)。
   * 若保留為空白，系統會自動為您產生唯一ID，並且可透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。

## 設計對話框{#design-dialog}

設計對話方塊可讓範本作者為容器定義允許的元件及其對應，類似於範本編輯器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)中[標準版面容器的設計對話方塊。

### 樣式標籤{#styles-tab}

表單容器元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling)。
