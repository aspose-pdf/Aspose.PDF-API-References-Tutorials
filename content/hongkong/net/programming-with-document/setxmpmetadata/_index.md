---
title: 在 PDF 檔案中設定 XMPMetadata
linktitle: 在 PDF 檔案中設定 XMPMetadata
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 檔案中設定 XMPMetadata。請遵循此逐步指南。
type: docs
weight: 330
url: /zh-hant/net/programming-with-document/setxmpmetadata/
---
在本文中，我們將提供如何使用 Aspose.PDF for .NET 在 PDF 檔案中設定 XMP 元資料的逐步指南。我們將在文章末尾提供完整的範例原始程式碼。

## 第一步：設定文檔目錄路徑

在開始之前，我們需要設定 PDF 文件所在目錄的路徑。我們將該路徑儲存在名為「dataDir」的變數中。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

確保更換`YOUR DOCUMENT DIRECTORY`與 PDF 檔案的實際路徑。

## 第 2 步：開啟 PDF 文件

第一步是開啟要為其設定 XMP 元資料的 PDF 檔案。為此，您需要建立一個新的`Document`物件並傳入 PDF 檔案的路徑。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開啟文件
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");
```

## 步驟 3：設定 XMP 元資料屬性

現在您已開啟 PDF 文件，您可以開始設定 XMP 元資料屬性。您設定的屬性將取決於您的特定需求，但以下是您可能想要設定的一些常見屬性：

- `xmp:CreateDate`：PDF 文件的創建日期。
- `xmp:Nickname`：PDF 檔案的暱稱或別名。
- `xmp:CustomProperty`：具有您指定值的自訂屬性。

要設定這些屬性，您可以使用`Metadata`的財產`Document`目的。這是一個例子：

```csharp
//設定屬性
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";
```

在本教程中，我們將建立日期設為當前日期和時間，將暱稱設為“暱稱”，將自訂屬性設為“自訂值”。您可以將這些值替換為您自己的值。

## 步驟 4：儲存 PDF 文件

設定 XMP 元資料屬性後，您需要儲存 PDF 檔案。為此，您可以使用`Save`的方法`Document`物件並傳入要儲存更新的 PDF 檔案的路徑。

```csharp
dataDir = dataDir + "SetXMPMetadata_out.pdf";
//儲存文件
pdfDocument.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 設定 XMPMetadata 的範例原始碼

以下是使用 Aspose.PDF for .NET 設定 XMPMetadata 的完整範例原始碼：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開啟文件
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");

//設定屬性
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";

dataDir = dataDir + "SetXMPMetadata_out.pdf";
//儲存文件
pdfDocument.Save(dataDir);

Console.WriteLine("\nXMP metadata in a pdf file setup successfully.\nFile saved at " + dataDir);
```

## 結論

Aspose.PDF for .NET 提供了在 PDF 檔案中設定 XMP 元資料的簡單方法，可讓您為文件新增描述性資訊和屬性。上面提供的逐步指南向您展示如何使用 C# 原始碼設定各種 XMP 元資料屬性。此外，您可以自訂 XMP 元資料以滿足您的特定需求和業務要求。透過 Aspose.PDF for .NET，管理 PDF 元資料變得高效，並且可以更好地組織和搜尋 PDF 文件。

### 在 PDF 檔案中設定 XMP 元資料的常見問題解答

#### Q：PDF 檔案中的 XMP 元資料是什麼？

答：XMP（可擴充元資料平台）是一種在各種文件格式（包括 PDF）中嵌入元資料的標準。 PDF 檔案中的 XMP 元資料可讓您為文件新增描述性資訊和屬性，例如建立日期、作者、標題、關鍵字和自訂屬性。它對於更好地組織、搜尋和歸檔 PDF 文件至關重要。

#### Q：除了範例中提到的屬性之外，我還可以設定其他 XMP 元資料屬性嗎？

答：是的，您可以根據您的特定要求設定各種 XMP 元資料屬性。一些常見的屬性包括`dc:title`（文件標題），`dc:creator` （文檔創建者），`dc:description` （文件說明），`pdf:Keywords` （文件關鍵字）等等。 XMP 規範提供了各種標準命名空間和自訂命名空間，用於設定不同類型的元資料。

#### Q：是否可以從現有 PDF 檔案中檢索和讀取 XMP 元資料？

答：是的，Aspose.PDF for .NET 提供了從現有 PDF 檔案讀取和檢索 XMP 元資料的功能。您可以使用`Metadata`的財產`Document`類別來存取 XMP 元資料並檢索特定屬性的值。