---
title: 設定 PDF 檔案中的圖像大小
linktitle: 設定 PDF 檔案中的圖像大小
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 設定 PDF 中的圖片大小。本逐步指南將協助您調整影像大小、調整頁面屬性和儲存 PDF。
type: docs
weight: 270
url: /zh-hant/net/programming-with-images/set-image-size/
---
## 介紹

使用 PDF 是許多應用程式的常見要求，並且操作 PDF 文件中的元素的能力至關重要。無論您是建立報告產生器還是為 PDF 新增動態內容，控製文件中影像的大小都是一項重要功能。在本教學中，我們將引導您了解如何使用 Aspose.PDF for .NET 設定 PDF 檔案中的圖片大小。這個強大的程式庫提供了對 PDF 內容的廣泛控制，我們將逐步分解它，向您展示它是多麼容易。最後，您將能夠自信地調整圖像大小並了解此功能如何增強您的 PDF 工作流程。


## 先決條件

在我們深入研究程式碼之前，您需要準備好一些東西才能遵循本教程。

1.  Aspose.PDF for .NET：請確定您安裝了最新版本的 Aspose.PDF 庫。你可以[在這裡下載](https://releases.aspose.com/pdf/net/).
2. .NET Framework 或 .NET Core：請確定您擁有設定了 .NET Framework 或 .NET Core 的工作環境。
3. C# 的基本知識：我們將使用 C# 作為我們的程式語言，因此熟悉它是至關重要的。
4. 範例圖像：您需要將範例圖像嵌入到 PDF 中。您可以使用任何您喜歡的圖像，但請確保它可以在您的專案目錄中存取。

## 導入包

若要使用 Aspose.PDF for .NET，首先需要匯入必要的命名空間。這是一個簡單的設定：

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

現在我們已經掌握了基礎知識，讓我們繼續建立和修改 PDF 文件。

## 步驟 1：初始化您的 PDF 文檔

我們需要做的第一件事是建立一個新的 PDF 文件。我們將使用`Document`Aspose.PDF 中的類別來完成此任務。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//實例化文檔對象
Document doc = new Document();
```
 
在這裡，我們實例化一個`Document`對象，它將代表我們的 PDF 文件。我們也使用以下命令指定檔案所在的目錄`dataDir`多變的。這是使用 Aspose.PDF 建立任何 PDF 的起點。

## 步驟 2： 在 PDF 中新增頁面

準備好文件後，我們需要向其中新增頁面。每個 PDF 必須至少有一頁，所以讓我們新增一頁。

```csharp
//將頁面新增至 PDF 檔案的頁面集合
Aspose.Pdf.Page page = doc.Pages.Add();
```
 
我們使用以下命令為文件新增頁面`Pages.Add()`方法。此頁面將充當我們放置圖像的畫布。 PDF 中的每個頁面本質上都是一張白紙，您可以在其中添加文字、圖像或其他內容。

## 步驟3：建立映像實例

現在是時候準備我們想要插入 PDF 的圖像了。 Aspose.PDF提供了一個`Image`處理影像的類別。

```csharp
//建立圖像實例
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```
 
我們建立一個新的實例`Image`班級。該物件將保存我們要新增到 PDF 的圖像的屬性。我們將在接下來的步驟中配置影像的大小和類型。

## 步驟 4：設定影像尺寸（寬度和高度）

這是我們教學的核心：設定圖像的大小。 Aspose.PDF 可讓您以磅為單位指定影像的寬度和高度。

```csharp
//設定影像寬度和高度（以磅為單位）
img.FixWidth = 100;
img.FixHeight = 100;
```
 
這`FixWidth`和`FixHeight`屬性可讓您設定影像的精確尺寸（以磅為單位）。在此範例中，我們將影像大小調整為 100x100 點。您可以調整這些值以滿足您的需求。

## 第 5 步：指定圖像類型

根據您使用的圖像格式，您可能需要設定圖像類型。 Aspose.PDF支援各種影像格式，這裡我們定義檔案類型。

```csharp
//將圖像類型設定為 SVG
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
```
 
在本例中，我們將文件類型保留為`Unknown`，它允許庫自動檢測圖像類型。如果您知道特定的文件類型，則可以設定它（例如，`ImageFileType.Jpeg`對於 JPEG 影像）。此步驟可確保 Aspose 知道如何正確處理影像。

## 第 6 步：設定影像檔案的路徑

現在我們需要告訴 Aspose 在哪裡可以找到圖像檔案。確保您的圖像可以在指定的目錄中存取。

```csharp
//來源檔案路徑
img.File = dataDir + "aspose-logo.jpg";
```
 
在這裡，我們設定圖像的檔案路徑。在本例中，影像位於`dataDir`資料夾並命名為`aspose-logo.jpg`。確保將其替換為圖像檔案的實際名稱和位置。

## 第 7 步：將圖像新增至頁面

配置圖像並設定檔案路徑後，我們現在可以將圖像新增到頁面中。

```csharp
//將圖像新增至段落集合中
page.Paragraphs.Add(img);
```
 
這`Paragraphs.Add()`方法允許我們將圖像添加到頁面。想想`Paragraphs`集合作為將在 PDF 頁面上呈現的項目清單。我們可以為該集合添加多個元素，例如圖像、文字和形狀。

## 步驟8：調整頁面屬性

為了確保我們的圖像適合，我們將調整頁面大小。這將確保頁面尺寸與我們添加的內容相符。

```csharp
//設定頁面屬性
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```
 
在這裡，我們將頁面寬度和高度設定為 800 點。此步驟是可選的，但可確保頁面容納調整大小的圖像。您可以根據您的具體要求調整這些值。

## 第 9 步：儲存 PDF

最後，配置好影像和頁面屬性後，我們就可以儲存PDF了。

```csharp
//儲存生成的 PDF 文件
dataDir = dataDir + "SetImageSize_out.pdf";
doc.Save(dataDir);
```
 
我們將修改後的文件另存為`SetImageSize_out.pdf`在同一目錄中。該檔案現在將包含您新增的調整大小的圖像。

## 結論

在本教學中，我們介紹如何使用 Aspose.PDF for .NET 設定 PDF 中的圖片大小。我們逐步完成了建立文件、新增頁面、配置影像和儲存結果的過程。本逐步指南只是您使用 Aspose.PDF for .NET 的開始。現在您已經了解如何調整圖像大小，可以隨意探索其他功能，例如文字格式設定、表格創建，甚至在 PDF 中添加註釋。

## 常見問題解答

### 我可以在 Aspose.PDF for .NET 中使用不同的影像格式嗎？  
是的，Aspose.PDF 支援各種影像格式，例如 JPEG、PNG、BMP 和 SVG。

### 如何保持影像的長寬比？  
您可以透過設定以下任一方式來保持縱橫比`FixWidth`或者`FixHeight`同時保持另一個維度未設定。

### 我可以將多個圖像新增至單一 PDF 頁面嗎？  
絕對地！只需重複添加圖像實例的過程並將每個圖像添加到`Paragraphs`收藏。

### 是否可以以點以外的單位設定影像尺寸？  
Aspose.PDF 主要使用點，但您可以將其他單位（如英吋或毫米）轉換為點（1 英吋 = 72 點）。

### 如何將圖像放置在頁面上的特定位置？  
您可以設定`Image.LowerLeftX`和`Image.LowerLeftY`用於在頁面上定位圖像的屬性。