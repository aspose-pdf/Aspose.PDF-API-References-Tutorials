---
title: 在 PDF 檔案中新增日期時間戳
linktitle: 在 PDF 檔案中新增日期時間戳
second_title: Aspose.PDF for .NET API 參考
description: 透過此逐步指南，了解如何使用 Aspose.PDF for .NET 將日期和時間戳記新增至 PDF 檔案。非常適合增強文件的真實性。
type: docs
weight: 10
url: /zh-hant/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
## 介紹

在管理文件（尤其是 PDF）時，新增日期和時間戳記可能會改變遊戲規則。無論您正在處理法律文件、專案報告或發票，時間戳不僅可以增加真實性，還可以提供文件建立或修改時間的清晰記錄。在本指南中，我們將引導您完成使用 .NET 的 Aspose.PDF 庫為 PDF 檔案新增日期和時間戳記的過程。 

本文旨在簡單易懂，因此即使您是程式設計或 Aspose.PDF 庫的新手，您也能夠充滿信心地實現此功能。讓我們深入了解吧！

## 先決條件

在我們開始之前，您需要滿足一些先決條件：

1. Visual Studio：確保您的電腦上安裝了 Visual Studio。您將在此處編寫和執行程式碼。
2. Aspose.PDF for .NET：您需要下載並安裝Aspose.PDF庫。你可以找到最新版本[這裡](https://releases.aspose.com/pdf/net/).
3. C# 基礎知識：熟悉 C# 程式設計將幫助您更好地理解範例，但如果您剛開始，您不必擔心；我們將逐步解釋一切。
4.  PDF 檔案：準備好範例 PDF 檔案。對於我們的範例，我們將使用一個名為`AddTextStamp.pdf`.

滿足這些先決條件後，您就可以開始在 PDF 檔案中新增日期和時間戳記了！

## 導入包

首先，您需要在 C# 專案中匯入必要的命名空間。操作方法如下：

### 建立一個新項目

1. 開啟 Visual Studio：啟動 Visual Studio 應用程式。
2. 建立新項目：從開始畫面中選擇「建立新項目」。
3. 選擇控制台應用程式：從專案範本清單中選擇“控制台應用程式（.NET Framework）”。
4. 為您的專案命名：為您的專案命名，例如，`PDFDateTimeStamp`.

### 新增 Aspose.PDF 參考

1. 右鍵點選引用：在解決方案資源管理器中，右鍵點選專案的「引用」資料夾。
2. 選擇“新增引用”：從上下文選單中選擇“新增引用”。
3. 瀏覽 Aspose.PDF：導航到下載 Aspose.PDF 的位置並選擇它。按一下「確定」將其新增至您的專案中。

### 導入所需的命名空間

在你的頂部`Program.cs`文件中，需要匯入以下命名空間：

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Annotations;
```

現在我們已經完成了所有設置，讓我們將向 PDF 文件添加日期和時間戳記的過程分解為清晰、可管理的步驟。

## 步驟1：設定文檔目錄

首先，您需要指定 PDF 檔案所在的目錄。這很重要，因為程式碼將在此目錄中找到 PDF。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY"; //替換成你的實際路徑
```

確保更換`YOUR DOCUMENT DIRECTORY`與 PDF 檔案的實際路徑。

## 第 2 步：開啟 PDF 文檔

接下來，您將開啟要在其中新增時間戳記的 PDF 文件。 

```csharp
//開啟文件
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

這行程式碼初始化了`Document`類別並將您的 PDF 文件加載到`pdfDocument`目的。

## 第 3 步：建立日期時間戳

現在是時候產生日期和時間戳記了。您將其格式化為以特定方式顯示。 

```csharp
string annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");
```

這裡，`DateTime.Now`取得當前日期和時間，以及`ToString`將其格式化為您想要的格式。

## 第 4 步：建立文字圖章

準備好日期和時間字串後，現在可以建立將新增到 PDF 中的文字圖章。

```csharp
//建立文字印章
TextStamp textStamp = new TextStamp(annotationText);
```

該行會建立一個新實例`TextStamp`使用格式化的日期和時間字串。

## 第 5 步：設定圖章屬性

您可以自訂圖章的外觀和位置。設定其屬性的方法如下：

```csharp
//設定圖章的屬性
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

在此步驟中，我們設定邊距並將圖章與 PDF 頁面的右下角對齊。

## 第 6 步：將圖章新增至 PDF

現在是時候將文字圖章新增到您的 PDF 文件中了。 

```csharp
//在集郵上新增郵票
pdfDocument.Pages[1].AddStamp(textStamp);
```

此行將圖章新增至 PDF 的第一頁。如果您想將其放置在不同的頁面上，您可以更改頁碼。

## 第 7 步：建立自由文字註釋（可選）

如果你想為圖章添加註釋，你可以創建一個`FreeTextAnnotation`如下：

```csharp
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;
```

此可選步驟建立一個自由文字註釋，可以提供有關圖章的附加上下文或資訊。

## 第8步：配置註解邊框

如果您想自訂註解的邊框，也可以這樣做：

```csharp
Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

此程式碼片段將邊框寬度設為 0，使其不可見，並將註解新增至 PDF。

## 第9步：儲存PDF文檔

最後，您需要儲存修改後的PDF文件。 

```csharp
dataDir = dataDir + "AddDateTimeStamp_out.pdf"; //指定輸出檔名
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);
```

此行將新增了時間戳記的 PDF 儲存到新文件中。您可以檢查指定的目錄以查看輸出。

## 結論

恭喜！您已使用 Aspose.PDF for .NET 成功為 PDF 檔案新增日期和時間戳記。這個簡單而有效的功能可以增強您的文檔，使它們更加專業，並提供創建或修改時間的清晰記錄。 

## 常見問題解答

### 我可以自訂時間戳中的日期格式嗎？
是的，您可以修改`ToString`方法將日期格式變更為您的偏好。

### Aspose.PDF 可以免費使用嗎？
 Aspose.PDF 提供免費試用版，但要獲得完整功能，您需要購買授權。您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).

### 我可以在 PDF 中新增多個時間戳記嗎？
絕對地！您可以建立多個`TextStamp`實例並將它們新增至 PDF 中的不同頁面或位置。

### 如果我沒有 Visual Studio 怎麼辦？
您可以使用任何 C# IDE 或文字編輯器，但為了執行和偵錯項目，建議使用 Visual Studio。

### 在哪裡可以找到更多使用 Aspose.PDF 的範例？
您可以在以下位置探索更多範例和教程[Aspose.PDF 文檔](https://reference.aspose.com/pdf/net/).