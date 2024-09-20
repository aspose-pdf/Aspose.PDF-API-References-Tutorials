---
title: PDF 檔案中的文字段
linktitle: PDF 檔案中的文字段
second_title: Aspose.PDF for .NET API 參考
description: 了解如何在 Aspose.PDF for .NET 中使用正規表示式搜尋 PDF 檔案中的特定文字段。
type: docs
weight: 540
url: /zh-hant/net/programming-with-text/text-segments/
---
## 介紹

PDF 文件在當今的數位世界中無處不在，通常用於從正式報告到電子書的各種內容。但從它們中提取文字有時就像大海撈針一樣。幸運的是，在 Aspose.PDF for .NET 等函式庫的幫助下，這項任務變得更加簡單！在本指南中，我們將介紹如何使用 Aspose.PDF 從 PDF 中提取特定文字段，並將其分解為清晰、可操作的步驟。 

## 先決條件

在深入了解文字擷取的實質內容之前，您需要滿足以下條件：

1. Visual Studio：確保您的電腦上安裝了 Visual Studio。這是我們編寫程式碼的地方。
2. .NET Framework 或 .NET Core 環境：確保您擁有適合您的應用程式的環境。 Aspose 同時支援 .NET Framework 和 .NET Core。
3.  Aspose.PDF 函式庫：您需要 Aspose.PDF for .NET 函式庫。如果您還沒有安裝，可以下載[這裡](https://releases.aspose.com/pdf/net/).
4. C# 基本知識：熟悉 C# 會有所幫助，但即使您是初學者，我們也會引導您逐步完成程式碼。
5. PDF 文件：手邊準備一個要從中提取文字的 PDF 文件。這可以是從財務報告到文章的任何內容。

## 導入包

現在您已完成所有設置，下一步是在 C# 程式中匯入必要的套件。這一點至關重要，因為它允許您存取 Aspose.PDF 庫的所有強大功能。

### 建立一個新項目

- 開啟 Visual Studio 並建立一個新的 C# 專案。為了簡單起見，您可以選擇控制台應用程式。

### 新增 Aspose.PDF 參考

- 右鍵單擊`References`解決方案資源管理器中的資料夾。
- 選擇「新增引用」並瀏覽至下載 Aspose.PDF.dll 的位置。
- 將此 DLL 新增至您的專案中。此步驟將您的項目連接到 Aspose.PDF 庫，解鎖其功能。

### 導入命名空間

在 C# 檔案的頂部，您需要包含 Aspose.PDF 命名空間：

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```
這告訴您的程式使用 Aspose.PDF 庫中的類別和方法。

讓我們透過實際例子來分解提取各種類型的文字片段。我們將使用`TextFragmentAbsorber`類，這是從 PDF 文件中尋找和提取文字的關鍵。

## 步驟1：初始化文檔

要使用任何 PDF，您需要將其加載到您的應用程式中。方法如下：

```csharp
//載入 PDF 文件
Document pdfDocument = new Document("Path/To/Your/PDFFile.pdf");
```
代替`"Path/To/Your/PDFFile.pdf"`與 PDF 的實際路徑。

## 步驟2：建立一個TextFragmentAbsorber

現在，讓我們探討一下使用的不同範例`TextFragmentAbsorber`檢索文字。

### 範例 1：提取精確的單字

要查找特定單字的精確匹配，您可以初始化`TextFragmentAbsorber`像這樣：

```csharp
//搜尋與「Word」完全匹配的內容
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"\bWord\b", new TextSearchOptions(true));
```
此程式碼設定吸收器精確查找單字“Word”，並將其視為整個單字。這`\b`表示單字邊界。

### 範例 2：不區分大小寫的搜尋

如果您想尋找特定字串（無論大小寫）（例如“line”），請按以下步驟操作：

```csharp
//以不區分大小寫的方式搜尋字串“Line”
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("(?i)Line", new TextSearchOptions(true));
```
這`(?i)`使搜尋忽略大小寫。 

### 範例 3：從 PDF 中提取所有文本

是否曾經需要解析 PDF 中的所有文字？這是一個簡單的方法：

```csharp
//解析PDF文件中的所有字串
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
```
正規表示式`[\S]+`捕獲所有非空白字元。 

## 第 3 步：接受文件中的吸收器

現在，您需要接受 PDF 文件中的吸收器：

```csharp
//接受文件中的吸收體
pdfDocument.Pages.Accept(textFragmentAbsorber);
```
該行告訴 PDF 文件處理您已初始化的吸收器。

## 第 4 步：檢索並顯示結果

最後，讓我們檢索提取的文字並顯示它。您可以這樣做：

```csharp
//取得擷取的文字片段
TextFragmentCollection textFragments = textFragmentAbsorber.TextFragments;

//循環遍歷每個片段並輸出
foreach (TextFragment textFragment in textFragments)
{
    Console.WriteLine(textFragment.Text);
}
```
此循環處理找到的每個片段並將其列印到控制台。

## 結論

從 PDF 文件中提取文字不一定是一項艱鉅的任務。透過 Aspose.PDF for .NET，您可以有效率地找出並提取所需的資訊。無論您是想抓取單字還是解析整個文檔，正規表示式的靈活性都可以滿足您的需求。`TextFragmentAbsorber`為您提供強大的搜尋功能。那為什麼還要等呢？立即深入研究您的 PDF 文件並開始提取有價值的見解！

## 常見問題解答

### 什麼是 Aspose.PDF for .NET？
Aspose.PDF 是一個功能強大的程式庫，用於在 .NET 應用程式中建立、操作和轉換 PDF 檔案。

### 我可以在 .NET Core 應用程式中使用 Aspose.PDF 嗎？
是的，Aspose.PDF for .NET 支援 .NET Framework 和 .NET Core 應用程式。

### 有免費試用嗎？
絕對地！您可以下載免費試用版[這裡](https://releases.aspose.com/).

### 我可以在哪裡獲得 Aspose.PDF 支援？
您可以聯絡 Aspose 支持社區[這裡](https://forum.aspose.com/c/pdf/10).

### 如何購買 Aspose.PDF 的授權？
您可以購買許可證[這裡](https://purchase.aspose.com/buy).