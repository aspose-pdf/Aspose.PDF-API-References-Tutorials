---
title: 從圖章註釋中提取文本
linktitle: 從圖章註釋中提取文本
second_title: Aspose.PDF for .NET API 參考
description: 透過此逐步教學（附有詳細的程式碼範例），了解如何使用 Aspose.PDF for .NET 從 PDF 中的圖章註解中擷取文字。
type: docs
weight: 80
url: /zh-hant/net/programming-with-stamps-and-watermarks/extract-text-from-stamp-annotation/
---
## 介紹

處理 PDF 文件時，從註釋中提取特定資料（例如文字）非常方便。在本教學中，我們將逐步指導您如何使用 Aspose.PDF for .NET 從 PDF 文件中的圖章註解中提取文字。這個功能強大的程式庫允許開發人員操作 PDF 文件，從而實現文字提取、註釋管理等任務。讓我們深入了解細節並將其全部分解！

## 先決條件

在我們開始本教學之前，您需要準備一些東西：

-  Aspose.PDF for .NET：您需要安裝 Aspose.PDF for .NET。你可以[在這裡下載最新版本](https://releases.aspose.com/pdf/net/).
- Visual Studio：本指南假設您使用 Visual Studio 作為整合開發環境 (IDE)。
- C# 基礎知識：您應該對 C# 程式設計有基本的了解。

確保您已設定這些工具，以便您可以按照教學進行操作。

## 導入包

任何 .NET 專案的第一步都是導入必要的命名空間。使用 Aspose.PDF，您只需要一些關鍵的導入即可開始：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

這些匯入帶來了處理 PDF 文件、註釋和文字擷取所需的功能。

讓我們逐步完成從圖章註釋中提取文本的過程。這將涉及載入 PDF 文件、識別圖章註釋以及提取文字內容。

## 第 1 步：載入 PDF 文檔

您需要做的第一件事是載入圖章註釋所在的 PDF 檔案。在此範例中，我們將從您的本機目錄載入範例 PDF 檔案。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "test.pdf");
```

在這裡，我們使用的是`Document` Aspose.PDF 提供的類別用於開啟 PDF 檔案並與之互動。這`dataDir`變數代表檔案的路徑。代替`"YOUR DOCUMENT DIRECTORY"`與儲存 PDF 的實際路徑。

## 第 2 步：辨識圖章註釋

PDF 註釋透過其類型和在文件中的位置來標識。在我們的例子中，我們想要在特定頁面上找到圖章註釋。操作方法如下：

```csharp
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;
```

在這行程式碼中：
- `doc.Pages[1]`：存取文件的第一頁。
- `Annotations[3]`：指頁面上的第四個註釋（因為索引從0開始）。
- `as StampAnnotation` ：將註釋轉換為`StampAnnotation`對象，這是我們正在處理的特定類型的註釋。

## 第 3 步：建立文字吸收器

要從圖章註釋中提取文本，我們需要使用文本吸收器。該工具將幫助我們吸收或捕獲 PDF 特定區域（在本例中為註釋）中的文字。

```csharp
TextAbsorber ta = new TextAbsorber();
```

這`TextAbsorber`類別旨在從文件的任何部分提取文本，我們將使用它來定位註釋的外觀。

## 步驟4：提取圖章註釋的外觀

PDF 中的圖章註釋具有關聯的外觀，通常以 XForm 的形式儲存。我們需要檢索此外觀以存取圖章內的實際文字。

```csharp
XForm ap = annot.Appearance["N"];
```

這裡：
- `annot.Appearance["N"]`：檢索名為“N”的外觀流（代表註釋的正常外觀）。

## 步驟5：提取文字內容

現在我們已經有了外觀，我們可以使用`TextAbsorber`訪問外觀並捕獲文字。

```csharp
ta.Visit(ap);
```

這`Visit`方法允許`TextAbsorber`分析外觀並提取其中嵌入的任何文字內容。

## 第 6 步：顯示提取的文本

最後，提取文字後，我們可以將其輸出到控制台或儲存以供進一步使用。

```csharp
Console.WriteLine(ta.Text);
```

這行簡單的程式碼在控制台視窗中顯示提取的文字。您還可以根據需要將其保存到文件或進一步操作它。

## 結論

使用 PDF 文件中的註釋（尤其是圖章註釋）可以為您的應用程式添加重要的功能。透過 Aspose.PDF for .NET，您擁有一組強大的工具，可以輕鬆提取資料、操作註釋以及以有意義的方式與 PDF 互動。在本教程中，我們向您展示瞭如何透過幾個簡單的步驟從圖章註釋中提取文字。現在輪到您在專案中試驗這些功能了！

## 常見問題解答

### 我可以使用 Aspose.PDF 從其他類型的註解中提取文字嗎？  
是的，Aspose.PDF 允許您從各種類型的註釋中提取文本，例如文本註釋、自由文本註釋等，而不僅僅是圖章註釋。

### Aspose.PDF支援新增自訂註解嗎？  
絕對地！ Aspose.PDF 支援在 PDF 文件中建立和新增自訂註釋，讓您可以靈活地管理和呈現資料。

### 我可以從圖章註釋中提取圖像嗎？  
是的，您可以使用類似的方法透過存取外觀和檢索影像資料從圖章註釋中提取影像。

### Aspose.PDF for .NET 也提供哪些其他功能？  
Aspose.PDF for .NET 提供了廣泛的功能，包括文字操作、表單欄位處理、文件轉換等等。

### Aspose.PDF for .NET 是免費的嗎？  
 Aspose.PDF for .NET 提供免費試用版，但要存取全套功能，您需要購買授權。您還可以申請[臨時執照](https://purchase.aspose.com/temporary-license/).