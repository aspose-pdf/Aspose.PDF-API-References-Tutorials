---
title: 画像の抽出
linktitle: 画像の抽出
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、PDF ドキュメントから画像を簡単に抽出できます。
type: docs
weight: 70
url: /ja/net/programming-with-security-and-signatures/extracting-image/
---
PDF ドキュメントから画像を抽出すると、多くの場合に役立ちます。 Aspose.PDF for .NET では、次のソース コードを使用して画像を簡単に抽出できます。

## ステップ 1: 必要なライブラリをインポートする

始める前に、C# プロジェクトに必要なライブラリをインポートする必要があります。必要なインポート ディレクティブは次のとおりです。

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## ステップ 2: ドキュメントフォルダーへのパスを設定する

この手順では、画像を抽出する PDF ファイルが含まれるフォルダーへのパスを指定する必要があります。交換する`"YOUR DOCUMENTS DIRECTORY"`次のコードでは、ドキュメント フォルダーへの実際のパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## ステップ 3: PDF ドキュメントから画像を抽出する

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
//ドキュメントディレクトリへのパス。
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

おめでとうございます！これで、Aspose.PDF for .NET を使用して PDF ドキュメントから画像を抽出するためのステップバイステップのガイドが完成しました。このコードを独自のプロジェクトに統合して、必要に応じて画像を抽出して使用できます。

高度な画像抽出および PDF ドキュメント操作機能の詳細については、公式の Aspose.PDF ドキュメントを必ずご確認ください。


### よくある質問

#### Q: Aspose.PDF for .NET は初心者に適していますか?

A: C# プログラミングにある程度の知識があると役に立ちますが、チュートリアルは初心者向けに設計されており、各ステップをガイドします。

#### Q: 複数の画像を一度に抽出できますか?

A: もちろんです！ループを実装し、提供されたコードを適応させることで、1 つの PDF ドキュメントから複数の画像を抽出できます。

#### Q: Aspose.PDF for .NET が画像抽出の唯一のソリューションですか?

A: 他にも利用可能なツールはありますが、Aspose.PDF for .NET はその効率性と包括的な機能で知られています。

#### Q: 抽出した画像を商用目的で使用できますか?

A: はい、抽出した画像は、商業プロジェクトなど、必要に応じて使用できます。

#### Q: Aspose.PDF を使用した PDF 操作に関するその他のリソースはどこで見つけられますか?

A: Aspose.PDF for .NET を使用した高度な PDF 操作に関する豊富なリソースと洞察については、公式ドキュメントを参照してください。