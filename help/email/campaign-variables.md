---
title: Campaign 變數
description: 使用 Campaign 變數做為預留位置，以撰寫個人化電子郵件內容。
role: Developer, Admin, User
exl-id: 124ff5bf-6612-4baf-b0ff-6b1a95b455c1
index: false
TQID: https://experienceleague.adobe.com/MB6K-S4DZbsD3puXls8w4rWi6posFFLxJRewKORMkxA
product_v2: id: c45915cf-e157-4af7-a80d-97b905bcb3a5id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: eb3ad9f8-54a2-45f3-abb1-d3976415a718
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: ce44533e-8ec8-4e11-a9e9-78b0fe561832id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 73aa5234ac63fa3be99feebce448bb6722513838
workflow-type: tm+mt
source-wordcount: 296
ht-degree: 100%

---

# Campaign 變數 {#campaign-variables}

使用 Campaign 變數來撰寫個人化電子郵件內容。 Campaign 變數作為 Adobe Campaign 值預留位置，可以插入至電子郵件內容。 透過 Adobe Campaign 傳送內容時，Campaign 會以收件者的個人化內容取代這些變數。

## 用途 {#usage}

「電子郵件核心元件」可讓您透過常見文字欄位旁的個人化按鈕，輕鬆存取 Campaign 變數。 按下時，會出現一個對話框，您可以從中選取個人化欄位。

可用的個人化欄位清單已與您的 Adobe Campaign 執行個體同步。 這些欄位是在結構描述 `nms:seedMember` 中管理的。 `nms:seedMember` 中的所有欄位也必須出現在您的收件者表格中。

## 選取 Adobe Campaign 變數對話框 {#dialog}

選取 Adobe Campaign 變數對話框可用於電子郵件核心元件的許多編輯對話框。 若要使用，只要按一下適用欄位旁的&#x200B;**選取 Adobe Campaign 變數**&#x200B;圖示即可。 此圖示有兩種形式。

![Adobe Campaign 按鈕](/help/email/assets/campaign-button.png)
![選取 Adobe Campaign 變數圖示](/help/email/assets/select-adobe-campaign-variable-icon.png)

按一下這兩個圖示會開啟&#x200B;**選取 Adobe Campaign 變數**&#x200B;對話框。

![選取 Adobe Campaign 變數對話框](assets/select-campaign-variable-dialog.png)

使用欄檢視來找出您要插入的變數。 按一下欄中的節點，會在右側的新欄中顯示其下層。 如此一來，您便可導覽變數內容結構。

選取您要插入的變數，然後按一下對話框右上角的核取記號。

![已選取 Adobe Campaign 變數](assets/select-campaign-variable-dialog-selected.png)

然後，變數會插入電子郵件核心元件編輯對話框的欄位中。

![Campaign 變數已插入至編輯對話框](assets/campaign-variable.png)

隨時按一下對話框左上方的 X，即可取消並關閉對話框。
