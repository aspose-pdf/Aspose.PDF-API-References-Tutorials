---
title: 署名情報の抽出
linktitle: 署名情報の抽出
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用した署名情報の抽出。
type: docs
weight: 80
url: /ja/net/programming-with-security-and-signatures/extract-signature-info/
---
PDF ドキュメントから署名情報を抽出するプロセスは、さまざまなシナリオで非常に役立ちます。署名されたドキュメントの信頼性を検証する必要がある場合でも、署名に使用された証明書を分析する必要がある場合でも、Aspose.PDF for .NET ライブラリは便利なソリューションを提供します。このチュートリアルでは、提供されている C# ソース コードを使用して署名情報を抽出するプロセスを段階的に説明します。

## 要件

始める前に、次の前提条件が満たされていることを確認してください。

1. C# プログラミング言語の基本的な知識。
2. Aspose.PDF for .NET ライブラリがシステムにインストールされています。
3. 1 つ以上の署名フィールドを持つ有効な PDF ドキュメント。

それでは、実装の詳細を見ていきましょう。

## ステップ 1: 必要なライブラリのインポート

開始するには、必要なライブラリを C# プロジェクトにインポートする必要があります。この場合、インポートする必要があります`Aspose.Pdf`そして`System.IO`名前空間。これを行うには、C# ファイルの先頭に次のコードを追加します。

```csharp
using Aspose.Pdf;
using System.IO;
```

## ステップ 2: ドキュメント パスの設定

次に、署名情報を抽出する PDF ドキュメントへのパスを設定する必要があります。交換する`"YOUR DOCUMENTS DIRECTORY"`次のコード スニペットでは、ドキュメントへの実際のパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

## ステップ 3: 署名情報の抽出

ここで、PDF ドキュメントから署名情報を抽出するコードの主要部分に進みましょう。ドキュメントのフォームの各フィールドを繰り返し処理し、それが署名フィールドであるかどうかを確認します。署名フィールドが見つかった場合は、証明書の抽出に進みます。次のコード スニペットを追加します。

```csharp
using (Document pdfDocument = new Document(input))
{
     foreach(Field field in pdfDocument.Form)
     {
         SignatureField sf = field as SignatureField;
         if (sf != null)
         {
             //証明書を抽出する
             Stream cerStream = sf.ExtractCertificate();
             if (cerStream != null)
             {
                 using (cerStream)
                 {
                     byte[] bytes = new byte[cerStream.Length];
                     using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
                     {
                         cerStream.Read(bytes, 0, bytes.Length);
                         fs.Write(bytes, 0, bytes.Length);
                     }
                 }
             }
         }
     }
}
```

## ステップ 4: 証明書の抽出

このステップでは、署名フィールドから証明書を抽出し、ファイルとして保存します。抽出された証明書はさらに分析したり、検証目的で使用したりできます。以下のコード スニペットは、抽出と保存のプロセスを示しています。

```csharp
Stream cerStream = sf.ExtractCertificate();
if (cerStream != null)
{
     using (cerStream)
     {
         byte[] bytes = new byte[cerStream.Length];
         using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
         {
             cerStream.Read(bytes, 0, bytes.Length);
             fs.Write(bytes, 0, bytes.Length);
         }
     }
}
```

## ステップ5

: 証明書の保存

最後に、抽出した証明書をファイルとして保存します。この例では、証明書は「input.cer」という名前で指定されたディレクトリに保存されます。要件に合わせてコードを変更できます。証明書を保存するためのコード スニペットは次のとおりです。

```csharp
using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
{
     fs.Write(bytes, 0, bytes.Length);
}
```

それでおしまい！ Aspose.PDF for .NET を使用して署名情報が正常に抽出されました。このコードを独自のアプリケーションに自由に統合したり、ニーズに応じて変更したりできます。

