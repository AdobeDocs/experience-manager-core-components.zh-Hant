---
title: 頁面元件(v2)
description: 「頁面元件」是可擴展的頁面元件，旨在與模板編輯器一起使用，並允許與模板編輯器一起裝配頁眉/頁腳和結構元件。
role: Architect, Developer, Admin, User
exl-id: e85fe4db-6de4-4a84-a54c-bd07a67efed3
source-git-commit: e291d4c1bfd37292d68c236178f9681c4e5ee741
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 0%

---

# 頁面元件(v2) {#page-component}

「頁面元件」是可擴展的頁面元件，用於 [模板編輯器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html) 並允許將頁眉/頁腳和結構元件與模板編輯器一起裝配。

## 使用狀況 {#usage}

「頁面元件」構成了所有使用核心元件設計的頁面以及可編輯模板的基礎。 通過使用頁面元件，頁眉、頁腳和頁面結構可以使用其他核心元件定義為模板。

使用 [設計對話框](#design-dialog)，可以為頁面定義自定義客戶端庫。 與具有可直接從元件訪問的編輯對話框的其他元件不同，由於「頁面元件」是頁面本身，因此 [編輯對話框](#edit-dialog) 頁面元件的「頁面屬性」窗口。

## 版本和相容性 {#version-and-compatibility}

本文檔介紹了2018年1月隨核心元件2.0.0版推出的頁面元件v2。

>[!CAUTION]
>
>本文檔介紹頁面元件的v2。
>
>有關頁面元件當前版本的詳細資訊，請參閱 [頁面元件](/help/components/page.md) 的子菜單。

## 漸進式Web應用支援 {#pwa-support}

2.15.0版核心元件為AEMas a Cloud Service內置 [漸進式Web應用(PWA)功能。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/enable-pwa.html) 在站點級別進行簡單配置，將您AEM的體驗變為PWA!

### 技術詳細資訊 {#technical-details}

有關頁面元件的最新技術文檔 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_page_v2)。

有關開發核心元件的詳細資訊，請參閱 [核心元件開發人員文檔](/help/developing/overview.md)。

## 編輯對話框 {#edit-dialog}

因為元件代表整個頁面，所以通常在編輯對話框中的設定在 [頁面屬性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html) 的子菜單。

## 設計對話框 {#design-dialog}

由於元件代表整個頁面，因此可通過 **頁面資訊 — >頁面策略** 編輯頁面模板時。

![頁面原則](/help/assets/page-policy.png)

>[!NOTE]
>
>在以前版本AEM中， **頁面策略** 調用 **頁面設計**。

### 屬性頁籤 {#properties-tab}

使用「頁面設計」窗口，可以定義要載入的客戶端庫以及頁面的Web資源庫。

* **客戶端庫**  — 這定義要載入的客戶端庫類別。 JavaScript將添加在正文端，CSS將添加到頁面頭。
* **客戶端庫JavaScript頁面頭**  — 這將定義要載入到頁頭中的JavaScript客戶端庫類別。
   * 此處定義的類別， **客戶端庫** 欄位將在頁面頭中載入JavaScript，而不是在body結尾。
   * 除非類別也位於 **客戶端庫** 的子菜單。

* **Web資源客戶端庫**  — 用於為Web資源（如favicon）提供服務的客戶端庫類別。

* **跳至主內容元素選擇器**  — 用作輔助功能，可直接跳至頁面的主要內容

![「頁面元件設計」對話框](/help/assets/page-design.png)

可以為 **客戶端庫** 和 **客戶端庫JavaScript頁面頭** 欄位：

* 要添加新欄位，請按一下或點擊 **添加** 按鈕。
* 要刪除欄位，請按一下或點擊要刪除的欄位旁邊的垃圾桶表徵圖。
* 要重新排列載入順序，請按一下或點擊並拖動要移動的欄位旁邊的控制滑塊。

有關使用客戶端庫的詳細資訊，請參見 [使用客戶端庫](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html)。

>[!CAUTION]
>
>在核心元件版本2.2.0中引入了為頁面頭單獨定義客戶端庫的功能。

### 樣式頁籤 {#styles-tab}

頁面元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。

## Adobe客戶端資料層 {#data-layer}

頁面元件支援 [Adobe客戶端資料層。](/help/developing/data-layer/overview.md)
