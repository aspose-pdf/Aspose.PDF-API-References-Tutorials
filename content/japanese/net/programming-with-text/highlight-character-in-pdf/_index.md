---
title: PDFファイル内の文字を強調表示する
linktitle: PDFファイル内の文字を強調表示する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内の文字を強調表示する方法を学びます。
type: docs
weight: 240
url: /ja/net/programming-with-text/highlight-character-in-pdf/
---
このチュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ファイル内の文字を強調表示する方法を説明します。提供されている C# ソース コードを使用して、PDF 内の文字を強調表示するプロセスを段階的に説明します。

## 要件

始める前に、以下のものがあることを確認してください。

- Aspose.PDF for .NET ライブラリがインストールされています。
- C# プログラミングの基本的な理解。

## ステップ 1: ドキュメント ディレクトリを設定する

まず、入力 PDF ファイルが配置されているディレクトリへのパスを設定する必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`の中に`dataDir`変数を PDF ファイルへのパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: PDF ドキュメントをロードする

次に、次のコマンドを使用して入力 PDF ドキュメントを読み込みます。`Aspose.Pdf.Document`クラス。

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## ステップ 3: PDF を画像に変換する

文字を強調表示するには、PDF ドキュメントを画像に変換します。`PdfConverter`クラス。変換の解像度を設定し、画像を`Bitmap`物体。

```csharp
int resolution = 150;
using (MemoryStream ms = new MemoryStream())
{
     PdfConverter conv = new PdfConverter(pdfDocument);
     conv. Resolution = new Resolution(resolution, resolution);
     conv. GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
     Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```

## ステップ 4: 文字を強調表示する

PDF ドキュメントの各ページをループして、`TextFragmentAbsorber`ページ内のすべての単語を検索するオブジェクト。次に、テキストの断片、セグメント、文字を反復処理して、長方形を使用してそれらを強調表示します。

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     //スケールと変形を設定する
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     //ページをループする
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         //ページ内のすべての単語を検索します
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
                         //ハイライト文字
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

## ステップ 5: 出力画像を保存する

最後に、強調表示された文字を含む変更された画像を指定された出力ファイルに保存します。

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### Aspose.PDF for .NET を使用した PDF のハイライト文字のサンプル ソース コード 
```csharp
try
{
	//ドキュメントディレクトリへのパス。
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
				//すべての単語を検索する TextAbsorber オブジェクトを作成する
				TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
				textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
				page.Accept(textFragmentAbsorber);
				//抽出されたテキスト断片を取得する
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

このチュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ドキュメント内の文字を強調表示する方法を学習しました。ステップバイステップのガイドに従って、提供されている C# コードを実行すると、PDF 内の文字を強調表示し、出力を画像として保存できます。

### よくある質問

#### Q: 「PDF ファイル内の文字をハイライトする」チュートリアルの目的は何ですか?

A: 「PDF ファイル内の文字を強調表示する」チュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ドキュメント内の文字を強調表示する方法を説明しています。このチュートリアルでは、これを実現するためのステップバイステップのガイドと C# ソース コードを提供します。

#### Q: PDF ドキュメント内の文字を強調表示したいのはなぜですか?

A: PDF ドキュメント内の文字を強調表示すると、特定のコンテンツを強調したり、特定のテキストをより見やすく区別したりするなど、さまざまな目的に役立ちます。

#### Q: ドキュメント ディレクトリはどのように設定すればよいですか?

A: ドキュメント ディレクトリを設定するには:

1. 交換する`"YOUR DOCUMENT DIRECTORY"`の中に`dataDir`変数には、入力 PDF ファイルが配置されているディレクトリへのパスを指定します。

#### Q: PDF ドキュメントをロードして画像に変換するにはどうすればよいですか?

 A: チュートリアルでは、`Aspose.Pdf.Document`クラスは、入力 PDF ドキュメントをロードするために使用されます。そうして`PdfConverter`PDF ドキュメントを画像に変換するためにクラスが使用されます。画像の解像度が設定され、画像が`Bitmap`物体。

#### Q: PDF ドキュメント画像内の文字を強調表示するにはどうすればよいですか?

A: このチュートリアルでは、PDF ドキュメントの各ページをループし、`TextFragmentAbsorber`、テキストの断片、セグメント、文字を反復処理して、長方形を使用してそれらを強調表示します。

#### Q: ハイライトされた文字やセグメントの外観をカスタマイズできますか?

A: はい、描画操作で使用される色とスタイルを変更することで、強調表示された文字とセグメントの外観をカスタマイズできます。

#### Q: 変更した文字を強調表示した画像を保存するにはどうすればよいですか?

 A: このチュートリアルでは、強調表示された文字を含む変更されたイメージを、`Save`の方法`Bitmap`クラス。

#### Q: このチュートリアルには有効な Aspose ライセンスが必要ですか?

A: はい、このチュートリアルが正しく動作するには、有効な Aspose ライセンスが必要です。 Aspose Web サイトから完全ライセンスを購入するか、30 日間の一時ライセンスを取得できます。