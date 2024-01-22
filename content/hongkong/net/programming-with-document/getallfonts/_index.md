---
title: 取得PDF檔案中的所有字體
linktitle: 取得PDF檔案中的所有字體
second_title: Aspose.PDF for .NET API 參考
description: 透過此逐步指南和範例程式碼，了解如何使用 Aspose.PDF for .NET 以程式設計方式取得 PDF 檔案中使用的所有字體。
type: docs
weight: 160
url: /zh-hant/net/programming-with-document/getallfonts/
---
Aspose.PDF for .NET 是一個功能強大的程式庫，可讓開發人員以程式設計方式處理 PDF 檔案。它提供的功能之一是能夠取得 PDF 文件中使用的所有字體。如果您需要以程式設計方式分析或操作 PDF 文件中的字體，這會很有用。

在本教學中，我們將討論如何使用 Aspose.PDF for .NET 來取得 PDF 文件中使用的所有字型。我們將提供有關如何執行此操作的逐步指南以及範例原始程式碼。

## 步驟 1：建立一個新的 C# 控制台應用程式
首先，在 Visual Studio 中建立一個新的 C# 控制台應用程式。您可以將其命名為任何您喜歡的名稱。建立專案後，您需要新增對 Aspose.PDF for .NET 程式庫的參考。

## 步驟2：導入Aspose.PDF命名空間
在 C# 檔案頂部新增以下程式碼行以匯入 Aspose.PDF 命名空間：

```csharp
using Aspose.Pdf;
```

## 第 3 步：載入 PDF 文檔
載入您想要從中取得字體的 PDF 文件：

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 第四步：取得所有字體
取得PDF文件中使用的所有字體：

```csharp
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
```

## 步驟5：列印所有字體
列印PDF文件中使用的所有字型：

```csharp
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

### 使用 Aspose.PDF for .NET 取得所有字體的範例原始碼
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

## 結論
在本教學中，我們討論如何使用 Aspose.PDF for .NET 來取得 PDF 文件中使用的所有字型。如果您需要以程式設計方式分析或操作 PDF 文件中的字體，取得 PDF 文件中使用的所有字體可能會很有用。 Aspose.PDF for .NET 提供了一個簡單易用的 API 來處理 PDF 文檔，包括取得 PDF 文件中使用的所有字體。

### 常見問題解答

#### Q：為什麼我需要取得 PDF 文件中使用的所有字體？

答：如果您需要以程式設計方式分析或操作字體以用於各種目的（例如字體替換或字體自訂），那麼取得 PDF 文件中使用的所有字體可能會很有用。

#### Q：如何使用 Aspose.PDF for .NET 取得 PDF 文件中使用的所有字型？

答：您可以透過呼叫 Aspose.PDF for .NET 來取得 PDF 文件中使用的所有字體`GetAllFonts`的方法`FontUtilities`班級。該方法傳回一個數組`Aspose.Pdf.Text.Font`對象，代表 PDF 文件中使用的字體。

#### Q：我可以根據某些條件過濾字體嗎？

答：是的，您可以使用 Aspose.PDF for .NET 根據某些條件過濾字體。取得所有字體後，您可以以程式設計方式分析字體並根據需要套用過濾邏輯。

#### Q：Aspose.PDF for .NET 是否相容於各種字體格式？

答：是的，Aspose.PDF for .NET 與各種字型格式相容，包括 TrueType、OpenType 和 Type 1 字型。它可以使用不同的字體格式並在 PDF 文件操作期間處理它們。