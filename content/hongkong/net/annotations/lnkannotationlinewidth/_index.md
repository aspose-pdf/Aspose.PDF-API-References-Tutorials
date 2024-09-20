---
title: lnk 註解線寬
linktitle: lnk 註解線寬
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 中設定墨跡註解線寬。這個詳細的教學將引導您完成每個步驟，確保高品質的輸出。
type: docs
weight: 110
url: /zh-hant/net/annotations/lnkannotationlinewidth/
---
## 介紹

處理 PDF 文件時，新增註解是突出顯示資訊或向文件添加互動元素的有效方法。其中一種註釋是墨跡註釋，它允許您在 PDF 上繪製自由線條。但是，如果您需要自訂這些線條的外觀，特別是線條寬度，該怎麼辦？在本教學中，我們將引導您完成使用 Aspose.PDF for .NET 設定墨跡註解線寬的過程。

## 先決條件

在深入研究程式碼之前，讓我們確保您已完成所有設定以順利遵循本教學：

1.  Aspose.PDF for .NET：請確定您已安裝 Aspose.PDF for .NET 程式庫。您可以從[下載頁面](https://releases.aspose.com/pdf/net/)或透過 Visual Studio 中的 NuGet 套件管理器安裝它。
2. 開發環境：本教學課程假設您正在 .NET 開發環境（例如 Visual Studio）中工作。
3. C# 基礎知識：對 C# 的基本了解將幫助您遵循編碼步驟。
4. PDF 文件：使用現有的 PDF 文件或為本教學課程建立一個新文件。

## 導入必要的命名空間

在開始編碼之前，請確保在專案中匯入必要的命名空間：

```csharp
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using System;
using System.Collections;
using System.Collections.Generic;
```

這些命名空間提供了操作 PDF 文件、使用註解和處理圖形元素所需的類別和方法。

現在我們已經具備了先決條件，讓我們將設定墨跡註釋線寬度的流程分解為清晰、可管理的步驟。

## 步驟1：初始化PDF文檔

首先，我們需要建立或開啟一個 PDF 文件。在本教程中，我們將從頭開始建立一個新的 PDF 文件。

```csharp
//初始化 PDF 文件
string dataDir = "YOUR DOCUMENT DIRECTORY"; //指定您的文件目錄
Document doc = new Document();
doc.Pages.Add(); //新增空白頁
```

在這裡，我們正在初始化一個新的`Document`對象，它代表我們的 PDF 文件。然後，我們向該文件新增一個空白頁以供使用。

## 步驟 2： 建立墨跡註釋

接下來，我們將創建墨跡註釋本身。這涉及定義構成墨跡筆畫的點。

```csharp
//建立墨跡註釋
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = Color.Red;
lineInfo.LineWidth = 2;
```

在這一步驟中，我們定義`LineInfo`對象，它保存墨跡筆畫的座標、可見性、顏色和初始線寬。這`VerticeCoordinate`陣列包含筆畫中每個點的 X 和 Y 座標。

## 第 3 步：將座標轉換為點

現在，我們需要將這些座標轉換為墨跡註釋可以使用的點。

```csharp
//將座標轉換為點
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
```

此循環處理座標數組，將每對座標轉換為`Point`對象，然後將其添加到我們的`inkList`.

## 步驟 4：將墨跡註解新增至 PDF 頁面

準備好點後，我們現在可以建立墨跡註釋並將其新增到 PDF 頁面。

```csharp
//將墨跡註釋新增至 PDF 頁面
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(Color.Green);
```

在這一步中，我們初始化一個`InkAnnotation`對象，指定頁面、邊界矩形和點列表。我們也設定註釋的主題、標題和顏色。

## 第 5 步：自訂註解邊框

為了進一步自訂註解的外觀，我們將修改其邊框屬性。

```csharp
//自訂註解的邊框
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);
```

在這裡，我們創建一個`Border`我們的註釋對象，設定其寬度、效果、虛線圖案和樣式。此步驟可確保註釋在 PDF 頁面上視覺上突出。

## 步驟 6：儲存 PDF 文檔

最後，進行所有必要的變更後，就可以儲存文件了。

```csharp
//儲存 PDF 文件
dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nInk annotation line width setup successfully.\nFile saved at " + dataDir);
```

此程式碼將修改後的帶有墨跡註解的 PDF 文件保存在指定目錄中。這`Console.WriteLine`語句確認程式碼成功執行。

## 結論

恭喜！您已使用 Aspose.PDF for .NET 在 PDF 文件中成功建立並自訂了墨跡註解。本教學涵蓋了從初始化文件到保存最終文件的整個過程。有了這些知識，您可以進一步探索 Aspose.PDF for .NET 的巨大功能，並將類似的技術應用於其他類型的註解或 PDF 操作。

## 常見問題解答

### 我可以對墨跡註釋的不同部分使用不同的顏色嗎？  
是的，您可以建立多個`InkAnnotation`不同顏色的對象，並將它們新增至 PDF 的相同或不同頁面。

### 如何動態改變線寬？  
您可以調整`LineWidth`的財產`LineInfo`將座標轉換為點之前的物件。

### 是否可以將墨跡註釋設定為透明？  
是的，您可以修改`Opacity`的財產`InkAnnotation`物件使其透明。

### 我可以在同一頁上新增多個墨跡註解嗎？  
絕對地！您可以透過重複此程序為單一頁面新增任意數量的墨跡註解。

### 如何從 PDF 中刪除墨跡註釋？  
您可以使用以下命令刪除註釋`doc.Pages[1].Annotations.Delete(a1)`方法，其中`a1`是你的註解對象。