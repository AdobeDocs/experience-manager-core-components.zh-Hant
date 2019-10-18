---
title: AEM Project Archetype Front-End Build
seo-title: AEM Project Archetype Front-End Build
description: AEM型應用程式的專案範本
seo-description: AEM型應用程式的專案範本
contentOwner: 博納特
content-type: 引用
topic-tags: 核心元件
translation-type: tm+mt
source-git-commit: 0a61f4e6d1ad8b4d5e3778018838dc70d496e1fc

---


# AEM Project Archetype Front-End Build {#aem-project-archetype-front-end-build}

AEM Project Archetype包含選用的專屬前端建立機制，以Webpack為基礎，具備下列功能。

* 完整TypeScript、ES6和ES5支援（含適用的Webpack包裝函式）
* 使用TSLint規則集的TypeScript和JavaScript連結
* ES5輸出，以支援舊版瀏覽器
* 萬用字元
   * 無需隨處新增匯入
   * 現在，所有JS和CSS檔案都可新增至每個元件
      * 最佳實務是 `/clientlib/js`在、 `/clientlib/css`或 `/clientlib/scss`
   * 由於 `.content.xml` 所有內 `js.txt`容都通過Webpack運行，所以不需要或/`css.txt` 檔案
   * 全域提取資料夾下的所有JS `/component/` 檔案。
      * Webpack可讓CSS/SCSS檔案透過JS檔案連結。
      * 它們被拉進兩個入口 `sites.js` 處 `vendors.js`。
   * AEM使用的唯一檔案是輸出 `site.js` 檔 `site.css` 案 `/clientlib-site` 以及 `dependencies.js` 和 `dependencies.css` 中 `/clientlib-dependencies`
* 區塊
   * 主要（網站js/css）
   * 廠商（相依性js/css）
* 完整的Sass/Scss支援（Sass會透過Webpack編譯為CSS）。

## 安裝 {#installation}

1. 全 [域安裝NodeJS](https://nodejs.org/en/download/) (v10+)。 這也將安裝npm。
1. 導覽至專案中的ui.frontend並執行 `npm install`。

## 使用狀況 {#usage}

以下NPM指令碼驅動前端工作流：

* `npm run dev` -已停用JS最佳化（樹狀結構等）和來源地圖，並停用CSS最佳化的完整建置。
* `npm run prod` -啟用JS最佳化（樹狀結構等）、停用來源地圖和啟用CSS最佳化的完整建置。

## 輸出 {#output}

### 一般 {#general}

* 站點- `site.js` 並 `site.css` 在clientlib-site資料夾中建立。
* 相依性- `dependencies.js` 並在 `dependencies.css` clientlib-dependencies資料夾中建立。

### JavaScript {#javascript}

* 最佳化——對於生產組建，所有未使用或呼叫的JS都會移除。

### CSS {#css}

* 自動預修——所有CSS都會透過預修器執行，而任何需要預修的屬性都會自動將這些屬性加入CSS中。
* 最佳化——在貼文時，所有CSS都會透過最佳化程式(cssnano)執行，並根據下列預設規則將它標準化：
   * 盡可能減少CSS計算運算式，以確保瀏覽器相容性和壓縮在等效長度、時間和角度值之間轉換。 請注意，預設情況下，不會轉換長度值。
   * 移除規則、選擇器與宣告中及周圍的注釋
   * 刪除重複的規則、at-rules和聲明
      * 請注意，這隻適用於完全重複的檔案。
   * 移除空的規則、媒體查詢和具有空選擇器的規則，因為它們不會影響輸出
   * 由選擇器和重疊的屬性／值對合併相鄰規則
   * 確保CSS檔案中只有單一@charset，並將它移至檔案頂端
   * 當產生的輸出較小時，以實際值取代CSS初始關鍵字
   * 使用SVGO壓縮內嵌SVG定義
* 清除——包含明確的清除工作，以視需要清除產生的CSS、JS和Map檔案。
* 源映射——僅構建開發

>[!NOTE]
>前端構建選項利用共用公共配置檔案的僅開發和僅生產webpack配置檔案。 這樣，可以單獨修改開發和生產設定。
