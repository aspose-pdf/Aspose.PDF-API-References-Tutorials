---
title: 將 Java 腳本新增至 PDF 文件
linktitle: 新增 Java 腳本 PDF 文件
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 將 JavaScript 新增至 PDF 檔案。包含文件和頁面層級腳本編寫程式碼教學的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-document/addjavascripttopage/
---
## 介紹

您是否想知道如何使用彈出警報或自動列印功能等互動式元素來增強您的 PDF？好消息－你可以！透過使用 Aspose.PDF for .NET，您可以將 JavaScript 無縫地新增到 PDF 文件中。無論您是要自動化任務還是建立動態使用者體驗，在 PDF 中嵌入 JavaScript 都可以為您的文件提供額外的功能。

## 先決條件

在我們進入編碼部分之前，您需要設定一些內容：

-  Aspose.PDF for .NET：從下列位置下載資料庫[Aspose 發布](https://releases.aspose.com/pdf/net/)或得到一個[免費試用](https://releases.aspose.com/).
- 開發環境：任何與 .NET 相容的 IDE，例如 Visual Studio。
- 基本 C# 知識：本指南假設您熟悉基本 C# 文法。
- 臨時許可證（可選）：您可以獲得[臨時執照](https://purchase.aspose.com/temporary-license/)如果您想在開發過程中避免限制。

## 導入包

在開始編寫程式碼之前，您需要從 Aspose.PDF 庫中匯入必要的命名空間。這些命名空間將允許您輕鬆操作 PDF 並新增 JavaScript 操作。

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

現在您已經匯入了正確的命名空間，您就可以開始編碼了。

## 第 1 步：載入現有 PDF

首先，您需要載入要新增 JavaScript 的 PDF 文件。此步驟為所有進一步修改奠定了基礎。想像一下，您有一個 PDF，想要透過動態功能來增強，例如在開啟時自動列印文件。

以下是載入該 PDF 檔案的方法：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//載入現有 PDF 文件
Document doc = new Document(dataDir + "input.pdf");
```

在此程式碼片段中，我們使用`Document`類別從指定目錄載入現有 PDF 檔案。確保更換`"YOUR DOCUMENT DIRECTORY"`與 PDF 檔案的實際路徑。

## 步驟 2：在文件層級新增 JavaScript

現在，讓我們加入一些在文件開啟時觸發的 JavaScript。在此範例中，我們將編寫一個腳本，在使用者開啟 PDF 時立即開啟列印對話方塊。

文件級 JavaScript 非常適合您想要套用於整個 PDF 的操作。可以將其視為為文件設定全域規則。

這是代碼：

```csharp
//在文件層級新增 JavaScript
//使用所需的 JavaScript 語句實例化 JavascriptAction
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

//將JavascriptAction物件分配給Document的OpenAction
doc.OpenAction = javaScript;
```

在這一步中，我們創建一個`JavascriptAction`定義 JavaScript 函數的對象，用於在開啟文件時開啟列印對話方塊。這`doc.OpenAction`然後將屬性指派給此 JavaScript 操作。

## 第 3 步：在頁面層級新增 JavaScript

並非每個操作都需要影響整個文件。有時，您希望在開啟或關閉某些頁面時發生特定操作。在這裡，我們將設定開啟和關閉特定頁面（假設第 2 頁）時的 JavaScript 操作。

頁面層級 JavaScript 對於有針對性的互動非常有用。它可以是任何內容，從使用者導航到頁面時顯示訊息到自動填寫表單欄位等自訂操作。

操作方法如下：

```csharp
//在頁面層級新增 JavaScript
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('Page 2 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('Page 2 closed')");
```

在此程式碼片段中，我們新增兩個 JavaScript 操作：
1. OnOpen 操作：當使用者開啟第 2 頁時，顯示一則警告「第 2 頁已開啟」。
2. OnClose 操作：當使用者離開第 2 頁時，顯示一則警告「第 2 頁已關閉」。

這為您的 PDF 添加了一層互動性。想像一下，引導使用者完成不同頁面上的一系列步驟，並在使用者進入或離開頁面時彈出警報。

## 步驟 4：儲存 PDF 文檔

您現在已將 JavaScript 新增至文件和特定頁面。最後一步是將修改後的 PDF 儲存到您想要的位置。這部分很簡單但至關重要 - 不要忘記保存您的工作！

這是代碼：

```csharp
//指定輸出檔案路徑
dataDir = dataDir + "JavaScript-Added_out.pdf";

//儲存更新的 PDF 文檔
doc.Save(dataDir);

Console.WriteLine("\nJavaScript added successfully to the PDF.\nFile saved at " + dataDir);
```

在此程式碼片段中，我們將新增了 JavaScript 的更新文件儲存到名為的新檔案中`"JavaScript-Added_out.pdf"`。這可以確保您不會覆蓋原始文件，並且可以為您提供備份以供使用。

## 結論

使用 Aspose.PDF for .NET 將 JavaScript 新增至 PDF 檔案是建立互動式動態 PDF 的強大方法。無論您是要自動執行列印等任務還是建立自訂警報，將 JavaScript 嵌入到 PDF 中的功能都可以使您的文件更具吸引力和功能性。

## 常見問題解答

### 我可以將多個 JavaScript 操作新增至 PDF 中的不同頁面嗎？
是的，您可以將不同的 JavaScript 操作指派給各個頁面或整個文件。

### 新增 JavaScript 後是否可以從 PDF 刪除 JavaScript？
是的，您可以透過清除`Actions`文檔或頁面的屬性。

### 我可以在 PDF 中使用哪些類型的 JavaScript 函數？
您可以使用 Adobe Acrobat 的 JavaScript 引擎支援的任何 JavaScript，例如列印、警報和表單操作。

### JavaScript 是否適用於所有 PDF 檢視器？
大多數 JavaScript 操作都可以在支援互動式 PDF 的 PDF 檢視器（例如 Adobe Acrobat）中執行。但是，一些基本的 PDF 閱讀器可能不支援 JavaScript。

### 我可以根據 PDF 中的使用者輸入觸發 JavaScript 操作嗎？
是的，您可以將 JavaScript 綁定到表單欄位以根據使用者輸入觸發操作。