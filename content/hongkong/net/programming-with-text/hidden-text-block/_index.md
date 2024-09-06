---
title: PDF 檔案中的隱藏文字區塊
linktitle: PDF 檔案中的隱藏文字區塊
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 檔案中建立隱藏文字區塊。
type: docs
weight: 230
url: /zh-hant/net/programming-with-text/hidden-text-block/
---
在本教學中，我們將說明如何使用 .NET 的 Aspose.PDF 庫在 PDF 檔案中建立隱藏文字區塊。隱藏文字區塊是浮動文本，當滑鼠遊標懸停在特定區域上時，該文字區塊變得可見。我們將使用提供的 C# 原始程式碼逐步完成建立隱藏文字區塊的過程。

## 要求

在開始之前，請確保您具備以下條件：

- 安裝了 Aspose.PDF for .NET 函式庫。
- 對 C# 程式設計有基本了解。

## 第 1 步：設定文檔目錄

首先，您需要設定要儲存生成的 PDF 檔案的目錄路徑。代替`"YOUR DOCUMENT DIRECTORY"`在`dataDir`變數包含您所需目錄的路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：建立範例文檔

在此步驟中，我們建立一個範例 PDF 文件並向其中新增一個文字片段。文字片段將作為顯示隱藏文字區塊的觸發器。

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## 第 3 步：開啟文檔

現在，我們使用以下命令打開先前建立的文檔`Document`班級。

```csharp
Document document = new Document(outputFile);
```

## 第四步：找到文字片段

我們使用一個`TextFragmentAbsorber`物件查找將觸發隱藏文字區塊顯示的文字片段。在本例中，我們正在搜尋確切的文字「將滑鼠遊標移至此處以顯示浮動文字」。

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## 第 5 步：建立隱藏文字字段

我們創建一個`TextBoxField`物件來表示隱藏的文字欄位。此欄位將包含當滑鼠遊標懸停在觸發器文字上時變得可見的文字。

```csharp
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
floatingField.Value = "This is the \"floating text field\".";
floatingField. ReadOnly = true;
floatingField.Flags |= AnnotationFlags.Hidden;
floatingField.PartialName = "FloatingField_1";
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField. Multiline = true;
```

## 步驟 6：將隱藏文字欄位新增至文件中

我們將隱藏文字欄位新增到文件的表單集合中。

```csharp
document.Form.Add(floatingField);
```

## 第7步：建立隱形按鈕

我們建立一個不可見的按鈕字段，該字段將位於觸發器文字片段的頂部。此按鈕欄位將具有與滑鼠進入和退出事件相關的操作。

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## 第 8 步：儲存文檔

最後，我們使用隱藏文字區塊來保存修改後的文件。

```csharp
document. Save(outputFile);
```

### 使用 Aspose.PDF for .NET 的隱藏文字區塊的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
//建立帶有文字的範例文檔
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
//開啟包含文字的文檔
Document document = new Document(outputFile);
//建立 TextAbsorber 物件以尋找與正規表示式相符的所有短語
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
//接受文件頁面的吸收器
document.Pages.Accept(absorber);
//取得第一個擷取的文字片段
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
//為頁面指定矩形中的浮動文字建立隱藏文字字段
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
//設定要顯示為欄位值的文本
floatingField.Value = "This is the \"floating text field\".";
//我們建議在這種情況下將欄位設為“唯讀”
floatingField.ReadOnly = true;
//設定「隱藏」標誌以使欄位在開啟文件時不可見
floatingField.Flags |= AnnotationFlags.Hidden;
//設定唯一的欄位名稱不是必需的，但允許
floatingField.PartialName = "FloatingField_1";
//設定欄位外觀的特徵不是必需的，但可以使其更好
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
//將文字欄位新增至文件中
document.Form.Add(floatingField);
//在文字片段位置建立不可見按鈕
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
//為指定欄位（註解）和不可見標誌建立新的隱藏操作。
// （如果您在上面指定了浮動字段，您也可以透過名稱引用浮動字段。）
//在不可見的按鈕欄位中新增滑鼠進入/退出的操作
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
//將按鈕欄位新增至文件中
document.Form.Add(buttonField);
//儲存文件
document.Save(outputFile);
```

## 結論

在本教學中，您學習如何使用 Aspose.PDF for .NET 函式庫建立隱藏文字區塊。透過遵循逐步指南，您可以產生帶有隱藏文字欄位的 PDF 文檔，當滑鼠遊標懸停在特定區域上時，隱藏文字欄位將變為可見。您可以根據您的要求自訂隱藏文字區塊的外觀和行為。

### 常見問題解答

#### Q：「PDF 檔案中的隱藏文字區塊」教學的目的是什麼？

答：「PDF 檔案中的隱藏文字區塊」教學課程介紹如何使用 .NET 的 Aspose.PDF 庫在 PDF 檔案中建立隱藏文字區塊。隱藏文字區塊是浮動文本，當滑鼠遊標懸停在特定區域上時，該文字區塊變得可見。本教程提供了使用 C# 原始程式碼的逐步指南。

#### Q：為什麼我要在 PDF 檔案中建立隱藏文字區塊？

答：建立隱藏文字區塊對於互動式 PDF 文件非常有用，您可以在其中提供僅當使用者將滑鼠遊標懸停在指定區域上時才可見的附加資訊或上下文。

#### Q：如何設定文檔目錄？

A：設定文檔目錄：

1. 代替`"YOUR DOCUMENT DIRECTORY"`在`dataDir`變數包含要儲存產生的 PDF 檔案的目錄路徑。

#### Q：如何建立範例文件並在其中新增文字片段？

答：在本教程中，您使用`Document`類別來建立範例 PDF 文件並添加文字片段。此文字片段用作顯示隱藏文字區塊的觸發器。

#### Q：如何找到觸發隱藏文字區塊的文字片段？

答：本教學示範如何使用`TextFragmentAbsorber`物件來尋找觸發隱藏文字區塊顯示的文字片段。它在 PDF 文件中搜尋特定的文字字串。

#### Q：如何建立和自訂隱藏文字欄位？

答：你創建一個`TextBoxField`物件來表示隱藏的文字欄位。本教學提供了用於設定各種屬性的程式碼，例如隱藏文字欄位的位置、值、外觀和行為。

#### Q：如何建立與隱藏文字區塊關聯的不可見按鈕？

答：使用以下命令建立不可見的按鈕字段`ButtonField`班級。此按鈕欄位位於觸發文字片段的頂部，並具有與滑鼠進入和退出事件關聯的操作。這些操作控制隱藏文字區塊的可見性。

#### Q：我可以自訂隱藏文字區塊和觸發區域的外觀嗎？

答：是的，您可以自訂隱藏文字欄位和隱形按鈕的各種屬性，包括字體、顏色、大小和位置。

#### Q：如何儲存修改後的帶有隱藏文字區塊的文件？

 A：本教學課程示範如何使用儲存修改後的文檔`Save`的方法`Document`班級。