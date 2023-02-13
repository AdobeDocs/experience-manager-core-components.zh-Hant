---
title: 適用性Forms核心元件 — 頁尾
description: 使用或自訂適用性Forms頁尾核心元件。
role: Architect, Developer, Admin, User
source-git-commit: b378fbd5695f82b8fc9de3a2d53a8387099ae33b
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 2%

---


# 頁尾 {#footer-adaptive-forms-core-component}

適用性表單中的頁尾元件通常是顯示在表單底部的區域，其中包含版權聲明、相關資源的連結或聯絡資訊等資訊。 頁尾可提供額外資訊，例如上次更新的日期，這對有無障礙需求的使用者有好處。

**範例**

![](/help/adaptive-forms/assets/footer.png)

## 使用狀況 {#reasons-to-use-footer}

將頁尾元件納入表單有好處的原因有幾個，包括：

* **法律要求**:某些表單可能需要包含免責聲明、版權聲明或其他法律資訊。 頁尾是包含此資訊的方便位置。

* **導覽**:頁尾可提供網站上其他重要頁面的連結，例如隱私權原則、服務條款或聯絡頁面。

* **品牌推廣**:頁尾可用來包含標誌或其他品牌元素，有助於加強組織或網站的身分。

* **一致性**:頁尾可讓表單的設計和版面保持一致，讓使用者更直覺且易於導覽。

* **其他內容**:頁尾可提供表單的其他內容，例如描述表單的文字或相關資源的連結，讓表單內容更豐富且方便使用。

## 版本與相容性 {#version-and-compatibility}

適用性Forms頁尾核心元件已於2023年2月發行，作為核心元件2.0.4的一部分。下表顯示所有支援的版本、AEM相容性，以及對應檔案的連結：

|  |  |
|---|---|
| 元件版本 | AEM as a Cloud Service  |
| — | --- |
| v1 | 相容於<br>[版本2.0.4](/help/versions.md) 和 | 相容 | 相容 |

如需核心元件版本和版本的相關資訊，請參閱 [核心元件版本](/help/versions.md) 檔案。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術詳細資訊 {#technical-details}

取得下列主題的技術檔案中適用性Forms頁尾核心元件的最新資訊： [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/footer/v1/footer). 如需開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).


## 配置對話框 {#configure-dialog}

您可以使用「設定」對話方塊輕鬆自訂訪客的頁尾體驗。 您也可以輕鬆定義頁尾選項，以提供順暢的使用者體驗。

![「屬性」頁簽](/help/adaptive-forms/assets/footer_propertiestab.png)

* **編輯對話方塊**
編輯對話方塊提供標準RTF格式工具，讓使用者為頁尾建立文字。

* **粗體**  — 此選項將粗體格式應用於選定文本，或將游標後輸入的文本大膽格式化。 `Ctrl+B` 是鍵盤的快捷鍵。

* **斜體**  — 此選項將斜體格式應用於選定文本或在游標後輸入的斜體文本。 `Ctrl+I` 是鍵盤的快捷鍵。

![項目符號選項](/help/adaptive-forms/assets/footer_bullet.png)


* **項目符號**

   * **項目符號圖示**  — 它將選定文本格式化為項目符號清單，或在游標後開始插入項目符號清單。 要結束項目符號清單，請再次點選或按一下「項目符號」按鈕，或輸入兩個歸位符。

   * **編號清單圖示**  — 它將選定文本格式化為編號清單，或在游標後開始插入編號清單。 若要結束編號清單，請再次點選或按一下「編號」按鈕，或輸入兩個歸位字元。

   * **輸出表徵圖**  — 它減少了游標之後輸入的選定文本或文本的縮進級別。 僅當游標的選定文本或位置已縮排時才處於活動狀態。

   * **縮進表徵圖**  — 它會增加游標之後輸入的選定文本或文本的縮進級別。

![超連結選項](/help/adaptive-forms/assets/footer_link.png)

* **超連結**

   * **路徑**  — 輸入路徑
      1. 使用「開啟選取對話方塊」在AEM中選擇路徑。
      1. 如果連結不在AEM內，請輸入絕對URL。
      1. 非絕對路徑會解譯為相對於AEM。
   * **替代文字**  — 輸入連結的替代描述性文字。

   * **目標**  — 選取連結行為
      * 目標
      * 相同索引標籤
      * 新索引標籤
      * 父框架
      * 上框架
   * **取消連結表徵圖**  — 此選項會移除已套用至所選文字的連結。 只有在已選取連結時，此選項才會啟用。

   * **段落格式表徵圖**  — 此選項允許將段落格式應用到選定文本。 它還幫助您設定游標後插入的文本的格式。 它定義標題的標題層。



* **ID**:此選項可控制HTML和資料層中元件的唯一識別碼。

   * 若保留為空白，系統會自動*產生唯一ID，並透過檢查產生的頁面來找到。
   * 若已指定ID，則作者應負責確認其唯一。
   * 變更ID可能會影響CSS、JS和資料層追蹤。


