---
title: PDF ファイル内の文字を強調表示する
linktitle: PDF ファイル内の文字を強調表示する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内の文字を強調表示する方法を学びます。
type: docs
weight: 240
url: /ja/net/programming-with-text/highlight-character-in-pdf/
---
このチュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ファイル内の文字を強調表示する方法について説明します。提供されている C# ソース コードを使用して、PDF 内の文字を強調表示するプロセスを段階的に説明します。

## 要件

始める前に、次のものがあることを確認してください。

- Aspose.PDF for .NET ライブラリがインストールされました。
- C# プログラミングの基本的な理解。

## ステップ1: ドキュメントディレクトリを設定する

まず、入力PDFファイルが保存されているディレクトリへのパスを設定する必要があります。`"YOUR DOCUMENT DIRECTORY"`の`dataDir` PDF ファイルへのパスを含む変数。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: PDFドキュメントを読み込む

次に、入力PDF文書を読み込み、`Aspose.Pdf.Document`クラス。

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## ステップ3: PDFを画像に変換する

文字を強調するには、PDF文書を画像に変換します。`PdfConverter`クラス。変換の解像度を設定し、画像を`Bitmap`物体。

```csharp
int resolution = 150;
using (MemoryStream ms = new MemoryStream())
{
     PdfConverter conv = new PdfConverter(pdfDocument);
     conv. Resolution = new Resolution(resolution, resolution);
     conv. GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
     Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```

## ステップ4: 文字を強調表示する

