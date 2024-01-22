---
title: 使用文字片段和段落旋轉文本
linktitle: 使用文字片段和段落旋轉文本
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中使用文字片段和段落來旋轉文字。
type: docs
weight: 400
url: /zh-hant/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
本教學介紹如何使用 Aspose.PDF for .NET 使用文字片段和段落旋轉文字。提供的 C# 原始程式碼逐步演示了該過程。

## 先決條件

在繼續學習本教學之前，請確保您具備以下條件：

- C# 程式語言的基礎知識。
- 安裝了 Aspose.PDF for .NET 函式庫。您可以從 Aspose 網站取得它或使用 NuGet 將其安裝到您的專案中。

## 第 1 步：設定項目

首先在您首選的整合開發環境 (IDE) 中建立一個新的 C# 項目，並新增對 Aspose.PDF for .NET 程式庫的參考。

## 步驟2：導入必要的命名空間

在 C# 檔案的開頭新增以下 using 指令以匯入所需的命名空間：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 步驟 3：建立 PDF 文檔

初始化`Document`物件建立一個新的 PDF 文件：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

確保更換`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

## 第 4 步：新增頁面

使用以下命令從文件中取得特定頁面`Pages.Add()`方法：

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## 第 5 步：建立文字片段

創建多個`TextFragment`對象，設定其文字和屬性，並指定旋轉角度：

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 315;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 270;
```

根據需要調整文字、旋轉角度和其他屬性。

## 步驟 6：為頁面新增文字片段

透過將已建立的文字片段附加到`Paragraphs`收藏：

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## 步驟7：儲存PDF文檔

使用以下命令將修改後的 PDF 文件儲存到文件中`Save`方法：

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

確保更換`"TextFragmentTests_Rotated3_out.pdf"`與所需的輸出檔名。

### 使用 Aspose.PDF for .NET 使用文字片段和段落旋轉文字的範例原始程式碼 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
//初始化文檔對象
Document pdfDocument = new Document();
//取得特定頁面
Page pdfPage = (Page)pdfDocument.Pages.Add();
//建立文字片段
TextFragment textFragment1 = new TextFragment("main text");
//設定文字屬性
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
//建立文字片段
TextFragment textFragment2 = new TextFragment("rotated text");
//設定文字屬性
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
//設定旋轉
textFragment2.TextState.Rotation = 315;
//建立文字片段
TextFragment textFragment3 = new TextFragment("rotated text");
//設定文字屬性
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
//設定旋轉
textFragment3.TextState.Rotation = 270;
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
//儲存文件
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

## 結論

恭喜！您已成功學習如何使用 Aspose.PDF for .NET 在 PDF 文件中使用文字片段和段落來旋轉文字。本教學提供了從建立文件到儲存修改版本的逐步指南。現在，您可以將此程式碼合併到您自己的 C# 專案中，以操作 PDF 文件中的文字旋轉。

### 常見問題解答

#### Q：「使用文字片段和段落旋轉文字」教學的目的是什麼？

答：「使用文字片段和段落旋轉文字」教學課程旨在引導您完成使用 .NET 的 Aspose.PDF 庫使用 PDF 文件中的文字片段和段落旋轉文字的過程。本教學提供了實現此功能的逐步說明和範例程式碼。

#### Q：本教學與之前的文字旋轉教學有何不同？

答：本教學結合使用文字片段和段落來實現 PDF 文件中的文字旋轉。它演示瞭如何單獨旋轉文字片段，然後將它們添加到頁面的`Paragraphs`集合實現更全面的文字旋轉效果。

#### Q：使用文字片段和段落進行文字旋轉有什麼好處？

答：同時使用文字片段和段落可以使文字旋轉更加靈活。文字片段支援單獨的旋轉和格式設置，而段落則提供用於在頁面內排列和定位文字片段的結構。

#### Q：我可以對同一段落內的不同文字片段套用不同的旋轉角度嗎？

答：是的，您可以對不同的應用應用不同的旋轉角度`TextFragment`同一段落中的物件。每個文字片段都可以使用指定的自己的旋轉角度`TextState.Rotation`財產。

#### Q：用這種方法可以達到複雜的文字旋轉效果嗎？

答：是的，透過將不同旋轉角度的文字片段組合併排列在段落內，您可以實現複雜且自訂的文字旋轉效果，增強 PDF 文件的視覺吸引力。

#### Q：使用文字片段和段落旋轉文字涉及哪些步驟？

答：步驟包括：

1. 透過建立新的 C# 專案並新增對 Aspose.PDF for .NET 庫的參考來設定專案。
2. 建立 PDF 文件並新增頁面。
3. 建立文字片段、設定其屬性並指定旋轉角度。
4. 使用以下命令將文字片段新增至頁面`Paragraphs`收藏。
5. 儲存修改後的 PDF 文件。

#### Q：我可以對整個段落應用旋轉嗎？

答：是的，您可以透過設定將旋轉應用於整個段落`TextState.Rotation`段落本身的屬性。這將旋轉該段落內的所有文字片段。