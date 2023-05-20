---
title: 自適應Forms核心元件 — 影像
description: 使用或定制自適應Forms影像核心元件。
role: Architect, Developer, Admin, User
exl-id: 9ee42d5d-16e3-4973-8364-5bc512ebe72e
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: tm+mt
source-wordcount: '978'
ht-degree: 0%

---

# 影像 {#image-adaptive-forms-core-component}

自適應表單中的影像元件是將影像包括在表單中的一種方法。 這些影像可用於增強表單的整體設計、提供附加資訊或作為視覺幫助來幫助用戶理解表單的目的。 影像元件可用於在表單中添加徽標、照片或圖形。

對於輔助功能，必須指定 **備用文本** 為影像提供簡短、描述性的文本替代，該文本將影像描述給無法看到它的用戶。


**範例**

![](/help/adaptive-forms/assets/image.png)


## 使用狀況 {#reasons-to-use-image-in-a-form}

將影像元件包含在自適應表單中是有益的，原因有幾：

* **品牌**:影像可用於顯示建立表單的組織的徽標或名稱，從而幫助建立品牌認可和信譽。

* **視覺輔助**:影像可以作為視覺輔助幫助用戶理解表單的目的，從而幫助用戶提供額外的資訊級別。

* **裝飾**:影像可用於增強形式的整體設計並使其更具視覺吸引力。

* **用戶體驗**:通過為用戶提供訪問和填寫表單域的清晰直觀的方式，可以使用影像來使表單更加用戶友好。

## 版本和相容性 {#version-and-compatibility}

自適應Forms手風琴核心元件於2023年2月發佈，作為用於Cloud Service的核心元件2.0.4的一部分，以及用於Forms或更晚版本的核心元件1.1.12的核心元件6.5.16.0的一部分。 下面是一個表，其中顯示了所有支援的版本AEM、相容性以及指向相應文檔的連結：

| 元件版本 | AEM as a Cloud Service  | AEM6.5.16.0Forms |
|---|---|---|
| v1 | 相容<br>[發行版2.0.4](/help/adaptive-forms/version.md) 之後 | 相容<br>[發行版1.1.12](/help/adaptive-forms/version.md) 晚但小於2.0.0。 |

有關核心元件版本和版本的資訊，請參閱 [核心元件版本](/help/adaptive-forms/version.md) 的子菜單。


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技術詳細資訊 {#technical-details}

獲取有關自適應Forms影像核心元件的最新資訊，請參閱 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/image/v1/image)。 有關開發核心元件的詳細資訊，請查看 [核心元件開發人員文檔](/help/developing/overview.md)。


## 配置對話框 {#configure-dialog}

通過「配置」對話框，您可以輕鬆地為訪問者定制您的映像體驗。 您還可以輕鬆定義映像選項，以獲得無縫的用戶體驗。

![「屬性」頁籤](/help/adaptive-forms/assets/image_properties.png)

* **名稱**  — 您可以在表單和規則編輯器中輕鬆地使用其唯一名稱標識表單元件，但名稱不能包含空格或特殊字元。

* **標題**  — 使用其「標題」，您可以輕鬆地在窗體中標識元件，預設情況下，標題會顯示在元件的頂部。 如果未添加標題，則將顯示元件的名稱，而不顯示標題文本。

* **記錄綁定引用的文檔**  — 此選項允許您將「自適應表單」欄位與「記錄文檔」欄位關聯。 當用戶在自適應表單的連結欄位中輸入任何值時，該值也會出現在相應記錄文檔的連結欄位中。 例如，「記錄文檔」綁定引用可用於根據在表單中輸入的客戶ID在「記錄文檔」中顯示客戶的名稱和地址。 通過這種方式，AEM Forms使您能夠生成記錄文檔，並為收集和管理資料提供無縫的用戶體驗。

* **說明**  — 說明是簡短的文本說明，提供有關特定影像用途的其他資訊或說明。

* **將資產拖放到此處或瀏覽要上載的檔案**  — 此選項允許使用滑鼠拖放來放置資產，如影像。 您還可以使用 **瀏覽** 按鈕 添加影像後，影像底部會出現三個按鈕：
   * **編輯**  — 點擊或按一下 **編輯** 以在「資產編輯器」中管理資產的格式副本。
   * **清除**  — 點擊或按一下 **清除** 來取消選擇當前選定的映像。
   * **選擇**  — 點擊或按一下 **選擇**  選項從「資產」資料夾中選擇另一個影像。

* **備用文本**  — 此選項用於輸入文本，該文本為影像提供了簡短和描述性的文本選項，用於向視障用戶描述影像。

* **隱藏元件**  — 選擇從窗體中隱藏元件的選項。 該元件仍可用於其他目的，如在規則編輯器中將其用於計算。 當您需要儲存用戶不需要看到或直接更改的資訊時，此功能非常有用。

* **只讀**  — 選擇選項，使元件不可編輯。 用戶可以查看欄位的值，但無法修改它。 該元件仍可用於其他目的，如在規則編輯器中將其用於計算。

## 設計對話框 {#design-dialog}

「設計」對話框用於定義和管理Image元件的CSS樣式。

### 樣式頁籤 {#styles-tab}

該頁籤用於定義和管理元件的CSS樣式。 自適應Forms影像核元件支AEM持 [樣式系統](/help/get-started/authoring.md#component-styling)。

![設計對話框](/help/adaptive-forms/assets/image_designdialog.png)

**預設CSS類**:可以為自適應Forms影像核心元件提供預設CSS類。

**允許的樣式**:可以通過提供表示樣式的名稱和CSS類來定義樣式。 例如，可以建立名為「bold text」的樣式，並提供CSS類「font-weight:粗體」。 可以在自適應Forms編輯器中使用這些樣式或將這些樣式應用於自適應表單。 要應用樣式，請在「自適應Forms」編輯器中，選擇要應用樣式的元件，導航到屬性對話框，然後從 **樣式** 的子菜單。 如果需要更新或修改樣式，只需返回到「設計」對話框，更新樣式頁籤中的樣式，並保存更改。
