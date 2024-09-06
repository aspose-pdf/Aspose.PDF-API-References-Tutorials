---
title: 在頁面上繪製 XForm
linktitle: 在頁面上繪製 XForm
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 在 PDF 頁面上繪製 XForm 表單的逐步指南。新增表單並將其放置在頁面上。
type: docs
weight: 10
url: /zh-hant/net/programming-with-operators/draw-xform-on-page/
---
在本教學中，我們將為您提供如何使用 Aspose.PDF for .NET 在頁面上繪製 XForm 的逐步指南。 Aspose.PDF 是一個功能強大的程式庫，可讓您以程式設計方式建立、操作和轉換 PDF 文件。使用 Aspose.PDF 提供的運算符，您可以在現有 PDF 頁面上新增和定位 XForm 表單。

## 先決條件

在開始之前，請確保您具備以下先決條件：

1. 隨 .NET Framework 安裝的 Visual Studio。
2. 適用於 .NET 的 Aspose.PDF 庫。

## 第 1 步：項目設置

首先，在 Visual Studio 中建立一個新專案並新增對 Aspose.PDF for .NET 程式庫的參考。您可以從Aspose官方網站下載該程式庫並將其安裝到您的電腦上。

## 第 2 步：導入必要的命名空間

在您的 C# 程式碼檔案中，匯入存取 Aspose.PDF 提供的類別和方法所需的命名空間：

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## 第三步：設定檔案路徑

定義背景影像、輸入PDF檔案和輸出PDF檔案的檔案路徑：

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

請務必指定電腦上的實際檔案路徑。

## 第 4 步：載入輸入 PDF 文件

使用以下程式碼載入輸入 PDF 檔案：

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
//以下程式碼使用 GSave/GRestore 運算符
//程式碼使用 ContatenateMatrix 運算子來定位 XForm
//程式碼使用Do操作符在頁面上繪製XForm
// GSave/GRestore 運算子包裝現有內容
//這樣做是為了在現有內容末尾獲取初始圖形狀態
//否則，現有操作符鏈的末端可能會留下不必要的轉換
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
//新增 GSave 運算子以在新指令後正確重設圖形狀態
pageContents. Add(new GSave());

//建立 XForm
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
//設定圖像的寬度和高度
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
//將圖像載入到流中
Stream imageStream = new FileStream(imageFile, FileMode.Open);
//將圖像新增至 XForm 資源圖像集合
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
//使用 Do 運算子：此運算子繪製影像
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
//將 XForm 放置在座標 x=100 和 y=500 處
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
//使用 Do 運算子繪製 XForm
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
//將 XForm 放置在座標 x=100 和 y=300 處
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
//使用 Do 運算子繪製 XForm
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

//GSave 之後使用 GRestore 還原圖形狀態
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

請務必指定實際檔案路徑並根據需要調整頁碼和 XForm 位置。

### 使用 Aspose.PDF for .NET 在頁面上繪製 XForm 的範例原始程式碼
 
```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	//範例示範了
	//GSave/GRestore 運算子用法
	//ContatenateMatrix 運算子用於定位 xForm
	//使用運算符在頁面上繪製 xForm
	//使用 GSave/GRestore 運算子對包裝現有內容
	//這是為了獲取現有內容的初始圖形狀態
	//否則，現有運營商鏈的末端可能會殘留一些不良的轉變
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	//新增儲存圖形狀態運算子以在新指令後正確清除圖形狀態
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	//建立xForm
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	//定義影像寬度和高度
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	//將圖像載入到流中
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	//將圖像新增至 XForm 資源的圖像集合中
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	//使用 Do 運算子：此運算子繪製影像
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	//將表單放置到 x=100 y=500 座標
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	//使用 Do 運算子繪製表格
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	//將表單放置到 x=100 y=300 座標
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	//使用 Do 運算子繪製表格
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	//GSave 之後使用 GRestore 還原圖形狀態
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## 結論

在本教學中，您學習如何使用 Aspose.PDF for .NET 在 PDF 頁面上繪製 XForm 表單。透過執行所述的步驟，您將能夠在現有頁面上新增和定位 XForm 表單，從而為 PDF 文件提供更大的靈活性。

### 頁面上繪製 XForm 的常見問題解答

#### Q：Aspose.PDF 中的 XForm 是什麼？

答：XForm 是 PDF 文件中可重複使用的圖形物件。它允許您定義和繪製可以在不同頁面上重複使用多次的複雜圖形、圖像或文字。

#### Q：如何匯入 Aspose.PDF 所需的命名空間？

答：在您的 C# 程式碼檔案中，使用`using`指令匯入存取 Aspose.PDF 提供的類別和方法所需的命名空間：
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### Q：GSave 和 GRestore 運算子的目的為何？

答： 的`GSave`和`GRestore` Aspose.PDF中的運算子用於儲存和還原圖形狀態。它們有助於確保應用於內容某一部分的轉換和設定不會影響後續部分。

#### Q：如何使用 Aspose.PDF 定義 XForm？

答：要建立 XForm，請使用`XForm.CreateNewForm`方法並將其添加到`Resources.Forms`特定頁面的集合。然後您可以將內容新增到 XForm 的`Contents`財產。

#### Q：如何在 XForm 中繪製影像？

A：將圖像載入到流中並將其新增至`Resources.Images`XForm 的集合。使用`Do`XForm 中的運算符`Contents`繪製影像。

#### Q：如何在 PDF 頁面上放置 XForm？

答：要將 XForm 放置在頁面上，請使用`ConcatenateMatrix`頁面內的運算符`Contents`。調整矩陣參數以指定 XForm 的平移（位置）和縮放。

#### Q：我可以在同一頁上繪製多個 XForm 嗎？

答：是的，您可以在同一頁上繪製多個 XForm，只需調整`ConcatenateMatrix`將每個 XForm 定位在不同座標的參數。

#### Q：XForm 創建後可以修改其內容嗎？

答：是的，您可以在建立後透過向其新增附加運算子來修改 XForm 的內容`Contents`財產。

#### Q：如果我省略 GSave 和 GRestore 運算符，會發生什麼事？

答：省略 GSave 和 GRestore 運算子可能會導致不必要的轉換或設定套用於後續內容。使用它們有助於保持乾淨的圖形狀態。

#### Q：我可以在 PDF 文件的不同頁面上重複使用 XForms 嗎？

答：是的，您可以透過將相同的 XForm 新增至頁面來在多個頁面上重複使用 XForm。`Resources.Forms`不同頁面的集合。

#### Q：我可以建立的 XForm 數量有限制嗎？

答：雖然對可以創建的 XForm 數量沒有嚴格限制，但請記住，太多的 XForm 可能會影響效能和記憶體使用。明智地使用它們。

#### Q：我可以旋轉 XForm 或套用其他轉換嗎？

答：是的，您可以使用`ConcatenateMatrix`運算子將旋轉、縮放和平移等變換應用到 XForm。
