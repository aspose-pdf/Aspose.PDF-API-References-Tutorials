---
title: 將工具提示新增至 PDF 檔案中的文本
linktitle: 將工具提示新增至 PDF 檔案中的文本
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 將工具提示新增至 PDF 檔案中的文字。使用資訊豐富的懸停文字輕鬆增強您的 PDF。
type: docs
weight: 90
url: /zh-hant/net/programming-with-text/add-tooltip-to-text/
---
## 介紹

在創建引人入勝的互動式 PDF 時，工具提示的價值無可估量。您知道那些當您將滑鼠懸停在某物上時會提供額外資訊的小彈出框嗎？他們可以提供上下文、描述，甚至一些建議，而不會弄亂您的文件。在本教學中，我們將介紹如何使用 Aspose.PDF for .NET 函式庫為 PDF 檔案中的文字新增工具提示。無論您是經驗豐富的開發人員還是剛剛涉足 PDF 世界，您都來對地方了！那麼就讓我們深入了解吧！

## 先決條件

在我們進入編碼部分之前，讓我們確保您擁有順利進行操作所需的一切。

### 已安裝 Visual Studio
在您的電腦上安裝 Visual Studio 非常重要，因為它將成為 .NET 應用程式的主要開發環境。

### Aspose.PDF for .NET 函式庫
您還需要可以使用 Aspose.PDF 庫。你可以[在這裡下載](https://releases.aspose.com/pdf/net/)。確保將其包含在您的項目參考中。

### C#基礎知識
C# 背景將對我們有很大幫助，因為我們將使用該語言進行編碼。但別擔心—我會引導您完成每一步！

### 可供使用的 PDF 文檔
您可以從空白 PDF 文件開始，就像我們在本範例中所做的那樣，或者如果您願意，也可以使用現有文件。

現在，讓我們繼續編碼部分！

## 導入包 

我們編碼冒險的第一步是導入必要的套件。開啟 Visual Studio 項目，然後在 C# 檔案的頂部新增以下內容`using`指令：

```csharp
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

這些套件可讓您存取建立和操作 PDF 文件所需的所有類別和功能。

## 第 1 步：設定您的文件目錄

首先，我們需要設定保存文檔的路徑。將此視為在檔案系統中找到一個舒適的位置，您的所有創作都將駐留在其中。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
```

確保更換`YOUR DOCUMENT DIRECTORY`與您機器上的實際路徑。

## 第 2 步：建立範例 PDF 文檔

接下來，是時候建立一個包含一些文字的簡單 PDF。這就是我們開始創作過程的地方！

```csharp
//建立帶有文字的範例文檔
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

在此步驟中，我們建立一個文檔，新增兩個文字片段，並將其儲存到我們先前指定的路徑。

## 步驟 3：開啟文件進行處理

現在我們已經建立了文檔，讓我們打開它，以便我們可以處理這些工具提示！

```csharp
//開啟包含文字的文檔
Document document = new Document(outputFile);
```

在這裡，我們只需載入我們剛剛建立的文件。

## 步驟 4：建立文字吸收器來尋找文字片段

我們需要找到要新增工具提示的文字片段。這就像使用放大鏡突出顯示大地圖的特定部分一樣！ 

```csharp
//建立 TextAbsorber 物件以尋找與正規表示式相符的所有短語
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorber);
```

## 步驟5：提取文字片段

接下來，我們提取從上一個步驟中找到的文字片段。

```csharp
//取得擷取的文字片段
TextFragmentCollection textFragments = absorber.TextFragments;
```

該片段使我們能夠保留我們感興趣的文本片段的引用。

## 第 6 步：循環片段並新增工具提示

現在來了有趣的部分！我們將循環遍歷每個文字片段並為每個文字片段添加一個工具提示。想像一下將小禮物（工具提示）包裹在特定項目（文字片段）周圍。

```csharp
//循環遍歷片段
foreach (TextFragment fragment in textFragments)
{
	//在文字片段位置建立不可見按鈕
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	//AlternateName 值將由檢視器應用程式顯示為工具提示
	field.AlternateName = "Tooltip for text.";
	//將按鈕欄位新增至文件中
	document.Form.Add(field);
}
```

在每次迭代中，我們建立一個與文字片段位置相對應的按鈕字段，並向其指派工具提示文字。

## 步驟 7：重複長工具提示

就像我們添加一個簡單的工具提示一樣，我們可以對較長的文字執行相同的操作。讓我們發揮我們的創造力吧！

```csharp
//接下來是很長的工具提示範例
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	//設定很長的文本
	field.AlternateName = "Lorem ipsum dolor sit amet, consectetur adipiscing elit," +
							" sed do eiusmod tempor incididunt ut labore et dolore magna" +
							" aliqua. Ut enim ad minim veniam, quis nostrud exercitation" +
							" ullamco laboris nisi ut aliquip ex ea commodo consequat." +
							" Duis aute irure dolor in reprehenderit in voluptate velit" +
							" esse cillum dolore eu fugiat nulla pariatur. Excepteur sint" +
							" occaecat cupidatat non proident, sunt in culpa qui officia" +
							" deserunt mollit anim id est laborum.";
	document.Form.Add(field);
}
```

在這裡，我們正在做與以前相同的工作，但使用了更擴展的工具提示。

## 第 8 步：儲存您的文件

最後一步是使用所有這些閃亮的新工具提示儲存文件。 

```csharp
//儲存文件
document.Save(outputFile);
```

就這樣，你就完成了！您已向 PDF 添加了工具提示，使其更加用戶友好和互動。

## 結論

這是一個簡單易懂的指南，介紹如何使用 Aspose.PDF for .NET 將工具提示新增至 PDF 檔案中的文字。這項技術可以顯著增強使用者體驗，讓您的文件內容更豐富，而不會一次用太多文字讓讀者感到不知所措。 

只需將滑鼠懸停在單字或短語上，讀者即可獲得相關信息，從而增加價值而不混亂。所以，捲起袖子來嘗試吧！在不知不覺中，您可能已經創建了各種引人入勝的引人注目的文檔。

## 常見問題解答

### 什麼是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一個函式庫，可讓開發人員在.NET 應用程式中建立、操作和轉換 PDF 文件。

### 我可以免費使用 Aspose.PDF 嗎？
是的，Aspose 提供免費試用供您探索其功能！你可以找到它[這裡](https://releases.aspose.com/).

### Aspose.PDF 有可用的授權選項嗎？
是的，您可以購買許可證或取得臨時許可證。查看選項[這裡](https://purchase.aspose.com/).

### 我可以使用 Aspose.PDF 添加工具提示以外的互動元素嗎？
絕對地！ Aspose.PDF 允許新增各種互動元素，如超連結、按鈕和表單。

### 在哪裡可以找到有關 Aspose.PDF 的更多文件？
你可以查看文檔[這裡](https://reference.aspose.com/pdf/net/)以獲得更深入的指導。