### Aspose.PDF for .NET を使用した署名情報の抽出のサンプル ソース コード 
```csharp
try
{
	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string input = dataDir + "ExtractSignatureInfo.pdf";
	using (Document pdfDocument = new Document(input))
	{
		foreach (Field field in pdfDocument.Form)
		{
			SignatureField sf = field as SignatureField;
			if (sf != null)
			{
				Stream cerStream = sf.ExtractCertificate();
				if (cerStream != null)
				{
					using (cerStream)
					{
						byte[] bytes = new byte[cerStream.Length];
						using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
						{
							cerStream.Read(bytes, 0, bytes.Length);
							fs.Write(bytes, 0, bytes.Length);
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET ライブラリを使用して PDF ドキュメントから署名情報を抽出する方法について段階的なガイドを説明しました。必要なライブラリのインポート、ドキュメント パスの設定、署名情報の抽出、証明書の抽出、ファイルへの保存のプロセスについて説明しました。これらの手順に従うことで、署名の詳細を簡単に取得し、必要に応じて操作できます。

### よくある質問

#### Q: PDF ドキュメントから署名情報を抽出する必要があるのはなぜですか?

A: PDF ドキュメントから署名情報を抽出すると、署名されたドキュメントの信頼性を検証し、署名に使用された証明書を分析するのに役立ちます。このプロセスは、署名されたコンテンツの整合性を確保するのに役立ち、法的およびセキュリティの目的で不可欠です。

#### Q: Aspose.PDF for .NET とは何ですか?

A: Aspose.PDF for .NET は、開発者が .NET アプリケーションで PDF ドキュメントを操作できるようにするライブラリです。 PDF ファイルをプログラムで作成、変更、操作するための幅広い機能を提供します。

#### Q: Aspose.PDF for .NET を使用して署名情報を抽出するための前提条件は何ですか?

A: 署名情報を抽出するには、C# プログラミング言語、システムにインストールされている Aspose.PDF for .NET ライブラリ、および 1 つ以上の署名フィールドを含む有効な PDF ドキュメントに関する基本的な知識が必要です。

#### Q: 抽出プロセスに必要なライブラリをインポートするにはどうすればよいですか?

A: を追加することで、必要なライブラリをインポートできます。`using`に対する指令`Aspose.Pdf`そして`System.IO`C# ファイルの先頭に。これらのディレクティブを使用すると、署名情報の抽出に必要なクラスとメソッドを使用できるようになります。

#### Q: 署名情報を抽出する PDF ドキュメントを指定するにはどうすればよいですか?

 A: を置き換えることにより、PDF ドキュメントへのパスを設定できます。`"YOUR DOCUMENTS DIRECTORY"`提供されたコード スニペット内のドキュメントへの実際のパスを使用してください。このパスは、署名情報を抽出する PDF ドキュメントをロードするために使用されます。

#### Q: PDF ドキュメントから署名情報を抽出するプロセスはどのようなものですか?

A: 抽出プロセスでは、PDF ドキュメントのフォーム フィールドを繰り返し処理し、各フィールドが署名フィールドであるかどうかを確認し、署名フィールドである場合は関連する証明書を抽出します。抽出された証明書は、さらに分析または検証するためにファイルとして保存できます。

#### Q: 署名フィールドから証明書はどのように抽出されますか?

A: 証明書は、次のコマンドを使用して署名フィールドから抽出されます。`ExtractCertificate()`によって提供されるメソッド`SignatureField` Aspose.PDF for .NET のクラス。このメソッドは、証明書データを含むストリームを返します。

#### Q: 抽出した証明書をファイルとして保存するにはどうすればよいですか?

 A: 抽出した証明書をファイルとして保存するには、証明書ストリームを読み取り、その内容をファイルに書き込みます。`FileStream`クラス。チュートリアルで提供されるコードは、このプロセスを示しています。

#### Q: この抽出した証明書を署名検証に使用できますか?

A: はい、抽出された証明書は署名の検証に使用できます。証明書の詳細を分析し、その信頼性を検証して、署名された文書の整合性を確保できます。

#### Q: このコードを自分のアプリケーションに統合するにはどうすればよいですか?

A: ステップバイステップのガイドに従って、提供されたコードを独自の C# アプリケーションに統合できます。必要に応じてパスとファイル名を変更し、コードを既存のプロジェクトに組み込みます。

#### Q: Aspose.PDF for .NET には署名管理に関連する他の機能はありますか?

A: はい。Aspose.PDF for .NET は、ドキュメントの署名、署名の検証、タイムスタンプ情報の追加など、デジタル署名を操作するためのさまざまな機能を提供します。これらの機能の詳細については、公式ドキュメントを参照してください。

#### Q: Aspose.PDF for .NET を使用するための追加リソースはどこで見つけられますか?

 A: .NET 用 Aspose.PDF の使用に関する詳細、チュートリアル、リソースについては、[Aspose.PDF for .NET](https://reference.aspose.com/pdf/net/).

#### Q: 暗号化された PDF ドキュメントから署名を抽出することはできますか?

A: 暗号化された PDF ドキュメントから署名を抽出できるかどうかは、ドキュメントの暗号化設定と権限によって異なる場合があります。署名情報にアクセスして抽出するために必要な権限があることを確認する必要がある場合があります。

#### Q: 1 つの PDF ドキュメントから複数の署名を抽出できますか?

A: はい、提供されたコードを変更して、PDF ドキュメント内のすべての署名フィールドを反復処理し、各フィールドから署名情報を抽出できます。これにより、文書内に存在する複数の署名に関する情報を抽出できます。

#### Q: 署名情報を抽出する実際の使用例にはどのようなものがありますか?

A: 署名情報を抽出する実際の使用例には、デジタル署名された文書の信頼性の検証、コンプライアンス目的での証明書の詳細の分析、監査目的での署名と署名者の記録の維持などが含まれます。

#### Q: 署名情報を抽出する際に法的考慮事項はありますか?

A: 署名情報の抽出は、特に法的拘束力のある文書を扱う場合に、法的な影響を与える可能性があります。管轄区域内の電子署名および文書の信頼性に関する関連規制および法律を必ず遵守してください。