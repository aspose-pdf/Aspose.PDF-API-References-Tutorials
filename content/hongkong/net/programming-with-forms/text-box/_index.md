---
title: 文字方塊
linktitle: 文字方塊
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中建立文字欄位。
type: docs
weight: 290
url: /zh-hant/net/programming-with-forms/text-box/
---
在本指南中，我們將逐步解釋如何使用 .NET 的 Aspose.PDF 庫在 PDF 文件中建立文字欄位。我們將向您展示如何開啟文件、建立文字欄位、自訂其屬性以及儲存編輯後的 PDF。

## 步驟1：配置文檔目錄

第一步是配置您要處理的 PDF 文件所在的文檔目錄。您可以使用`dataDir`變數來指定目錄路徑。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

一定要更換`"YOUR DOCUMENTS DIRECTORY"`與文檔目錄的實際路徑。

## 步驟 2：開啟 PDF 文檔

在此步驟中，我們將使用以下命令開啟 PDF 文檔`Document`Aspose.PDF 類別。

```csharp
Document pdfDocument = new Document(dataDir + "TextField.pdf");
```

確保指定的文檔目錄中存在 PDF 檔案。

## 第 3 步：建立文字字段

我們將使用以下命令建立一個文字字段`TextBoxField`班級。您可以使用指定位置座標和欄位大小`Rectangle`班級。

```csharp
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField. PartialName = "textbox1";
textBoxField.Value = "Text Field";
```

根據需要自訂座標、大小、部分名稱和文字欄位值。

## 步驟 4：自訂文字欄位屬性

在此步驟中，我們將自訂文字欄位屬性，例如邊框、顏色等。

```csharp
Border border = new Border(textBoxField);
border. width = 5;
border. Dash = new Dash(1, 1);
textBoxField. Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```

根據您的喜好自訂文字欄位屬性。

## 步驟 5：將欄位新增至文件中

現在我們已經建立並配置了文字字段，我們可以將其新增到 PDF 文件中。

```csharp
pdfDocument.Form.Add(textBoxField, 1);
```

## 第6步：儲存修改後的PDF

最後，我們可以使用以下指令儲存修改後的PDF`Save`的方法`Document`班級。

```csharp
dataDir = dataDir + "TextBox_out.pdf";
pdfDocument.Save(dataDir);
```

請務必指定已編輯 PDF 的完整路徑和檔案名稱。

### 使用 Aspose.PDF for .NET 的文字方塊範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟文件
Document pdfDocument = new Document(dataDir + "TextField.pdf");
//建立一個字段
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField.PartialName = "textbox1";
textBoxField.Value = "Text Box";
//TextBoxField.Border = 新邊框(
Border border = new Border(textBoxField);
border.Width = 5;
border.Dash = new Dash(1, 1);
textBoxField.Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
//將字段新增至文檔
pdfDocument.Form.Add(textBoxField, 1);
dataDir = dataDir + "TextBox_out.pdf";
//儲存修改後的 PDF
pdfDocument.Save(dataDir);
Console.WriteLine("\nTextbox field added successfully.\nFile saved at " + dataDir);
```

## 結論

在本指南中，我們學習如何使用 .NET 的 Aspose.PDF 庫在 PDF 文件中建立文字欄位。透過執行所描述的步驟，您可以自訂文字欄位的屬性並根據需要將其新增至文件。請隨意進一步探索 Aspose.PDF for .NET 的功能，以擴充處理 PDF 檔案的可能性。

### 常見問題解答

#### Q：我可以使用 Aspose.PDF for .NET 在單一 PDF 文件中建立多個文字欄位嗎？

答：是的，您可以使用 Aspose.PDF for .NET 在單一 PDF 文件中建立多個文字欄位。只需重複為文件中每個所需位置建立和自訂文字欄位的過程即可。

#### Q：如何自訂文字欄位的外觀，例如字體大小和顏色？

答：您可以透過調整文字欄位的屬性來自訂文字欄位的外觀，例如字體大小、字體樣式、顏色、邊框樣式、背景顏色等。在提供的範例原始程式碼中，邊框寬度、邊框虛線圖案和文字顏色都是自訂的。

#### Q：是否可以從已建立的文字欄位中提取使用者輸入的文字？

答：是的，您可以從建立的文字欄位中提取使用者輸入的文字。使用者填寫 PDF 文件中的文字欄位後，您可以使用 Aspose.PDF for .NET 以程式設計方式檢索欄位值。

#### Q：我可以將文字欄位新增至現有 PDF 文件而不建立新文件嗎？

答：是的，您可以將文字欄位新增至現有 PDF 文檔，而無需建立新文檔。 Aspose.PDF for .NET 提供了修改現有 PDF 文件的功能，包括新增文字欄位、核取方塊和其他表單元素。

#### Q：Aspose.PDF for .NET 是否支援其他類型的表單字段，例如複選框和單選按鈕？

答：是的，Aspose.PDF for .NET 支援各種類型的表單字段，包括複選框、單選按鈕、下拉清單等。您可以使用該程式庫來處理 PDF 文件中不同類型的表單元素。