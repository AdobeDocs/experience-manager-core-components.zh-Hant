---
title: 適用性Forms核心元件 — 影像
description: 使用或自訂適用性Forms影像核心元件。
role: Architect, Developer, Admin, User
source-git-commit: 1e6460d318f4f9a5dfdcbb81723da01b51b72f3f
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 0%

---


# 影像 {#image-adaptive-forms-core-component}

適用性表單中的影像元件是將影像納入表單的方法。 這些影像可用於增強表單的整體設計、提供額外資訊或作為視覺輔助，以協助使用者了解表單的用途。 影像元件可用來在表單中新增標誌、像片或圖形。

若為協助工具，請務必指定 **替代文字** 為影像提供簡短、描述性的文字替代項目，可向無法看見的使用者說明影像。


**範例**

![](/help/adaptive-forms/assets/image.png)


## 使用狀況 {#reasons-to-use-image-in-a-form}

將影像元件納入最適化表單有幾個好處，包括：

* **品牌推廣**:影像可用來顯示建立表單之組織的標誌或名稱，有助於建立品牌認可度和信譽。

* **視覺輔助**:影像可協助使用者提供額外的資訊，方法是提供視覺輔助，協助使用者了解表單的用途。

* **裝飾**:影像可用於增強表單的整體設計，使其更具視覺吸引力。

* **使用者體驗**:影像可讓使用者以清楚且直覺的方式存取和填寫表單欄位，讓表單更方便使用。

## 版本與相容性 {#version-and-compatibility}

適用性Forms影像核心元件已於2023年2月發行，是核心元件2.0.4的一部分。下表顯示所有支援的版本、AEM相容性，以及對應檔案的連結：

| 元件版本 | AEM as a Cloud Service  |
|--- |--- |---|---|
| v1 | 相容於<br>[版本2.0.4](/help/versions.md) 和 | 相容 | 相容 |

如需核心元件版本和版本的相關資訊，請參閱 [核心元件版本](/help/versions.md) 檔案。


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術詳細資訊 {#technical-details}

取得適用性Forms影像核心元件的最新資訊，請參閱 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/image/v1/image). 如需開發核心元件的詳細資訊，請參閱 [核心元件開發人員檔案](/help/developing/overview.md).


## 配置對話框 {#configure-dialog}

您可以透過「設定」對話方塊輕鬆自訂訪客的影像體驗。 您也可以輕鬆定義影像選項，以提供順暢的使用者體驗。

![「屬性」頁簽](/help/adaptive-forms/assets/image_properties.png)

* **名稱**  — 您可以在表單和規則編輯器中，以唯一的名稱輕鬆識別表單元件，但名稱不得包含空格或特殊字元。

* **標題**  — 使用其「標題」，您可以輕鬆地在表單中識別元件，預設情況下，標題會顯示在元件上方。 如果未新增標題，則會顯示元件名稱，而非標題文字。

* **記錄綁定引用的文檔**  — 此選項可讓您將適用性表單欄位與記錄檔案欄位建立關聯。 當使用者在適用性表單的連結欄位中輸入任何值時，該值也會出現在對應記錄檔案的連結欄位中。 例如，記錄文檔綁定引用可用於根據在表單中輸入的客戶ID在記錄文檔中顯示客戶的名稱和地址。 如此一來，AEM Forms便能讓您產生記錄檔，並提供順暢的使用者體驗，以收集和管理資料。

* **說明**  — 說明是簡短的文本說明，提供有關特定影像用途的其他資訊或說明。

* **將資產放置在此處或瀏覽要上傳的檔案**  — 此選項可讓您拖放滑鼠，拖放影像等資產。 您也可以使用 **瀏覽** 按鈕。 新增影像後，影像底部會顯示三個按鈕：
   * **編輯**  — 點選或按一下 **編輯** 在「資產編輯器」中管理資產的轉譯。
   * **清除**  — 點選或按一下 **清除** 以取消選取目前選取的影像。
   * **挑選**  — 點選或按一下 **挑選**  選項，從「資產」資料夾選取其他影像。

* **替代文字**  — 此選項用於輸入文本，該文本為影像提供簡短的描述性文本替代項，該替代項向視障用戶描述影像。

* **隱藏元件**  — 選取從表單中隱藏元件的選項。 元件仍可供其他用途存取，例如在規則編輯器中用於計算。 當您需要儲存不需要由使用者看到或直接變更的資訊時，這個功能會很實用。

* **唯讀**  — 選取選項，使元件不可編輯。 使用者可以看到欄位的值，但無法修改它。 元件仍可供其他用途存取，例如在規則編輯器中用於計算。

## 設計對話方塊 {#design-dialog}

「設計對話方塊」可用來定義和管理影像元件的CSS樣式。

### 樣式標籤 {#styles-tab}

「設計對話方塊」可用來定義及管理元件的CSS樣式。 適用性Forms影像核心元件支援AEM [樣式系統](/help/get-started/authoring.md#component-styling).

**預設CSS類**:您可以為適用性Forms影像核心元件提供預設CSS類別。

**允許的樣式**:您可以提供代表樣式的名稱和CSS類別，以定義樣式。 例如，您可以建立名為「粗體文字」的樣式，並提供CSS類別「font-weight:粗體」。 您可以在適用性Forms編輯器中，將這些樣式使用或套用至適用性表單。 若要套用樣式，請在適用性Forms編輯器中選取您要套用樣式的元件、導覽至屬性對話方塊，然後從 **樣式** 下拉式清單。 如果需要更新或修改樣式，只需返回「設計」對話框、更新樣式頁簽中的樣式並保存更改即可。