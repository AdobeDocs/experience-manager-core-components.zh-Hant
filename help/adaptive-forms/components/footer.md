---
title: 自適應Forms核心元件 — 頁腳
description: 使用或自定義自適應Forms頁腳核心元件。
role: Architect, Developer, Admin, User
exl-id: c8e7d3fe-4b82-4a80-8da2-19f6cff1e3e9
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: tm+mt
source-wordcount: '770'
ht-degree: 2%

---

# 頁尾 {#footer-adaptive-forms-core-component}

自適應表單中的頁腳元件是通常出現在表單底部的區域，它包含諸如版權聲明、相關資源連結或聯繫資訊等資訊。 頁腳可提供附加資訊，如上次更新的日期，這對具有輔助功能需求的用戶是有益的。

**範例**

![](/help/adaptive-forms/assets/footer.png)

## 使用狀況 {#reasons-to-use-footer}

將頁腳元件包含在表單中是有益的，原因有幾：

* **法律要求**:某些表格可能需要包含免責聲明、版權聲明或其他法律資訊。 頁腳是包含此資訊的方便位置。

* **導航**:頁腳可以提供指向網站上其他重要頁面的連結，如隱私策略、服務條款或聯繫人頁面。

* **品牌**:頁腳可用於包括徽標或其他品牌要素，有助於增強組織或網站的身份。

* **一致性**:頁腳在表單的設計和佈局中提供一致性，使用戶更直觀、更易於導航。

* **附加上下文**:頁腳可以為表單提供附加上下文，如描述表單的文本或到相關資源的連結，使表單更具資訊性和用戶友好性。

## 版本和相容性 {#version-and-compatibility}

自適應Forms手風琴核心元件於2023年2月發佈，作為用於Cloud Service的核心元件2.0.4的一部分，以及用於Forms或更晚版本的核心元件1.1.12的核心元件6.5.16.0的一部分。 下面是一個表，其中顯示了所有支援的版本AEM、相容性以及指向相應文檔的連結：

| 元件版本 | AEM as a Cloud Service  | AEM6.5.16.0Forms |
|---|---|---|
| v1 | 相容<br>[發行版2.0.4](/help/adaptive-forms/version.md) 之後 | 相容<br>[發行版1.1.12](/help/adaptive-forms/version.md) 晚但小於2.0.0。 |

有關核心元件版本和版本的資訊，請參閱 [核心元件版本](/help/adaptive-forms/version.md) 的子菜單。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術詳細資訊 {#technical-details}

獲取有關自適應Forms頁腳核心元件的最新資訊，請參閱 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/footer/v1/footer)。 有關開發核心元件的詳細資訊，請查看 [核心元件開發人員文檔](/help/developing/overview.md)。


## 配置對話框 {#configure-dialog}

使用「配置」對話框，您可以輕鬆自定義訪問者的頁腳體驗。 您還可以輕鬆定義頁腳選項，以獲得無縫的用戶體驗。

![「屬性」頁籤](/help/adaptive-forms/assets/footer_propertiestab.png)

* **編輯對話框**
編輯對話框提供標準的富格文本格式工具，允許用戶為頁腳建立文本。

* **粗體**  — 此選項將粗體格式應用於選定文本或大膽設定游標後輸入的文本格式。 `Ctrl+B` 是鍵盤快捷鍵。

* **斜體**  — 此選項將斜體格式應用於游標後輸入的選定文本或斜體文本。 `Ctrl+I` 是鍵盤快捷鍵。

![項目符號選項](/help/adaptive-forms/assets/footer_bullet.png)


* **項目符號**

   * **項目符號表徵圖**  — 它將選定文本格式化為項目符號清單，或在游標後開始插入項目符號清單。 要結束項目符號清單，請再次點擊或按一下「項目符號」按鈕，或輸入兩個回車符。

   * **編號清單表徵圖**  — 它將選定文本格式化為編號清單，或在游標後開始插入編號清單。 要結束編號清單，請再次點擊或按一下「編號」按鈕，或輸入兩個回車符。

   * **輸出表徵圖**  — 它減少在游標後輸入的選定文本或文本的縮進級別。 僅當游標的選定文本或位置已縮進時才處於活動狀態。

   * **縮進表徵圖**  — 它增加了游標後輸入的選定文本或文本的縮進級別。

![超連結選項](/help/adaptive-forms/assets/footer_link.png)

* **超連結**

   * **路徑**  — 輸入路徑
      1. 使用「開啟選擇」對話框選擇中的路AEM徑。
      1. 如果連結不在AEM其中，請輸入絕對URL。
      1. 非絕對路徑被解釋為相對於AEM。
   * **備選文本**  — 輸入連結的備選說明性文本。

   * **目標**  — 選擇連結行為
      * 目標
      * 相同索引標籤
      * 新索引標籤
      * 父框架
      * 上框架
   * **取消連結表徵圖**  — 此選項將刪除已應用於選定文本的連結。 僅當已選擇連結時，此選項才處於活動狀態。

   * **段落格式表徵圖**  — 此選項允許您將段落格式應用於選定文本。 它還幫助您設定游標後插入的文本的格式。 它定義標題的標題級別。



* **ID**:此選項允許控制HTML和資料層中元件的唯一標識符。

   * 如果留空，則系統會為您自動生成一個唯一的ID *，並通過檢查生成的頁面來找到它。
   * 如果指定了ID，則作者有責任確保其唯一。
   * 更改ID可能會影響CSS、JS和資料層跟蹤。

