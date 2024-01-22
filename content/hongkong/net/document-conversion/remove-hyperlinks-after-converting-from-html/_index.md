---
title: 從 Html 轉換後刪除超鏈接
linktitle: 從 Html 轉換後刪除超鏈接
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 將 HTML 轉換為 PDF 後刪除超連結的逐步指南。
type: docs
weight: 250
url: /zh-hant/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
在本教學中，我們將引導您完成使用 Aspose.PDF for .NET 從 HTML 檔案產生的 PDF 檔案中刪除超連結的過程。超連結是可以重定向到其他頁面或網站的可點擊連結。透過執行以下步驟，您將能夠從生成的 PDF 檔案中刪除超連結。

## 先決條件
在開始之前，請確保滿足以下先決條件：

- C# 程式語言的基礎知識。
- 您的系統上安裝了適用於 .NET 的 Aspose.PDF 庫。
- 開發環境，例如 Visual Studio。

## 步驟 1： 載入 HTML 檔案並刪除超鏈接
在此步驟中，我們將載入 HTML 檔案並從產生的 PDF 文件中刪除超連結。使用以下程式碼：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//使用 HTML 載入選項載入 HTML 文件
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());

//瀏覽文件第一頁的註釋
foreach(Annotation a in doc.Pages[1].Annotations)
{
     //檢查註釋是否是鏈接
     if (a.AnnotationType == AnnotationType.Link)
     {
         LinkAnnotation the = (LinkAnnotation)a;
        
         //檢查操作是否屬於 GoToURIAction 類型
         if (the.Action is GoToURIAction)
         {
             GoToURIAction gta = (GoToURIAction)the.Action;
             gta.URI = "";
            
             //使用文字片段吸收器尋找相符的文字片段
             TextFragmentAbsorber tfa = new TextFragmentAbsorber();
             tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
             doc.Pages[a.PageIndex].Accept(tfa);
            
             //循環遍歷匹配的文字片段並從超連結中刪除屬性
             foreach(TextFragment tf in tfa.TextFragments)
             {
                 tf.TextState.Underline = false;
                 tf.TextState.ForegroundColor = Color.Black;
             }
         }
        
         //從頁面中刪除註釋
         doc.Pages[a.PageIndex].Annotations.Delete(a);
     }
}
```

一定要更換`"YOUR DOCUMENTS DIRECTORY"`與 HTML 檔案所在的實際目錄。

## 步驟 2： 儲存生成的 PDF 文件
最後，我們將保存生成的不含超連結的 PDF 檔案。使用以下程式碼：

```csharp
//儲存生成的 PDF 文件
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

上面的程式碼使用文件名保存生成的 PDF 文件`"RemoveHyperlinksFromText_out.pdf"`.

### 使用 Aspose.PDF for .NET 從 Html 轉換後刪除超連結的範例原始碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
doc.Save(new MemoryStream());
foreach (Annotation a in doc.Pages[1].Annotations)
{
	if (a.AnnotationType == AnnotationType.Link)
	{
		LinkAnnotation la = (LinkAnnotation)a;
		if (la.Action is GoToURIAction)
		{
			GoToURIAction gta = (GoToURIAction)la.Action;
			gta.URI = "";
			TextFragmentAbsorber tfa = new TextFragmentAbsorber();
			tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
			doc.Pages[a.PageIndex].Accept(tfa);
			foreach (TextFragment tf in tfa.TextFragments)
			{
				tf.TextState.Underline = false;
				tf.TextState.ForegroundColor = Color.Black;
			}
		}
		doc.Pages[a.PageIndex].Annotations.Delete(a);
	}
}
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

## 結論
在本教學中，我們介紹了使用 Aspose.PDF for .NET 從 HTML 檔案產生的 PDF 檔案中刪除超連結的逐步過程。按照上述說明操作，您將能夠成功從生成的 PDF 文件中刪除超連結。

### 常見問題解答

#### Q：什麼是 Aspose.PDF for .NET？

答：Aspose.PDF for .NET 是一個功能強大的程式庫，可讓開發人員在 C# 應用程式中處理 PDF 文件。它提供了廣泛的功能，包括將 HTML 文件轉換為 PDF 和操作 PDF 內容的能力。

#### Q：為什麼我要從 PDF 檔案中刪除超連結？

答：從 PDF 文件中刪除超連結的原因有很多。例如，您可能希望消除用於列印或存檔目的的外部鏈接，或確保 PDF 內容無法透過超鏈接進行導航。

#### Q：如何使用 Aspose.PDF for .NET 載入 HTML 檔案並刪除超連結？

答：要載入 HTML 檔案並刪除超鏈接，您可以使用 Aspose.PDF for .NET`HtmlLoadOptions`班級。迭代 PDF 頁面的註釋以尋找連結註釋並修改其屬性。

#### Q：我可以自訂生成的 PDF 的輸出檔名嗎？

答：是的，您可以透過修改儲存 PDF 文件的程式碼來自訂產生的 PDF 檔案的輸出檔案名稱。只需更改所需的檔案名稱即可`doc.Save()`方法。

#### Q：是否可以根據某些條件選擇性地刪除超連結？

答：是的，您可以根據特定條件選擇性地刪除超連結。例如，您可以選擇僅刪除外部連結或指向特定 URL 的連結。