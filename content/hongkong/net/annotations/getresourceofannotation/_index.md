---
title: 取得註釋資源
linktitle: 取得註釋資源
second_title: Aspose.PDF for .NET API 參考
description: 透過此逐步指南，了解如何使用 Aspose.PDF for .NET 擷取註解資源。
type: docs
weight: 90
url: /zh-hant/net/annotations/getresourceofannotation/
---
此範例展示如何使用 Aspose.PDF for .NET 取得註解資源。若要使用 Aspose.PDF for .NET 取得註解資源，請依照下列步驟操作：

## 第一步：設定文檔所在目錄的路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步驟2：開啟包含您要取得其資源的註解的PDF文件。

```csharp
Document doc = new Document(dataDir + "AddAnnotation.pdf");
```

## 步驟 3：建立註釋。

```csharp
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
```

## 步驟 4：將註解新增至文件中的頁面。

```csharp
doc.Pages[1].Annotations.Add(sa);
```

## 步驟5：儲存文件。

```csharp
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## 第六步：開啟修改後的文件。

```csharp
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## 步驟7：取得註解的action。

```csharp
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
```

## 第7步：獲取動作的再現。

```csharp
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
```

## 步驟8：取得媒體剪輯。

```csharp
MediaClip clip = (rendition as MediaRendition).MediaClip;
```

## 步驟9：取得文件規範。

```csharp
FileSpecification data = (clip as MediaClipData).Data;
```

## 步驟10：讀取媒體資料。

```csharp
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
   ms.Write(buffer, 0, read);
}
```

## 第11步：列印再現的名稱和再現操作。

```csharp
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

透過執行下列步驟，您可以使用 Aspose.PDF for .NET 輕鬆取得 PDF 文件中的註解資源。

### 使用 Aspose.PDF for .NET 取得註解資源的範例原始碼：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開啟文件
Document doc = new Document(dataDir + "AddAnnotation.pdf");
//建立註釋
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
doc.Pages[1].Annotations.Add(sa);
//儲存文件
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
//開啟文件
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
//獲取註解的動作
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
//獲得演繹動作的演繹
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
//媒體剪輯
MediaClip clip = (rendition as MediaRendition).MediaClip;
FileSpecification data = (clip as MediaClipData).Data;
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
//媒體資料可在 FileSpecification.Contents 中存取
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
ms.Write(buffer, 0, read);
}
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

## 結論

在本教學中，我們探討如何使用 Aspose.PDF for .NET 從 PDF 文件中取得特定註解的資源。透過遵循逐步指南並使用提供的 C# 原始程式碼，開發人員可以輕鬆存取和管理 PDF 文件中的註釋，包括再現註釋。

### 常見問題解答

#### Q：什麼是 PDF 註釋上下文中的再現？

答：在 PDF 註釋的脈絡中，再現是多媒體內容簡報。它允許在 PDF 文件中嵌入多媒體，例如音訊或視訊。再現註解指定要呈現的媒體及其播放方式。

#### Q：我可以獲得與演繹註釋關聯的媒體檔案的名稱嗎？

答：是的，您可以使用 Aspose.PDF for .NET 取得與再現註解關聯的媒體檔案的名稱。媒體檔案名稱可以透過以下方式存取`FileSpecification`的`MediaClip`目的。

#### Q：Aspose.PDF for .NET 能否從再現註解中擷取媒體檔案？

答：是的，Aspose.PDF for .NET 可以從再現註解中提取媒體資料（包括音訊或視訊內容），並將其儲存為單獨的檔案。

#### Q：如何存取再現註釋的媒體資料？

 A：可透過以下方式存取再現註釋的媒體資料：`FileSpecification.Contents`的財產`MediaClipData`目的。

#### Q：我可以使用 Aspose.PDF for .NET 修改與再現註解相關的媒體嗎？

答：Aspose.PDF for .NET 提供了存取和修改與再現註解關聯的媒體資料的方法。您可以更新或取代再現註解所使用的媒體檔案。