PDF文書の各ページをループし、`TextFragmentAbsorber`オブジェクトを使用して、ページ内のすべての単語を検索します。次に、テキストのフラグメント、セグメント、文字を反復処理して、四角形を使用して強調表示します。

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     //スケールと変換を設定する
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     //ページをループする
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         //ページ内のすべての単語を検索
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         //テキストの断片をループする
         foreach(TextFragment textFragment in textFragmentCollection)
         {
             if (i == 0)
             {
                 //文字を強調表示する
                 gr.DrawRectangle(
                     Think.Yellow,
                     (float)textFragment.Position.XIndent,
                     (float)textFragment.Position.YIndent,
                     (float)textFragment.Rectangle.Width,
                     (float)textFragment.Rectangle.Height);

                 //セグメントをループする
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     //ハイライトセグメント
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     //文字をループする
                     foreach(CharInfo characterInfo in segment.Characters)
                     {
                         //ハイライトキャラクター
                         gr.DrawRectangle(
                             Think.Black,
                             (float)characterInfo.Rectangle.LLx,
                             (float)characterInfo.Rectangle.LLY,
                             (float)characterInfo.Rectangle.Width,
                             (float)characterInfo.Rectangle.Height);
                     }
                 }
             }
         }
     }
}
```

## ステップ5: 出力画像を保存する

最後に、強調表示された文字を含む変更された画像を指定された出力ファイルに保存します。

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### Aspose.PDF for .NET を使用して PDF 内の文字を強調表示するサンプル ソース コード 
```csharp
try
{
	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	int resolution = 150;
	Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
	using (MemoryStream ms = new MemoryStream())
	{
		PdfConverter conv = new PdfConverter(pdfDocument);
		conv.Resolution = new Resolution(resolution, resolution);
		conv.GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
		using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
		{
			float scale = resolution / 72f;
			gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);
			for (int i = 0; i < pdfDocument.Pages.Count; i++)
			{
				Page page = pdfDocument.Pages[1];
				//すべての単語を見つけるためのTextAbsorberオブジェクトを作成する
				TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
				textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
				page.Accept(textFragmentAbsorber);
				//抽出されたテキストフラグメントを取得する
				TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
				//フラグメントをループする
				foreach (TextFragment textFragment in textFragmentCollection)
				{
					if (i == 0)
					{
						gr.DrawRectangle(
						Pens.Yellow,
						(float)textFragment.Position.XIndent,
						(float)textFragment.Position.YIndent,
						(float)textFragment.Rectangle.Width,
						(float)textFragment.Rectangle.Height);
						for (int segNum = 1; segNum <= textFragment.Segments.Count; segNum++)
						{
							TextSegment segment = textFragment.Segments[segNum];
							for (int charNum = 1; charNum <= segment.Characters.Count; charNum++)
							{
								CharInfo characterInfo = segment.Characters[charNum];
								Aspose.Pdf.Rectangle rect = page.GetPageRect(true);
								Console.WriteLine("TextFragment = " + textFragment.Text + "    Page URY = " + rect.URY +
												  "   TextFragment URY = " + textFragment.Rectangle.URY);
								gr.DrawRectangle(
								Pens.Black,
								(float)characterInfo.Rectangle.LLX,
								(float)characterInfo.Rectangle.LLY,
								(float)characterInfo.Rectangle.Width,
								(float)characterInfo.Rectangle.Height);
							}
							gr.DrawRectangle(
							Pens.Green,
							(float)segment.Rectangle.LLX,
							(float)segment.Rectangle.LLY,
							(float)segment.Rectangle.Width,
							(float)segment.Rectangle.Height);
						}
					}
				}
			}
		}
		dataDir = dataDir + "HighlightCharacterInPDF_out.png";
		bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
	}
	Console.WriteLine("\nCharacters highlighted successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http://www.aspose.com/purchase/default.aspx.");
}
```

## 結論

このチュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ドキュメント内の文字を強調表示する方法を学びました。ステップ バイ ステップ ガイドに従って、提供されている C# コードを実行すると、PDF 内の文字を強調表示し、出力を画像として保存できます。

### よくある質問

#### Q: 「PDF ファイル内の文字を強調表示する」チュートリアルの目的は何ですか?

A: 「PDF ファイル内の文字を強調表示する」チュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ドキュメント内の文字を強調表示する方法について説明します。このチュートリアルでは、これを実現するためのステップバイステップのガイドと C# ソース コードが提供されます。

#### Q: PDF 文書内の文字を強調表示する必要があるのはなぜですか?

A: PDF ドキュメント内の文字を強調表示すると、特定のコンテンツを強調したり、特定のテキストをより見やすく識別しやすくしたりするなど、さまざまな目的に役立ちます。

#### Q: ドキュメント ディレクトリを設定するにはどうすればよいですか?

A: ドキュメントディレクトリを設定するには:

1. 交換する`"YOUR DOCUMENT DIRECTORY"`の`dataDir`入力 PDF ファイルが配置されているディレクトリへのパスを持つ変数。

#### Q: PDF ドキュメントを読み込んで画像に変換するにはどうすればよいですか?

 A: チュートリアルでは、`Aspose.Pdf.Document`クラスは入力PDF文書を読み込むために使用されます。次に、`PdfConverter`クラスはPDF文書を画像に変換するために使われます。画像の解像度が設定され、画像は`Bitmap`物体。

#### Q: PDF ドキュメント画像内の文字を強調表示するにはどうすればよいですか?

A: チュートリアルでは、PDF文書の各ページをループし、`TextFragmentAbsorber`テキストの断片、セグメント、文字を反復処理して、四角形を使用して強調表示します。

#### Q: 強調表示された文字やセグメントの外観をカスタマイズできますか?

A: はい、描画操作で使用する色とスタイルを変更することで、強調表示された文字とセグメントの外観をカスタマイズできます。

#### Q: 文字を強調表示した変更後の画像を保存するにはどうすればよいですか?

 A: このチュートリアルでは、強調表示された文字を含む変更された画像を、指定された出力ファイルに保存する方法を説明します。`Save`方法の`Bitmap`クラス。

#### Q: このチュートリアルには有効な Aspose ライセンスが必要ですか?

A: はい、このチュートリアルを正しく動作させるには、有効な Aspose ライセンスが必要です。Aspose Web サイトからフル ライセンスを購入するか、30 日間の一時ライセンスを取得できます。