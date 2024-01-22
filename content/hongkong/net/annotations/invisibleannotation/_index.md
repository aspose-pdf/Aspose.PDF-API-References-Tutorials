---
title: PDF 檔案中的隱形註釋
linktitle: PDF 檔案中的隱形註釋
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 C# 原始程式碼和 Aspose.PDF for .NET 在 PDF 檔案中隱藏註解。逐步指南。
type: docs
weight: 100
url: /zh-hant/net/annotations/invisibleannotation/
---
PDF 文件中的註釋是一項強大的功能，可讓您為文件添加額外的資訊或註釋，而無需更改實際內容。它們可用於突出顯示文字、引起對文件特定區域的注意或添加評論或回饋。

您可以在 PDF 文件中使用多種不同類型的註釋，包括：

- 文字註釋
- 連結註釋
- 印章註釋
- 聲音註釋
- 文件附件註釋
- 還有很多

## 步驟 1：使用 Aspose.PDF for .NET 在 PDF 文件中建立不可見註釋

要使用 Aspose.PDF for .NET 在 PDF 文件中建立不可見註釋，我們首先需要建立一個`FreeTextAnnotation`物件並指定註釋的位置和大小。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開啟文件
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
```

在上面的程式碼中，我們創建了一個`FreeTextAnnotation`物件並指定 PDF 文件第 2 頁上的註釋位置。我們也指定註釋中顯示的文字的字體類型、大小和顏色。

## 步驟 2：為不可見註解新增特徵

接下來，我們可以為註解添加一些特徵，例如邊框顏色、背景顏色或不透明度。

```csharp
annotation.Characteristics.Border = System.Drawing.Color.Red;
```

在上面的程式碼中，我們將註解的邊框顏色設定為紅色。

## 第 3 步：設定註釋標誌

建立註釋並設定其特徵後，我們可以指定註釋標誌。在本教程中，我們希望註釋可列印，但不可查看。

```csharp
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);
```

## 第四步：儲存修改後的PDF文檔

最後，我們可以使用新的不可見註解來儲存修改後的PDF文件。

```csharp
dataDir = dataDir + "InvisibleAnnotation_out.pdf";
doc.Save(dataDir);
```

## 如何使用 Aspose.PDF for .NET 進行不可見註解的範例原始程式碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開啟文件
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
annotation.Contents = "ABCDEFG";
annotation.Characteristics.Border = System.Drawing.Color.Red;
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);

dataDir = dataDir + "InvisibleAnnotation_out.pdf";
//儲存輸出檔案
doc.Save(dataDir);
//ExEnd:InvisibleAnnotation
Console.WriteLine("\nAnnotation nvisible successfully.\nFile saved at " + dataDir);
```

## 結論

在本教學中，我們學習如何使用 Aspose.PDF for .NET 在 PDF 文件中建立不可見註解。當您想要在文件中添加額外資訊或註釋而不向讀者顯示它們時，不可見註釋是一個有用的功能。透過遵循逐步指南並使用提供的 C# 原始程式碼，開發人員可以輕鬆地在 PDF 文件中建立和自訂不可見註釋。 Aspose.PDF for .NET 提供了一整套用於處理註解的工具，讓您能夠增強 PDF 檔案的互動性和可用性。

### 常見問題解答

#### Q：什麼是 PDF 文件中的隱形註釋？

答：PDF文件中的不可見註解是指在頁面上不可見但包含附加資訊或註解的註解。它允許您添加評論或回饋，而無需向讀者顯示它們。

#### Q：什麼類型的特徵可以加入不可見註解？

答：可以為不可見註解添加各種特徵，例如邊框顏色、背景顏色、不透明度、字體類型、大小以及將顯示的文字的顏色。

#### Q：我可以為不可見註釋設定不同的註釋標誌嗎？

答：是的，您可以根據您的需求為不可見註釋設定不同的註釋標誌。例如，您可以使註釋可列印但不可查看。

#### Q：如何為 PDF 文件的特定頁面新增不可見註解？

答：要為PDF文件的特定頁面新增不可見註釋，您需要建立一個`FreeTextAnnotation`物件並指定該頁面上註解的位置和大小。

#### Q：我可以修改 PDF 檔案中現有不可見註解的特徵嗎？

答：是的，您可以使用 Aspose.PDF for .NET 修改 PDF 檔案中現有不可見註解的特徵。您可以變更註解的字體類型、大小、顏色、邊框顏色、背景顏色、不透明度和其他屬性。