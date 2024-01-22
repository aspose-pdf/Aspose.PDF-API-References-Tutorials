---
title: 在 PDF 檔案中設定標註屬性
linktitle: 在 PDF 檔案中設定標註屬性
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 檔案中設定標註屬性。使用標註線、文字顏色和結束樣式自訂註解。
type: docs
weight: 130
url: /zh-hant/net/annotations/setcalloutproperty/
---
 Aspose.PDF for .NET 是一個功能強大的程式庫，用於在 C# 中建立、操作和轉換 PDF 文件。該程式庫提供的功能之一是能夠為 PDF 文件中的自由文字註釋設定標註屬性。這可以使用以下方法完成`FreeTextAnnotation`類，它允許您使用標註創建註釋。

在本教學中，我們將引導您完成在 C# 中使用 Aspose.PDF for .NET 設定自由文字註解標註屬性的過程。請依照以下步驟開始。

## 安裝 Aspose.PDF for .NET

如果您還沒有這樣做，您將需要[下載](https://releases.aspose.com/pdf/net/)並從 Aspose 版本或透過 NuGet 套件管理器安裝 Aspose.PDF for .NET。

## 第 1 步：建立一個新的 PDF 文檔

使用以下命令建立新的 PDF 文檔`Document`Aspose.PDF for .NET 提供的類別。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## 步驟 2：為文件新增頁面

使用以下命令為文件新增頁面`Pages`的集合`Document`班級。

```csharp
Page page = doc.Pages.Add();
```

## 第 3 步：設定預設外觀

透過建立新的文字註釋來設定自由文字註釋的預設外觀`DefaultAppearance`對象並設定其屬性，例如`TextColor`和`FontSize`.

```csharp
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```

## 步驟 4：建立帶有標註的自由文字註釋

使用標註建立新的自由文字註釋`FreeTextAnnotation`班級。設定`Intent`財產給`FreeTextIntent.FreeTextCallout`指定這是一個標註註釋。設定`EndingStyle`財產給`LineEnding.OpenArrow`指定標註末尾的箭頭樣式。設定`Callout`屬性到數組`Point`表示頁面上應繪製標註線的點的物件。

```csharp
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
    new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
```

## 步驟5：為頁面新增自由文字註釋

使用以下命令將自由文字註釋新增至頁面`Annotations`的集合`Page`班級。

```csharp
page.Annotations.Add(fta);
```

## 第 6 步：為註釋新增文本

透過設定將文字新增至註釋`RichText`屬性為格式化 XML 字串。在本教程中，我們將文字顏色設為紅色，並將字體大小設為 9。

```csharp
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" 樣式=\"顏色:#FF
```

## 步驟7：儲存文檔

現在使用以下程式碼儲存文件：

```csharp
doc.Save(dataDir + "SetCalloutProperty.pdf")
```

### 使用 Aspose.PDF for .NET 設定標註屬性的範例原始碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
	new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
page.Annotations.Add(fta);
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"> <span style=\"font-size:9.0pt;font-family:Helvetica\">這是一個例子</span></p></body>";
doc.Save(dataDir + "SetCalloutProperty.pdf");
```

## 結論

在本教學中，我們探討如何使用 Aspose.PDF for .NET 在 PDF 文件中設定自由文字註解的標註屬性。標註註釋可用於提供與文件中特定區域相關的附加資訊或解釋。 Aspose.PDF for .NET 提供了廣泛的處理 PDF 文件的特性和功能，包括建立和自訂註釋，例如標註。透過遵循逐步指南並使用提供的 C# 原始程式碼，開發人員可以輕鬆在 PDF 文件中實現標註註釋，從而增強文件的可用性和清晰度。 Aspose.PDF for .NET 是一個多功能且可靠的程式庫，用於 .NET 應用程式中的 PDF 操作，提供強大的工具來高效處理各種 PDF 相關任務。

### 在 PDF 檔案中設定標註屬性的常見問題解答

#### Q：什麼是 PDF 文件中的標註註釋？

答：PDF 文件中的標註註解是一種註解類型，可讓您建立具有指向文件中特定區域的引線的文字方塊。它通常用於提供與文件中特定部分或元素相關的附加資訊或註釋。

#### Q：我可以使用 Aspose.PDF for .NET 自訂標註註解的外觀嗎？

答：是的，您可以自訂標註註解的各種屬性，例如顏色、字體大小、文字對齊方式、線條樣式、箭頭樣式等。

#### Q：如何為標註註釋新增文字？

 A：若要在標註註釋中新增文本，您可以設定`RichText`的財產`FreeTextAnnotation`目的。這`RichText`屬性採用格式化 XML 字串，表示要在標註註解中顯示的文字。

#### Q：我可以使用 Aspose.PDF for .NET 將多個標註註解新增至 PDF 文件嗎？

答：是的，您可以透過建立多個標註實例來在 PDF 文件中建立多個標註註釋。`FreeTextAnnotation`物件並將它們新增至文件中的不同頁面或位置。