---
title: PDF 文件中的分組複選框
linktitle: PDF 文件中的分組複選框
second_title: Aspose.PDF for .NET API 參考
description: 透過此逐步教學課程，了解如何使用 Aspose.PDF for .NET 在 PDF 文件中建立分組複選框（單選按鈕）。
type: docs
weight: 170
url: /zh-hant/net/programming-with-forms/grouped-check-boxes/
---
## 介紹

建立互動式 PDF 並不像聽起來那麼困難，尤其是當您擁有 Aspose.PDF for .NET 等強大工具時。您可能需要新增至 PDF 文件中的互動元素之一是分組複選框，或更具體地說，是允許使用者從一組選項中選擇一個選項的單選按鈕。本教學將引導您完成使用 Aspose.PDF for .NET 將分組複選框（單選按鈕）新增至 PDF 文件的過程。無論您是初學者還是經驗豐富的開發人員，您都會發現本指南引人入勝、詳細且易於遵循。

## 先決條件

在我們深入了解逐步指南之前，讓我們先介紹一些基本的先決條件：

1.  Aspose.PDF for .NET：請確定您已安裝 Aspose.PDF 庫。如果沒有，您可以[在這裡下載](https://releases.aspose.com/pdf/net/).
2. IDE：您應該設定一個開發環境，例如 Visual Studio。
3. .NET Framework：此專案應針對與 Aspose.PDF 相容的 .NET Framework 版本。
4. 基本 C# 知識：需要熟悉 C# 和 PDF 操作才能順利進行操作。
5. 許可證：Aspose.PDF 需要完整功能的許可證。你可以[獲得臨時許可證](https://purchase.aspose.com/temporary-license/)如果需要的話。

## 導入包

在開始之前，請確保您已將必要的命名空間匯入到您的專案中：

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Forms;
```

這些套件將使您能夠存取操作 PDF 文件所需的所有類別和方法，包括建立單選按鈕和定義其屬性。

在本節中，我們將把建立分組複選框（單選按鈕）的過程分解為清晰、易於遵循的步驟。

## 第 1 步：建立新的 PDF 文檔

第一步是建立一個實例`Document`對象，它將代表您的 PDF 文件。然後，在文件中新增一個空白頁，您將在其中放置分組的複選框。

```csharp
//實例化文檔對象
Document pdfDocument = new Document();

//將頁面新增至 PDF 文件
Page page = pdfDocument.Pages.Add();
```

這為為 PDF 添加任何元素（例如單選按鈕）奠定了基礎。

## 第 2 步：初始化單選按鈕字段

接下來，我們需要建立一個`RadioButtonField`對象，它將保存分組的複選框（單選按鈕）。此欄位將會新增至將顯示複選框的特定頁面。

```csharp
//實例化RadioButtonField物件並將其指派給第一頁
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

將此視為將各個單選按鈕選項組合在一起的容器。

## 第 3 步：新增單選按鈕選項

現在，讓我們將單獨的單選按鈕選項新增到該欄位。在此範例中，我們將新增兩個單選按鈕並使用`Rectangle`目的。

```csharp
//新增第一個單選按鈕選項並使用 Rectangle 指定其位置
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));

//設定選項名稱以供識別
opt1.OptionName = "Option1";
opt2.OptionName = "Option2";
```

在這裡，`Rectangle`物件定義頁面上每個單選按鈕的座標和大小。

## 第四步：自訂單選按鈕的樣式

您可以透過設定單選按鈕來自訂單選按鈕的外觀`Style`財產。例如，您可能需要方形複選框或十字形複選框。

```csharp
//設定單選按鈕的樣式
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Cross;
```

這使您可以控制複選框的外觀和感覺，使它們更加用戶友好且具有視覺吸引力。

## 步驟 5：配置邊框屬性

邊框在使復選框易於識別方面發揮著至關重要的作用。在這裡，我們將在每個單選按鈕選項周圍添加實心邊框並定義它們的寬度和顏色。

```csharp
//配置第一個單選按鈕的邊框
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt1.Characteristics.Border = Color.Black;

//配置第二個單選按鈕的邊框
opt2.Border = new Border(opt2);
opt2.Border.Style = BorderStyle.Solid;
opt2.Border.Width = 1;
opt2.Characteristics.Border = Color.Black;
```

此步驟可確保每個單選按鈕都有明確定義的邊框，從而提高文件的可讀性。

## 第 6 步：將單選按鈕選項新增至表單

現在，我們將單選按鈕新增到文件的表單中。這是將複選框分組到單一欄位下的最後一步。

```csharp
//將單選按鈕欄位新增至文件的表單對象
pdfDocument.Form.Add(radio);
```

表單物件充當所有互動元素的容器，包括我們分組的複選框。

## 第7步：儲存PDF文檔

最後，一切設定完畢後，您可以將 PDF 文件儲存到您想要的位置。

```csharp
//定義輸出檔案路徑
string dataDir = "YOUR DOCUMENT DIRECTORY" + "GroupedCheckBoxes_out.pdf";

//儲存 PDF 文件
pdfDocument.Save(dataDir);

//確認創建成功
Console.WriteLine("Grouped checkboxes added successfully. File saved at " + dataDir);
```

就是這樣！您已使用 Aspose.PDF for .NET 成功建立了具有分組複選框的 PDF。

## 結論

在 PDF 文件中新增分組複選框等互動式元素一開始似乎很棘手，但使用 Aspose.PDF for .NET，一切都變得輕而易舉。透過遵循本逐步指南，您已了解如何設定基本 PDF 文件、新增分組單選按鈕、自訂其外觀以及儲存最終結果。無論您是要建立表單、調查或任何其他類型的互動式 PDF，本指南都可以為您提供堅實的入門基礎。

## 常見問題解答

### 我可以在群組中新增兩個以上的單選按鈕嗎？
絕對地！只需實例化額外的`RadioButtonOptionField`對象並將它們添加到`RadioButtonField`如教程所示。

### 如何處理一個文件中的多組複選框？
若要建立多個群組，請實例化單獨的群組`RadioButtonField`每個組別的物件。

### 我可以添加的複選框數量有限制嗎？
不會，Aspose.PDF for .NET 不會對您可以新增至 PDF 的複選框數量施加任何限制。

### 新增複選框後我可以更改它們的外觀嗎？
是的，您可以在新增複選框後修改邊框樣式、寬度和顏色等屬性。

### 是否可以使用圖像作為單選按鈕？
是的，Aspose.PDF 允許您透過設定將自訂圖像用作單選按鈕`Appearance`每個單選按鈕選項的屬性。