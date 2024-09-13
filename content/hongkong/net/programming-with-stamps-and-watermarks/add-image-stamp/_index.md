---
title: 在 PDF 檔案中新增圖像戳記
linktitle: 在 PDF 檔案中新增圖像戳記
second_title: Aspose.PDF for .NET API 參考
description: 透過逐步指導和範例程式碼，了解如何使用 Aspose.PDF for .NET 將圖像圖章新增至 PDF 檔案。
type: docs
weight: 20
url: /zh-hant/net/programming-with-stamps-and-watermarks/add-image-stamp/
---
## 介紹

在處理 PDF 檔案時，很少有工具像 Aspose.PDF for .NET 一樣強大且使用者友好。無論您是要添加註釋、建立表單還是蓋章圖像，該程式庫都提供了廣泛的功能來滿足各種 PDF 操作需求。在本教程中，我們將重點放在一項特定任務：將圖像圖章新增至 PDF 檔案。這不僅僅是將圖像放到頁面上；而是將圖像貼到頁面上。這是關於透過品牌和視覺吸引力來增強您的文件！

## 先決條件

在深入研究程式碼的細節之前，讓我們確保您已擁有所需的一切。這是您需要的：

1. Visual Studio 或任何 .NET IDE：您需要有一個 .NET 開發環境來實作程式碼片段。
2.  Aspose.PDF for .NET Library：這是我們將要使用的主要工具。您可以從以下位置下載該庫的最新版本[Aspose 發佈頁面](https://releases.aspose.com/pdf/net/).
3. C# 基礎知識：對 C# 程式設計的基本了解將幫助您順利瀏覽程式碼。
4. 圖像檔案：您需要一個要用作圖章的圖像檔案。確保它採用支援的格式（如 JPEG、PNG 等）。
5. 現有 PDF 文件：擁有一個範例 PDF 文件，您將在其中添加圖像圖章。

現在我們已經準備好了，讓我們開始編寫程式碼吧！

## 導入包

首先，在執行任何操作之前，您需要匯入必要的命名空間。在 C# 程式碼中，您可以透過在檔案頂部新增以下 using 指令來執行此操作：

```csharp
using System.IO;
using Aspose.Pdf;
using System;
using Aspose.Pdf.Text;
```

這將允許您存取 Aspose.PDF 庫提供的各種類別和方法。

## 第 1 步：設定您的文件目錄

第一步是指定文檔的路徑。您需要將文件和影像儲存在明確定義的目錄中。為了簡單起見，請宣告一個變數`dataDir`像這樣：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

確保更換`"YOUR DOCUMENT DIRECTORY"`與系統上的實際路徑。

## 第 2 步：開啟 PDF 文檔

接下來，我們需要開啟我們想要修改的PDF文件。這就是 Aspose.PDF 的閃光點！你只需要幾行程式碼：

```csharp
Document pdfDocument = new Document(dataDir + "AddImageStamp.pdf");
```

該行創建了一個新的`Document`透過載入指定的 PDF 檔案來物件。確保該檔案存在於您指定的目錄中；否則，您將遇到文件未找到的錯誤！

## 第 3 步：建立圖像圖章

現在到了有趣的部分——添加圖像印章！首先，我們需要使用您的圖像檔案建立一個圖像圖章物件：

```csharp
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");
```

該行初始化一個`ImageStamp`代表您要新增的圖像的物件。檢查影像檔案路徑是否正確至關重要。

## 步驟 4：配置影像標記屬性

您可以在這裡發揮創意並自訂您的印章。您可以設定位置、大小、旋轉和不透明度等屬性。以下是如何執行此操作的範例：

```csharp
imageStamp.Background = true; //如果您希望圖章位於背景中，則設定為 true
imageStamp.XIndent = 100; //位置從左開始
imageStamp.YIndent = 100; //從頂部開始的位置
imageStamp.Height = 300; //設定印章的高度
imageStamp.Width = 300; //設定印章的寬度
imageStamp.Rotate = Rotation.on270; //如果需要的話可以旋轉
imageStamp.Opacity = 0.5; //設定不透明度
```

請根據您的要求隨意調整這些值！透過這種自訂，您可以將印章準確地放置在您想要的位置。

## 步驟 5：將圖章新增至特定頁面

現在我們已經配置了圖章，下一步是指定我們想要將其放置在 PDF 文件中的位置。在此範例中，我們將其新增至第一頁：

```csharp
pdfDocument.Pages[1].AddStamp(imageStamp);
```

此程式碼片段告訴 Aspose 將圖章加入到文件的第一頁。

## 第 6 步：儲存文檔

套用圖章後，就可以儲存變更了。您需要指定輸出 PDF 檔案的路徑：

```csharp
dataDir = dataDir + "AddImageStamp_out.pdf";
pdfDocument.Save(dataDir);
```

您的文件現已儲存並套用了新的圖像印記！

## 第7步：確認修改

最後，確認您的操作是否成功總是好的。您可以使用簡單的控制台訊息來完成此操作：

```csharp
Console.WriteLine("\nImage stamp added successfully.\nFile saved at " + dataDir);
```

此訊息將通知您已新增圖像戳記，並告知您在哪裡可以找到新修改的 PDF。

## 結論

恭喜！您剛剛使用 Aspose.PDF for .NET 將圖像圖章新增至 PDF。乍看之下似乎很複雜，但經過一些練習，您可以透過多種方式自訂您的 PDF 文件。這裡的關鍵是嘗試 Aspose 提供的各種屬性 - 您的想像力是有限的。

## 常見問題解答

### Aspose.PDF for .NET 可以免費使用嗎？  
 Aspose.PDF提供免費試用，但試用期結束後需要許可證才能繼續使用。您可以查看[定價選項在這裡](https://purchase.aspose.com/buy).

### 我可以將多個圖章新增到單一 PDF 中嗎？  
絕對地！您可以建立多個`ImageStamp`物件並將它們新增至 PDF 中的任何頁面。

### 郵票支援哪些圖像格式？  
Aspose.PDF支援各種影像格式，包括JPEG、PNG和BMP。

### 如何旋轉圖像圖章？  
您可以設定`Rotate`的財產`ImageStamp`物件以所需角度旋轉影像。選項包括`Rotation.on90`, `Rotation.on180`， ETC。

### 在哪裡可以找到有關 Aspose.PDF 的更多文件？  
您可以瀏覽完整的 API 參考和文檔[這裡](https://reference.aspose.com/pdf/net/).