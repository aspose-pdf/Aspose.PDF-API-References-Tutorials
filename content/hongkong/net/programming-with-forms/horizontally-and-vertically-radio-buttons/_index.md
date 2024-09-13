---
title: 水平和垂直單選按鈕
linktitle: 水平和垂直單選按鈕
second_title: Aspose.PDF for .NET API 參考
description: 透過此逐步教學，了解如何使用 Aspose.PDF for .NET 在 PDF 中建立水平和垂直對齊的單選按鈕。
type: docs
weight: 180
url: /zh-hant/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
## 介紹

建立互動式 PDF 表單可以顯著增強使用者體驗，尤其是在收集資訊時。最常見的表單元素之一是單選按鈕，它允許使用者從一組選項中選擇一個選項。在本教學中，我們將探索如何使用 Aspose.PDF for .NET 建立水平和垂直對齊的單選按鈕。無論您是經驗豐富的開發人員還是新手，本指南都將逐步引導您完成整個過程，確保您清楚地了解每個部分。

## 先決條件

在深入研究程式碼之前，您應該滿足一些先決條件：

1.  Aspose.PDF for .NET：請確定您已安裝 Aspose.PDF 庫。您可以從[地點](https://releases.aspose.com/pdf/net/).
2. Visual Studio：一個可以編寫和測試程式碼的開發環境。
3. C# 基礎知識：熟悉 C# 程式設計將有助於您更好地理解程式碼片段。

## 導入包

首先，您需要在 C# 專案中匯入必要的套件。您可以這樣做：

### 建立一個新項目

開啟 Visual Studio 並建立一個新的 C# 專案。為了簡單起見，您可以選擇控制台應用程式。

### 新增 Aspose.PDF 參考

1. 在解決方案資源管理器中以滑鼠右鍵按一下您的專案。
2. 選擇“管理 NuGet 套件”。
3. 搜尋“Aspose.PDF”並安裝最新版本。

```csharp
using System;
using System.IO;
using Aspose.Pdf.Facades;
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

現在您已完成所有設置，讓我們分解程式碼以建立水平和垂直對齊的單選按鈕。

## 第 1 步：設定文檔目錄

在此步驟中，我們將定義儲存 PDF 文件的目錄路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`與您要儲存 PDF 檔案的實際路徑。這很重要，因為它告訴程式在哪裡找到輸入檔案以及在哪裡保存輸出。

## 步驟2：載入現有的PDF文檔

接下來，我們需要載入我們將要使用的 PDF 文件。這是使用以下方法完成的`FormEditor`班級。

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

在這裡，我們建立一個實例`FormEditor`並將其綁定到名為的現有 PDF 文件`input.pdf`。確保該檔案存在於您指定的目錄中。

## 步驟 3：配置單選按鈕屬性

現在，讓我們為單選按鈕設定一些屬性。這包括按鈕之間的間隙、它們的方向和它們的大小。

```csharp
formEditor.RadioGap = 4; //單選按鈕選項之間的距離
formEditor.RadioHoriz = true; //設定為 true 以進行水平對齊
formEditor.RadioButtonItemSize = 20; //單選按鈕的大小
formEditor.Facade.BorderWidth = 1; //邊框寬度
formEditor.Facade.BorderColor = System.Drawing.Color.Black; //邊框顏色
```

這些屬性將有助於定義單選按鈕在 PDF 中的顯示方式。這`RadioGap`屬性控制按鈕之間的空間，而`RadioHoriz`決定了他們的佈局。

## 第 4 步：新增水平單選按鈕

現在，讓我們將水平單選按鈕新增到 PDF 中。

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

在此程式碼中，我們定義單選按鈕的項目並將它們新增至 PDF。這`AddField`方法採用多個參數，包括欄位類型、欄位名稱和放置座標。

## 第 5 步：新增垂直單選按鈕

接下來，我們將新增垂直單選按鈕。為此，我們需要將方向更改回垂直。

```csharp
formEditor.RadioHoriz = false; //設定為 false 進行垂直對齊
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

就像以前一樣，我們定義項目並將它們添加到 PDF，但這次它們將垂直對齊。

## 步驟 6：儲存 PDF 文檔

最後，我們需要儲存修改後的PDF文件。

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
```

此程式碼使用新新增的單選按鈕儲存 PDF。確保檢查指定目錄中的輸出檔案。

## 結論

使用 Aspose.PDF for .NET 在 PDF 中建立單選按鈕是一個簡單的過程。透過遵循本教學中概述的步驟，您可以輕鬆地將水平和垂直對齊的單選按鈕新增至 PDF 表單中。這不僅增強了文件的互動性，也改善了整體使用者體驗。所以，繼續嘗試吧！

## 常見問題解答

### 什麼是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一個功能強大的程式庫，可讓開發人員以程式設計方式建立、操作和轉換 PDF 文件。

### 我可以免費使用 Aspose.PDF 嗎？
是的，Aspose 提供免費試用版，您可以使用它來評估該程式庫。你可以下載它[這裡](https://releases.aspose.com/).

### 如何獲得 Aspose.PDF 支援？
您可以透過訪問獲得支持[Aspose論壇](https://forum.aspose.com/c/pdf/10).

### 是否可以使用 Aspose.PDF 建立其他表單元素？
絕對地！ Aspose.PDF支援各種表單元素，包括文字欄位、複選框和下拉式清單。

### 哪裡可以購買 Aspose.PDF for .NET？
您可以從以下位置購買 Aspose.PDF for .NET[購買頁面](https://purchase.aspose.com/buy).