---
title: 擷取影像
linktitle: 擷取影像
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 輕鬆從 PDF 文件中擷取影像。
type: docs
weight: 70
url: /zh-hant/net/programming-with-security-and-signatures/extracting-image/
---
在許多情況下，從 PDF 文件中提取圖像很有用。使用 Aspose.PDF for .NET，您可以使用以下原始程式碼輕鬆擷取影像：

## 步驟1：導入所需的庫

在開始之前，您需要為 C# 專案匯入必要的程式庫。以下是必要的導入指令：

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## 步驟 2：設定文件資料夾路徑

在此步驟中，您需要指定包含要從中提取影像的 PDF 檔案的資料夾的路徑。代替`"YOUR DOCUMENTS DIRECTORY"`在以下程式碼中使用文件資料夾的實際路徑：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## 步驟 3：從 PDF 文件中擷取影像

現在我們將使用以下程式碼從 PDF 文件中提取圖像：

```csharp
using (Document pdfDocument = new Document(input))
{
foreach(Field field in pdfDocument.Form)
{
SignatureField sf = field as SignatureField;
if (sf != null)
{
string outFile = dataDir + @"output_out.jpg";
using (Stream imageStream = sf.ExtractImage())
{
if (imageStream != null)
{
using (Image image = Bitmap.FromStream(imageStream))
{
image.Save(outFile, ImageFormat.Jpeg);
}
}
}
}
}
}
```

在此範例中，我們循環遍歷 PDF 文件中表單的每個欄位。如果找到簽名字段，我們會提取關聯的圖像並將其保存到 JPEG 檔案中。

### 使用 Aspose.PDF for .NET 擷取影像的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir+ @"ExtractingImage.pdf";
using (Document pdfDocument = new Document(input))
{
	foreach (Field field in pdfDocument.Form)
	{
		SignatureField sf = field as SignatureField;
		if (sf != null)
		{
			string outFile = dataDir+ @"output_out.jpg";
			using (Stream imageStream = sf.ExtractImage())
			{
				if (imageStream != null)
				{
					using (System.Drawing.Image image = Bitmap.FromStream(imageStream))
					{
						image.Save(outFile, System.Drawing.Imaging.ImageFormat.Jpeg);
					}
				}
			}
		}
	}
}
```

## 結論

恭喜！現在您有了使用 Aspose.PDF for .NET 從 PDF 文件中提取影像的逐步指南。您可以將此程式碼整合到您自己的專案中以提取圖像並根據需要使用它們。

請務必查看官方 Aspose.PDF 文檔，以取得更多有關高級影像擷取和 PDF 文檔操作功能的資訊。


### 常見問題解答

#### Q：Aspose.PDF for .NET 適合初學者嗎？

答：雖然熟悉 C# 程式設計會有所幫助，但我們的教學課程旨在適合初學者，引導您完成每個步驟。

#### Q：我可以一次提取多張影像嗎？

答：當然！透過實現循環並調整提供的程式碼，您可以從單一 PDF 文件中提取多個影像。

#### Q：Aspose.PDF for .NET 是影像擷取的唯一解決方案嗎？

答：雖然還有其他可用的工具，但 Aspose.PDF for .NET 以其高效和全面的功能而聞名。

#### Q：我可以將提取的圖像用於商業用途嗎？

答：是的，提取後，圖像即可根據需要使用，包括用於商業項目。

#### Q：在哪裡可以找到更多有關使用 Aspose.PDF 操作 PDF 的資源？

答：請造訪我們的官方文檔，以取得使用 Aspose.PDF for .NET 進行進階 PDF 作業的豐富資源和見解。