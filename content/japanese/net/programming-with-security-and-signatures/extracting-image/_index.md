---
title: 画像の抽出
linktitle: 画像の抽出
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、PDF ドキュメントから画像を簡単に抽出できます。
type: docs
weight: 70
url: /ja/net/programming-with-security-and-signatures/extracting-image/
---
PDF ドキュメントから画像を抽出することは、多くの場合に便利です。Aspose.PDF for .NET では、次のソース コードを使用して簡単に画像を抽出できます。

## ステップ1: 必要なライブラリをインポートする

始める前に、C# プロジェクトに必要なライブラリをインポートする必要があります。必要なインポート ディレクティブは次のとおりです。

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## ステップ2: ドキュメントフォルダへのパスを設定する

この手順では、画像を抽出するPDFファイルを含むフォルダへのパスを指定する必要があります。`"YOUR DOCUMENTS DIRECTORY"`次のコードでは、ドキュメント フォルダーへの実際のパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## ステップ3: PDF文書から画像を抽出する

ここで、次のコードを使用して PDF ドキュメントから画像を抽出します。

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

この例では、PDF ドキュメント内のフォームの各フィールドをループします。署名フィールドが見つかった場合は、関連する画像を抽出し、JPEG ファイルに保存します。

### Aspose.PDF for .NET を使用して画像を抽出するためのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
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

おめでとうございます！これで、Aspose.PDF for .NET を使用して PDF ドキュメントから画像を抽出するためのステップ バイ ステップ ガイドができました。このコードを独自のプロジェクトに統合して、画像を抽出し、必要に応じて使用することができます。

高度な画像抽出機能と PDF ドキュメント操作機能の詳細については、公式の Aspose.PDF ドキュメントを必ず確認してください。


### よくある質問

#### Q: Aspose.PDF for .NET は初心者に適していますか?

A: C# プログラミングに多少精通していると役立ちますが、このチュートリアルは初心者向けに設計されており、各ステップをガイドします。

#### Q: 一度に複数の画像を抽出できますか?

A: もちろんです! ループを実装し、提供されているコードを適応させることで、単一の PDF ドキュメントから複数の画像を抽出できます。

#### Q: Aspose.PDF for .NET は画像抽出の唯一のソリューションですか?

A: 他にも利用できるツールはありますが、Aspose.PDF for .NET は効率性と包括的な機能で定評があります。

#### Q: 抽出した画像を商用目的で使用できますか?

A: はい、一度抽出した画像は、商業プロジェクトを含め、必要に応じて自由に使用できます。

#### Q: Aspose.PDF を使用した PDF 操作に関する詳細なリソースはどこで入手できますか?

A: Aspose.PDF for .NET を使用した高度な PDF 操作に関する豊富なリソースと詳細情報については、弊社の公式ドキュメントをご覧ください。