---
title: 市場活動變數
description: 使用促銷活動變數作為佔位符來合成個性化電子郵件內容。
role: Architect, Developer, Admin, User
exl-id: 124ff5bf-6612-4baf-b0ff-6b1a95b455c1
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 0%

---


# 市場活動變數 {#campaign-variables}

使用市場活動變數來合成個性化電子郵件內容。 市場活動變數充當可插入電子郵件內容的Adobe Campaign值的佔位符。 當內容通過Adobe Campaign發送時，市場活動將用收件人的個性化內容替換這些變數。

## 使用狀況 {#usage}

電子郵件核心元件使市場活動變數可以通過常用文本欄位旁邊的個性化按鈕輕鬆訪問。 按下時，將顯示一個對話框，您可以從中選擇個性化欄位。

可用個性化設定欄位清單與您的Adobe Campaign實例同步。 在架構中在Adobe Campaign管理欄位 `nms:seedMember`。 中的所有欄位 `nms:seedMember` 收件人表中也必須存在。

## 選擇Adobe Campaign變數對話框 {#dialog}

「選擇Adobe Campaign變數」對話框可在電子郵件核心元件的許多編輯對話框中使用。 要使用它，只需按一下 **選擇Adobe Campaign變數** 表徵圖。 此表徵圖可以採用兩種形式。

![Adobe Campaign按鈕](/help/email/assets/campaign-button.png)
![選擇Adobe Campaign變數表徵圖](/help/email/assets/select-adobe-campaign-variable-icon.png)

按一下兩個表徵圖將開啟 **選擇Adobe Campaign變數** 對話框。

![「選擇Adobe Campaign變數」對話框](assets/select-campaign-variable-dialog.png)

使用列視圖查找要插入的變數。 按一下列中的節點將在右側的新列中顯示其子項。 這樣，您就可以導航可變內容結構。

選擇要插入的變數，然後按一下對話框右上角的複選標籤。

![Adobe Campaign變數已選擇](assets/select-campaign-variable-dialog-selected.png)

然後，變數將插入電子郵件核心元件的編輯對話框的欄位中。

![將市場活動變數插入編輯對話框](assets/campaign-variable.png)

隨時按一下對話框左上角的X以取消和關閉對話框。
