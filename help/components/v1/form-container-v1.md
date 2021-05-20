---
title: 表單容器元件(v1)
description: 核心元件表單容器元件可建立簡單的提交表單。
index: n
role: Architect, Developer, Administrator, Business Practitioner
exl-id: 1e34219f-fa82-494e-82e2-1b4d63d37fea
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 2%

---

# 表單容器元件(v1){#form-container-component-v1}

核心元件表單容器元件可建立簡單的提交表單。

## 使用狀況 {#usage}

表單容器元件支援簡單的WCM表單，並使用巢狀結構允許其他表單元件，以建立簡單的資訊提交表單和功能。

透過使用[設定對話方塊](#settings-dialog)，內容編輯器可定義觸發表單提交的動作類型、應儲存提交的內容，以及應觸發工作流程時。 範本作者可使用[設計對話方塊](#design-dialog)來定義允許元件及其對應，類似於範本編輯器](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/templates.html)中[標準版面容器的設計對話方塊。

## 版本和相容性{#version-and-compatibility}

本檔案說明表單容器元件v1，最初是透過AEM 6.3推出核心元件1.0.0版。

下表列出表單容器元件v1的相容性。

| AEM版本 | 表單容器元件v1 |
|--- |--- |
| 6.3 | 相容 |
| 6.4 | 相容 |

>[!CAUTION]
>
>本檔案說明「表單容器元件」的v1。
>
>有關表單容器元件當前版本的詳細資訊，請參閱[表單容器元件](/help/components/forms/form-container.md)文檔。

## 設定對話框{#settings-dialog}

設定對話方塊可讓內容作者定義提交元件時要採取的動作。

![](/help/assets/chlimage_1.png)

根據所選&#x200B;**動作類型**，容器內的可用選項將更改。 可用的動作類型為：

* [郵件](#mail)
* [存放區內容](#store-content)
* [提交訂單](#submit-order)
* [更新訂單](#update-order)

無論類型為何，都有[一般設定](#general-settings)套用至每個動作。

### 郵件 {#mail}

提交表單時，郵件動作類型會傳送電子郵件給指定的收件者。

![](/help/assets/chlimage_1-1.png)

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

![](/help/assets/chlimage_1-2.png)

* **內容路徑**  — 儲存已提交內容的內容存放庫路徑
* **檢視資料**  — 點選或按一下，以JSON形式檢視儲存的已提交資料
* **開始工作流程**  — 設定以在表單提交時將儲存的內容作為裝載來開始工作流程

### 提交訂單 {#submit-order}

提交表格後，將提交訂單。

![](/help/assets/chlimage_1-3.png)

### 更新訂單 {#update-order}

提交表單時，將更新訂單。

![](/help/assets/chlimage_1-4.png)

### 一般設定 {#general-settings}

無論選取的動作類型為何，都可以一律定義感謝頁面。

![](/help/assets/chlimage_1-5.png)

表單提交完成後，系統會將使用者重新導向至指定頁面。

* 使用「選擇」對話框在AEM中選擇資源。
* 如果感謝頁面不在AEM中，請指定絕對URL。 非絕對URL會相對於AEM來解譯。
* 留空可在提交後重新顯示表單。

## 設計對話框{#design-dialog}

設計對話方塊可讓範本作者為容器定義允許的元件及其對應，類似於範本編輯器](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/templates.html#main-pars_title_1754153843)中[標準版面容器的設計對話方塊。

## 技術詳細資訊{#technical-details}

如需表單容器元件[的最新技術檔案，請參閱GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/container/v1/container)。

您可從GitHub下載整個核心元件專案。

有關開發核心元件的詳細資訊，請參閱[核心元件開發人員檔案](/help/developing/overview.md)。
