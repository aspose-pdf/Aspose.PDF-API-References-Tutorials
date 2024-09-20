---
title: 提取 PDF 文件中的全部文本
linktitle: 提取 PDF 文件中的所有文本
second_title: Aspose.PDF for .NET API 參考
description: 透過此逐步教學，了解如何使用 Aspose.PDF for .NET 從 PDF 檔案中輕鬆提取文字。
type: docs
weight: 180
url: /zh-hant/net/programming-with-text/extract-text-all/
---
## 介紹

在這個數位時代，處理PDF文件已經成為一項常見的任務。無論您是想要建立文件處理應用程式的開發人員，還是需要提取重要資料的業務專業人員，了解如何有效地從 PDF 文件中提取文字都可以為您節省大量時間和精力。在本文中，我們將深入介紹 Aspose.PDF for .NET 程式庫的使用，這是一個功能強大的工具，可以幫助您快速輕鬆地從 PDF 文件中提取文字。

## 先決條件

在我們深入了解從 PDF 文件中提取文字的細節之前，您需要滿足一些基本要求：

1. .NET Framework：確保您的開發電腦上安裝了 .NET Framework。 Aspose.PDF 與 .NET 無縫協作，因此擁有最新版本是一個優勢。
2. Aspose.PDF 函式庫：您需要 Aspose.PDF for .NET 函式庫來處理 PDF 作業。你可以[在這裡下載](https://releases.aspose.com/pdf/net/).
3. 開發環境：強烈建議使用 Visual Studio 等 IDE。它提供了一個用戶友好的介面來編寫、構建和調試程式碼。
4. C# 基礎知識：熟悉 C# 程式語言將幫助您更好地理解我們將要探索的程式碼片段。

現在我們已經解決了先決條件，讓我們導入必要的套件！

## 導入包

要開始我們的提取過程，您首先需要在 C# 專案中匯入所需的命名空間。您可以這樣做：

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

這些命名空間將提供對 PDF 操作所需的類別和方法的存取。 

讓我們將提取過程分解為易於遵循的步驟。閱讀本指南後，您將能夠從任何 PDF 文件中無縫提取文字。

## 第 1 步：設定您的文件目錄

您要做的第一件事是指定 PDF 檔案所在的目錄。這對於查找您要使用的文件至關重要。

程式碼範例：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

在此程式碼片段中，只需替換`"YOUR DOCUMENT DIRECTORY"`與 PDF 檔案所在的實際路徑。例如，如果您的檔案位於`C:\Documents`，你會設定`dataDir`到那條路。

## 第 2 步：開啟 PDF 文檔

設定目錄後，您需要開啟要從中提取文字的 PDF 文件。這是使用以下方法完成的`Document`來自 Aspose.PDF 命名空間的類別。

程式碼範例：

```csharp
//開啟文件
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

這裡，確保檔案名稱`ExtractTextAll.pdf`是正確的。這是您將用來提取文字的文件。

## 第 3 步：建立文字吸收器對象

下一步是創建一個`TextAbsorber`目的。這是一個神奇的工具，可以幫助您吸收 PDF 中的所有文字。

程式碼範例：

```csharp
//建立 TextAbsorber 物件來提取文本
TextAbsorber textAbsorber = new TextAbsorber();
```

透過初始化`TextAbsorber`，您準備從 PDF 頁面中提取所有文字內容。

## 第 4 步：接受所有頁面的吸收器

現在您已準備好文字吸收器，您需要使其在 PDF 文件的所有頁面上運作。這可確保捕獲每個頁面的文字。

程式碼範例：

```csharp
//接受所有頁面的吸收器
pdfDocument.Pages.Accept(textAbsorber);
```

透過此步驟，您基本上是在說：“嘿，文字吸收器，繼續收集本文檔中每一頁的所有文字！”

## 第 5 步：檢索提取的文本

一旦文字被吸收，就該把它拉出來了。您可以使用簡單的屬性存取提取的文字。

程式碼範例：

```csharp
//獲取提取的文本
string extractedText = textAbsorber.Text;
```

現在，變數`extractedText`包含從 PDF 收集的所有文字。那有多酷？

## 第 6 步：將提取的文字寫入文件

最後，您可能希望將提取的文字儲存到新的文字檔案中，以便以後輕鬆存取。以下是如何做到這一點。

程式碼範例：

```csharp
//建立編寫器並開啟文件
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
//將一行文字寫入文件
tw.WriteLine(extractedText);
//關閉流
tw.Close();
```

此程式碼開啟一個名為的新文件`extracted-text.txt`，將所有提取的內容寫入其中，然後關閉該文件。所以現在，每當您想查看提取的文字時，只需查看您的文件目錄即可！

## 結論

給你了！只需幾個簡單的步驟，您就可以使用 Aspose.PDF for .NET 從任何 PDF 檔案中提取文字。無論您是建立應用程式來分析文檔，還是只是需要從 PDF 中獲取一些註釋，Aspose.PDF 都提供了強大、易於使用的 API，讓您的生活更輕鬆。記得查看一下[文件](https://reference.aspose.com/pdf/net/)了解這個強大的函式庫提供的更多特性和功能。

## 常見問題解答

### 可以免費使用 Aspose.PDF for .NET 嗎？
是的，Aspose 提供免費試用。你可以下載它[這裡](https://releases.aspose.com/).

### 如果我的 PDF 包含圖像和圖形怎麼辦？
Aspose.PDF專注於文字擷取。如果您的 PDF 包含圖像，您可能需要採用不同的方法來處理它們。

### 有臨時許可證嗎？
絕對地！您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).

### 我可以在哪裡獲得 Aspose.PDF 支援？
您可以在以下位置找到支持和社區討論：[Aspose論壇](https://forum.aspose.com/c/pdf/10).

### 我可以將提取的文字儲存為什麼格式？
您可以將文字儲存為各種格式，例如`.txt`, `.docx`，甚至直接存入資料庫。