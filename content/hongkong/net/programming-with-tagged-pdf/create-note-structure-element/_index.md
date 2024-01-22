---
title: 建立註解結構元素
linktitle: 建立註解結構元素
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 在 PDF 文件中建立結構化註解項目的逐步指南。
type: docs
weight: 30
url: /zh-hant/net/programming-with-tagged-pdf/create-note-structure-element/
---
在本教學中，我們將為您提供如何使用 Aspose.PDF for .NET 在 PDF 文件中建立註解結構元素的逐步指南。 Aspose.PDF 是一個功能強大的程式庫，可讓您以程式設計方式建立、操作和轉換 PDF 文件。使用Aspose.PDF的標記內容結構功能，您可以為PDF文件新增結構化註解。

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
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## 步驟 3：建立 PDF 文件並註解結構化元素

使用以下程式碼建立 PDF 文件並新增註解結構化元素：

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample Grade Items");
taggedContent.SetLanguage("fr-FR");

ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);

NoteElement note1 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note1);
note1.SetText("Note with automatically generated ID. ");

NoteElement note2 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note2);
note2.SetText("Note with ID = 'note_002'.");
note2.SetId("note_002");

NoteElement note3 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note3);
note3.SetText("Note with ID = 'note_003'.");
note3.SetId("note_003");
```

此程式碼建立一個空 PDF 文件並將結構化註解元素加入到段落中。每個註解都是使用 Aspose.PDF 提供的方法建立的。

## 步驟 4：儲存 PDF 文檔

使用以下程式碼儲存PDF文件：

```csharp
document. Save(outFile);
```

此程式碼將帶有註釋結構化元素的 PDF 文件儲存到指定文件中。

### 使用 Aspose.PDF for .NET 建立註解結構元素的範例原始碼 

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
//建立 PDF 文件
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
//新增段落元素
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
//新增註釋元素
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
//新增註釋元素
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
//新增註釋元素
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
//必須拋出異常 - Aspose.Pdf.Tagged.TaggedException：ID='note_002' 的結構元素已存在
//note3.SetId("note_002");
//如果 ClearId() 用於註解結構元素，則產生的文件不符合 PDF/UA
//note3.ClearId();
//儲存標記的 PDF 文檔
document.Save(outFile);
//檢查 PDF/UA 合規性
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 結論

在本教學中，您學習如何使用 Aspose.PDF for .NET 在 PDF 文件中建立註解結構元素。結構化註解元素可讓您為 PDF 文件添加附加的結構化資訊。

### 常見問題解答

#### Q：使用 Aspose.PDF for .NET 在 PDF 文件中建立註解結構元素的目的是什麼？

答：使用 Aspose.PDF for .NET 在 PDF 文件中建立註解結構元素可讓您在文件內容中新增結構化註解。這些註釋可以提供額外的上下文、解釋或對內容特定部分的引用。

#### Q：Aspose.PDF 庫如何協助在 PDF 文件中建立註解結構元素？

答：Aspose.PDF for .NET 是一個功能強大的函式庫，提供以程式設計方式建立、操作和轉換 PDF 文件的功能。在本教學中，庫的標記內容結構功能用於在 PDF 文件內容中建立結構化註解元素。

#### Q：使用 Aspose.PDF for .NET 在 PDF 文件中建立註解結構元素的先決條件是什麼？

答：開始之前，請確保您已安裝了具有 .NET 框架的 Visual Studio，並在專案中引用了適用於 .NET 的 Aspose.PDF 程式庫。

#### Q：所提供的 C# 程式碼如何在 PDF 文件的內容中建立註解結構元素？

答：程式碼示範如何建立 PDF 文件、定義註解結構化元素並將它們新增到段落中。每個註解都是使用 Aspose.PDF 提供的方法建立的，讓您可以將結構化註解合併到內容中。

#### Q：我可以自訂我創建的筆記結構元素的內容和屬性嗎？

答：是的，您可以使用Aspose.PDF庫提供的方法和屬性來自訂註解結構元素的內容和屬性。該程式碼展示瞭如何設定註釋元素的文字和 ID，但您可以根據需要進一步自訂它們。

#### Q：筆記結構元素與文件內容之間的層次關係是如何建立的？

答：層次關係是透過加入註釋結構元素作為其他結構元素（例如段落）的子元素來建立的。在程式碼中，使用以下方法將註解元素附加到段落元素`AppendChild`方法。

#### Q：我可以為註解結構元素分配唯一的 ID 嗎？

答：是的，您可以使用以下命令為註解結構元素指派唯一的 ID：`SetId`方法。程式碼示範如何將註解元素的 ID 設定為唯一值。

#### Q：如果我嘗試將重複的 ID 指派給註解結構元素，會發生什麼事？

答：嘗試將重複的 ID 指派給註解結構元素將導致例外狀況。本教程中提供的程式碼包含說明此場景的註解。

#### Q：建立筆記結構元素時如何確保 PDF/UA 合規性？

答：本教學中提供的程式碼示範如何使用以下方法驗證 PDF/UA 合規性：`Validate`方法。透過根據 PDF/UA 標準驗證文檔，您可以確保新增的註釋結構元素符合輔助功能指南。

#### Q：我可以使用此方法為現有 PDF 文件添加註釋結構元素嗎？

答：是的，您可以修改提供的方法，將註解結構元素新增至現有 PDF 文件中。您可以使用 Aspose.PDF 載入現有文檔，然後按照類似的步驟附加註解元素，而不是建立新文檔。
