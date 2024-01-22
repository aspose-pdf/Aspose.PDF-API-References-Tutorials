---
title: 設定自由文字註釋格式
linktitle: 設定自由文字註釋格式
second_title: Aspose.PDF for .NET API 參考
description: 本文提供了有關如何使用 Aspose.PDF for .NET 建立自由文字註解並指定其內容的逐步指南
type: docs
weight: 140
url: /zh-hant/net/annotations/setfreetextannotationformatting/
---
Aspose.PDF for .NET 是一個功能強大且易於使用的 PDF 文件操作 API，可讓您在 .NET 應用程式中以程式設計方式處理 PDF 檔案。 Aspose.PDF for .NET 提供的功能之一是能夠在 PDF 文件中設定自由文字註解格式。在本文中，我們將引導您逐步完成使用 Aspose.PDF for .NET 設定自由文字註解格式的過程。

## 先決條件

在我們開始之前，請確保您符合以下先決條件：

- Microsoft Visual Studio 2010 或更高版本
- .NET 的 Aspose.PDF
- C#基礎知識



## 步驟 1：建立一個新的 C# 控制台應用程式

首先，在 Microsoft Visual Studio 中建立一個新的 C# 控制台應用程式。若要建立新的控制台應用程序，請從主選單中選擇“檔案”>“新建”>“專案”>“Visual C#”>“控制台應用程式”。

## 步驟 2：新增 Aspose.PDF for .NET 的引用

接下來，在專案中加入 Aspose.PDF for .NET 的參考。為此，請在“解決方案資源管理器”窗格中右鍵單擊您的項目，選擇“新增”>“參考”，然後瀏覽到儲存 Aspose.PDF for .NET DLL 檔案的位置。選擇 DLL 檔案並按一下「確定」將引用新增至您的專案。

## 第三步：設定環境

新增對 Aspose.PDF for .NET 的參考後，您需要設定環境。為此，請建立一個名為「dataDir」的新字串變量，並將其設定為 PDF 文件所在目錄的路徑。將下面程式碼中的「YOUR DOCUMENT DIRECTORY」替換為文件目錄的實際路徑：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步驟 4：開啟 PDF 文檔

設定好環境後，您可以使用以下程式碼開啟PDF文件：

```csharp
//開啟文件
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");
```

將“SetFreeTextAnnotationFormatting.pdf”替換為 PDF 文件的實際名稱。

## 第 5 步：設定預設外觀

若要設定自由文字註解的預設外觀，您需要使用所需的字體、字體大小和顏色實例化 DefaultAppearance 物件。在本教程中，我們將字體設定為“Arial”，字體大小設定為 28，顏色設定為紅色。

```csharp
//實例化 DefaultAppearance 對象
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
```

## 第 6 步：建立自由文字註釋

現在您已經設定了預設外觀，您可以使用以下程式碼建立自由文字註釋：

```csharp
//建立註釋
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
```

上面的程式碼在 PDF 文件的第二頁上建立一個新的自由文字註解。註釋將位於 (200, 400)，寬度為 400，高度為 600。

## 第7步：指定註釋的內容

建立自由文字註解後，您可以使用以下程式碼指定註解的內容：

```csharp
//指定註釋的內容
freetext.Contents = "Free Text
```

### 使用 Aspose.PDF for .NET 設定自由文字註解格式的範例原始碼
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開啟文件
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");

//實例化 DefaultAppearance 對象
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
//建立註釋
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
//指定註釋的內容
freetext.Contents = "Free Text";
//新增註解到頁面註解集合
pdfDocument.Pages[1].Annotations.Add(freetext);
dataDir = dataDir + "SetFreeTextAnnotationFormatting_out.pdf";
//儲存更新後的文檔
pdfDocument.Save(dataDir);            
```

## 結論

在本教學中，我們學習如何使用 Aspose.PDF for .NET 在 PDF 文件中設定自由文字註解格式。該庫提供了一種簡單有效的方式以程式設計方式處理 PDF 文檔，允許開發人員創建和自訂各種類型的註釋，包括自由文字註釋。透過遵循逐步指南並使用提供的 C# 原始程式碼，您可以輕鬆設定環境、開啟 PDF 文件並建立具有自訂格式的自由文字註釋。 Aspose.PDF for .NET 是一個強大且可靠的 API，可簡化 PDF 文件操作任務，使其成為處理 PDF 文件的 .NET 開發人員的寶貴工具。

### 常見問題解答

#### Q：什麼是 PDF 文件中的自由文字註釋？

答：PDF 文件中的自由文本註釋是一種註解類型，可讓您在文件中新增文本，而無需綁定到特定位置或結構。它通常用於在文件中提供評論、註釋或其他附加資訊。

#### Q：我可以使用 Aspose.PDF for .NET 自訂自由文字註解的外觀嗎？

答：是的，您可以自訂自由文字註釋的各種屬性，例如字體、字號、顏色、位置等。

#### 問：如何指定自由文本註釋的內容？

 A：要指定自由文字註釋的內容，可以設定`Contents`的財產`FreeTextAnnotation`反對所需的文本。

#### Q：我可以使用 Aspose.PDF for .NET 將多個自由文字註解新增至 PDF 文件嗎？

答：是的，您可以透過建立多個自由文字註釋實例來在 PDF 文件中建立多個自由文字註釋。`FreeTextAnnotation`物件並將它們新增至文件中的不同頁面或位置。