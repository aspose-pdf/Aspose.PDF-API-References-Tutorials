---
title: 新增lnk註釋
linktitle: 新增lnk註釋
second_title: Aspose.PDF for .NET API 參考
description: 在這個引人入勝的逐步指南中，學習如何使用 Aspose.PDF for .NET 將墨跡註解新增至 PDF 檔案。
type: docs
weight: 20
url: /zh-hant/net/annotations/addlnkannotation/
---
## 介紹

歡迎來到使用 Aspose.PDF for .NET 進行 PDF 操作的世界！如果您希望增強您的 PDF 文檔，無論是用於專業用途、個人專案還是介於兩者之間的任何用途，那麼您來對地方了。今天，我們將深入研究 Aspose.PDF 的一個具體但實用的功能：在 PDF 文件中添加墨跡註釋。當您想要在文件中添加類似手寫的註釋或簽名，使文件更具互動性和吸引力時，此功能非常有用。

## 先決條件

在我們深入研究編碼魔法之前，讓我們確保您已具備開始使用所需的一切：

1. .NET Framework：確保您的電腦上安裝了 .NET。該程式庫可與各種版本的 .NET 無縫協作，包括 .NET Core。
2.  Aspose.PDF 庫：您需要下載 .NET 的 Aspose.PDF 庫並在專案中引用。如果您還沒有這樣做，您可以從以下位置取得最新版本[下載連結](https://releases.aspose.com/pdf/net/).
3. 程式碼編輯器：您可以使用您選擇的任何程式碼編輯器，但強烈建議使用 Visual Studio，因為它易於與 .NET 應用程式一起使用。
4. 對 C# 的基本了解：C# 的實用知識將幫助您順利瀏覽編碼範例。
5. 設定您的開發環境：確保您的 IDE 設定為處理 .NET 項目，並且您已在專案中正確引用了 Aspose.PDF 庫。 

滿足這些先決條件後，您就可以開始為 PDF 添加墨跡註釋了！

## 導入包

在開始編碼之前，讓我們先導入必要的套件。在 C# 檔案的頂部，加入以下 using 語句：

```csharp
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
using System;
using System.Collections;
using System.Collections.Generic;
```

這將使您能夠存取使用 PDF 註釋所需的所有類別和方法。

現在我們已經做好了準備，是時候捲起袖子開始討論細節了！我們將分解每個步驟，以確保您準確了解如何建立墨跡註釋並將其新增至 PDF 文件。

## 步驟1：設定文檔和目錄

您要做的第一件事是設定文件以及要儲存輸出文件的路徑。 

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
```
我們定義一個變數`dataDir`，它指向保存生成的 PDF 的目錄。這`Document`然後實例化對象，建立一個新的 PDF 文件進行編輯。

## 第 2 步：向文件新增頁面

接下來，您需要為新建立的文件新增頁面。

```csharp
Page pdfPage = doc.Pages.Add();
```
在這裡，我們為文件新增一個新頁面。每個PDF至少需要一頁，所以這一步是不可或缺的。

## 第 3 步：定義繪圖矩形

在繪製任何內容之前，您需要定義在頁面上放置墨跡註釋的位置。

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
```
在這裡，我們創建一個`Rectangle`對象，指定頁面上我們將添加墨跡註釋的區域。我們將其尺寸設定為適合整個頁面，從 (0,0) 開始。

## 第四步：準備墨點

現在到了有趣的部分 - 定義構成墨跡註釋的點。 

```csharp
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
```
此程式碼區塊建立一個點數組列表，其中每個數組代表墨跡筆畫的一組點。在這裡，我們定義三個點形成一個三角形；您可以調整座標以適合您的設計。

## 第 5 步：建立墨跡註釋

定義點後，就可以建立實際的墨跡註解了。

```csharp
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList)
{
    Title = "XXX",
    Color = Aspose.Pdf.Color.LightBlue,
    CapStyle = CapStyle.Rounded
};
```
我們實例化`InkAnnotation`對象，傳入頁、矩形和墨點。此外，我們正在設定一些屬性，例如`Title`, `Color`， 和`CapStyle`。客製化這些以滿足您的需求！

## 步驟6：設定邊框和不透明度

想讓您的註解脫穎而出嗎？讓我們給它一些風格。

```csharp
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
```
在這裡，我們向註釋添加特定寬度的邊框並設定其不透明度，使其半透明。

## 第 7 步：將註釋新增至頁面

現在您的註釋已準備就緒，是時候將其新增至 PDF 頁面了。

```csharp
pdfPage.Annotations.Add(ia);
```
此行將我們先前建立的墨跡註解新增至頁面的註解集合中。 

## 第 8 步：儲存文檔

最後，讓我們儲存修改後的文件。

```csharp
dataDir = dataDir + "AddInkAnnotation_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nInk annotation added successfully.\nFile saved at " + dataDir);
```
我們修改我們的`dataDir`包含輸出檔名並儲存文件。控制台會列印確認訊息，讓您知道一切順利。

## 結論

現在你就擁有了！您已使用 Aspose.PDF for .NET 成功將墨跡註解新增至 PDF 文件。這個簡單而有效的功能可以增強您的文件並使它們具有互動性。無論您是添加簽名、註釋還是塗鴉，墨跡註釋都提供了豐富內容的獨特方式。

## 常見問題解答

### 什麼是Aspose.PDF？
Aspose.PDF 是一個用於在 .NET 應用程式中建立、操作和轉換 PDF 文件的程式庫。

### 我可以免費使用 Aspose.PDF 嗎？
是的！ Aspose 提供免費試用版來評估其產品。你可以下載它[這裡](https://releases.aspose.com/).

### 是否可以新增多個墨跡註解？
絕對地！您可以建立多個`InkAnnotation`物件並將它們新增至文件頁面。

### 我在哪裡可以找到更多範例？
您可以查看[文件](https://reference.aspose.com/pdf/net/)取得詳細教學和範例。

### 如果我需要支援該怎麼辦？
如果您遇到任何問題，可以透過以下方式尋求協助[支援論壇](https://forum.aspose.com/c/pdf/10).