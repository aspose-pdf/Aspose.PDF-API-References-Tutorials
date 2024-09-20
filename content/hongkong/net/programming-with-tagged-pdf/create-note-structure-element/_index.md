---
title: 建立註解結構元素
linktitle: 建立註解結構元素
second_title: Aspose.PDF for .NET API 參考
description: 透過這個詳細的逐步教學，學習如何使用 Aspose.PDF for .NET 在 PDF 中建立註解結構元素。
type: docs
weight: 30
url: /zh-hant/net/programming-with-tagged-pdf/create-note-structure-element/
---
## 介紹

創建結構化文件在當今的數位世界中至關重要，尤其是在處理 PDF 時。當涉及文件可訪問性時，.NET 的 Aspose.PDF 庫是一個強大的工具，可以幫助開發人員無縫管理 PDF 內容。在本教學中，我們將深入探討如何使用 Aspose.PDF for .NET 在 PDF 中建立註解結構元素。無論您是經驗豐富的開發人員還是新手，本指南都將以對話式、易於理解的方式引導您完成每個步驟。那麼，就讓我們開始吧！

## 先決條件

在我們開始編碼和建立註釋結構元素之前，讓我們確保您已準備好所需的一切：

1. .NET 環境：您應該設定一個 .NET 開發環境，例如 Visual Studio。
2.  Aspose.PDF 庫：您需要下載並安裝 Aspose.PDF 庫。你可以從[這裡](https://releases.aspose.com/pdf/net/).
3. 基本 C# 知識：要充分利用本教學課程，必須熟悉 C# 程式設計。
4. 存取 .NET Framework：確保您的專案面向 .NET Framework 的相容版本。
5. 文件目錄：設定一個目錄來儲存 PDF 和日誌檔案。 

一切都準備好了嗎？偉大的！讓我們進入代碼吧！

## 導入包

第一步是導入必要的包。這可以在您的開發環境中完成。這是執行此操作的簡單方法：

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

這些命名空間提供對建立和操作 PDF 文件所需的類別和方法的存取。

## 第 1 步：設定文檔

首先，您需要建立一個新的文檔實例。這是您想要產生的任何 PDF 的起點。操作方法如下：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";

//建立 PDF 文件
Document document = new Document();
```
這段程式碼初始化一個新的`Document`物件並設定輸出 PDF 和日誌檔案的檔案路徑。確保更換`"YOUR DOCUMENT DIRECTORY"`與您的實際目錄路徑。

## 步驟 2：設定標記內容屬性

接下來，讓我們深入了解為 PDF 設定標記內容。這包括定義標題和語言屬性。

```csharp
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
```
在這裡，我們正在訪問`TaggedContent`文件並設定其標題和語言。這對於可訪問性標準至關重要，並使您的文件更加專業。

## 第 3 步：建立段落元素

現在，我們將向標記的內容添加一個段落元素。這將作為您的筆記的容器。

```csharp
//新增段落元素
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
```
透過創建一個`ParagraphElement`，我們提供了一個將添加註釋元素的基礎。這類似於在建造牆壁之前先打好房子的地基。

## 第 4 步：新增註解元素

現在有趣的部分是：添加註釋元素！您可以建立多個筆記 - 讓我們分三步驟完成！

### 步驟 4.1：新增第一個註釋

```csharp
//新增註釋元素
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID.");
```
此程式碼使用自動產生的 ID 建立第一個註解。請注意，在我們的上一段中添加內容是多麼容易。

### 步驟 4.2：新增第二個註釋

```csharp
//新增註釋元素
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
```
對於第二個註釋，我們明確地設定了 ID`note_002`。請務必注意 ID，因為它們提供了一種稍後引用特定註釋的方法。

### 步驟 4.3：新增第三個註釋

```csharp
//新增註釋元素
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
//必須拋出異常 - Aspose.Pdf.Tagged.TaggedException：ID='note_002' 的結構元素已存在
```
第三個音符與第二個音符非常相似，但使用另一個唯一的 ID。當心;嘗試建立另一個具有相同 ID 的筆記`note_002`會拋出異常。 

## 第 5 步：儲存文檔

新增註解後，就可以儲存文件了！

```csharp
//儲存標記的 PDF 文檔
document.Save(outFile);
```
這一簡單的行將您所有的辛苦工作保存到指定的 PDF 文件中。 

## 第 6 步：驗證 PDF/UA 合規性

為了確保您的文件符合輔助功能標準，您可以對其進行驗證。

```csharp
//檢查 PDF/UA 合規性
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```
此程式碼段根據 PDF/UA（通用輔助功能）標準檢查您的 PDF。您將收到一個指示合規性的布林值！

## 結論

現在你就擁有了！現在您已成功在 PDF 文件中建立註釋結構元素，從而實現更好的可訪問性和結構 - 感謝 Aspose.PDF for .NET！透過執行這些步驟，您可以更有效地管理 PDF，使其更加用戶友好。 

## 常見問題解答

### PDF 中的註解結構元素是什麼？
註釋元素是添加到 PDF 特定部分的註釋或註釋，可增強清晰度和理解性。

### Aspose.PDF for .NET 是免費的嗎？
雖然 Aspose.PDF 提供免費試用，但它是一個商業產品；價格會根據您的使用情況和所需功能而有所不同。

### 我可以使用 Aspose.PDF 建立其他類型的元素嗎？
是的！ Aspose.PDF 支援圖像、表單和超連結等多種元素來豐富您的文件。

### 什麼是 PDF/UA 合規性？
PDF/UA 合規性確保 PDF 可供殘障人士訪問，符合全球標準。

### 我可以在哪裡獲得 Aspose.PDF 支援？
如需支持，請訪問[Aspose論壇](https://forum.aspose.com/c/pdf/10)您可以在這裡提出問題並分享您的經驗。