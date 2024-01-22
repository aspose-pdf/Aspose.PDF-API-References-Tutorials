---
title: 使用子集策略在 PDF 檔案中嵌入字體
linktitle: 使用子集策略嵌入字體
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 透過子集策略在 PDF 檔案中嵌入字型。透過僅嵌入必要的字元來優化 PDF 大小。
type: docs
weight: 130
url: /zh-hant/net/programming-with-document/embedfontsusingsubsetstrategy/
---
在本教學中，我們將討論如何使用 Aspose.PDF for .NET 透過子集策略在 PDF 檔案中嵌入字體。 Aspose.PDF for .NET 是一個功能強大的程式庫，可讓開發人員以程式設計方式建立、編輯和操作 PDF 文件。在 PDF 檔案中嵌入字型是確保文件在不同裝置上正確顯示的重要步驟，無論這些裝置上是否安裝了所需的字型。

## 步驟 1：建立一個新的 C# 控制台應用程式
首先，在 Visual Studio 中建立一個新的 C# 控制台應用程式。您可以將其命名為任何您喜歡的名稱。建立專案後，您需要新增對 Aspose.PDF for .NET 程式庫的參考。

## 步驟2：導入Aspose.PDF命名空間
在 C# 檔案頂部新增以下程式碼行以匯入 Aspose.PDF 命名空間：

```csharp
using Aspose.Pdf;
```

## 第 3 步：載入現有 PDF 文件
要將字體嵌入到現有 PDF 文件中，您需要使用 Document 類別載入該文件。以下程式碼示範如何載入現有的 PDF 檔案：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//載入現有 PDF 文件
Document doc = new Document(dataDir + "input.pdf");
```

## 步驟 4：使用子集策略嵌入字體
Aspose.PDF for .NET 提供了兩種字體嵌入策略：SubsetAllFonts 和 SubsetEmbeddedFontsOnly。

SubsetAllFonts 策略將把所有字體作為子集嵌入到文件中。子集是字體的一部分，僅包含文件中使用的字元。此策略對於減小 PDF 文件的檔案大小非常有用。

SubsetEmbeddedFontsOnly 策略將僅嵌入已嵌入文件中的字體子集。如果未嵌入字體，則不會受到此策略的影響。

以下程式碼示範如何使用子集策略在 PDF 檔案中嵌入字體：

```csharp
//對於 SubsetAllFonts，所有字體都會作為子集嵌入到文件中。
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);

//對於完全嵌入的字體，將嵌入字體子集，但未嵌入文件的字體不會受到影響。
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
```

## 第5步：儲存PDF文檔
使用子集策略將所有字型嵌入 PDF 檔案後，您需要儲存文件。以下程式碼示範如何儲存PDF檔案：

```csharp
doc.Save(dataDir + "Output_out.pdf");
```

### 使用 Aspose.PDF for .NET 透過子集策略嵌入字體的範例原始程式碼。 

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
//對於 SubsetAllFonts，所有字體都會作為子集嵌入到文件中。
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);
//對於完全嵌入的字體，將嵌入字體子集，但未嵌入文件的字體不會受到影響。
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
doc.Save(dataDir + "Output_out.pdf");
```

## 結論
在本文中，我們討論如何使用 Aspose.PDF for .NET 透過子集策略在 PDF 檔案中嵌入字體。 Aspose.PDF for .NET 提供了一個簡單易用的 API 來處理 PDF 文檔，包括使用不同策略新增和嵌入字體。在PDF文件中嵌入字型是確保文件在不同裝置上正確顯示的重要步驟，而子集策略是減少PDF文件文件大小的實用功能。

### 使用子集策略在 PDF 文件中嵌入字體的常見問題解答

#### Q：PDF 文件中字體嵌入的子集策略是什麼？

答：PDF 文件中字體嵌入的子集策略意味著僅嵌入包含文件中使用的字元的字體部分。這有助於透過消除不必要的字型資料來減小 PDF 文件的檔案大小。

#### Q：SubsetAllFonts 和 SubsetEmbeddedFontsOnly 策略有什麼區別？

答： 的`SubsetAllFonts`策略將把所有字體作為子集嵌入到文件中，而`SubsetEmbeddedFontsOnly`策略將僅嵌入已嵌入文件中的字體子集。後一種策略不會影響尚未嵌入的字體。

#### Q：為什麼採用子集策略的字體嵌入很重要？

答：採用子集策略的字體嵌入對於確保 PDF 文件包含正確顯示文字所需的字體資料非常重要，同時還可以透過僅包含文件中使用的字元來保持較小的文件大小。

#### Q：我可以使用 Aspose.PDF for .NET 嵌入不同策略的字體嗎？

答：是的，Aspose.PDF for .NET 提供了各種字體嵌入策略，包括`SubsetAllFonts`和`SubsetEmbeddedFontsOnly`。您可以根據您的需求選擇合適的策略。

#### Q：Aspose.PDF for .NET 是處理 PDF 文件的可靠資料庫嗎？

答：是的，Aspose.PDF for .NET 是一個可靠且功能強大的 PDF 文件庫。它提供了在 .NET 應用程式中建立、編輯和操作 PDF 文件的豐富功能。