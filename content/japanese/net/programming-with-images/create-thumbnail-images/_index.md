---
title: PDF ファイルにサムネイル画像を作成する
linktitle: PDF ファイルにサムネイル画像を作成する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、PDF ファイルにサムネイル画像を簡単に作成できます。
type: docs
weight: 100
url: /ja/net/programming-with-images/create-thumbnail-images/
---
このガイドでは、Aspose.PDF for .NET を使用して PDF ファイルにサムネイル画像を作成する方法を段階的に説明します。環境がすでにセットアップされていることを確認し、以下の手順に従ってください。

## ステップ 1: ドキュメント ディレクトリを定義する

開始する前に、ドキュメント用に正しいディレクトリを設定していることを確認してください。交換する`"YOUR DOCUMENT DIRECTORY"`コード内で PDF ファイルを含むディレクトリへのパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ディレクトリ内のすべての PDF ファイルの名前を取得する

このステップでは、C# のコマンドを使用して、指定されたディレクトリに存在するすべての PDF ファイルの名前を取得します。`Directory`クラス。ファイルは文字列の配列に保存されます。

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## ステップ 3: すべての PDF ファイルとそのページを参照する

このステップでは、すべての PDF ファイルとそのページを調べて、画像のサムネイルを作成します。を使用します。`for`ループを使用してすべてのファイルを反復処理します。

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     //PDF ドキュメントを開く
     Document pdfDocument = new Document(fileEntries[counter]);
    
     //文書のすべてのページに目を通す
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         //サムネイル画像を保存するストリームを作成する
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             //解像度オブジェクトを作成する
             Resolution resolution = new Resolution(300);
            
             //指定された属性を持つ JPEG デバイスを作成します
             JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
            
             //特定のページを変換し、画像をストリームに保存します
             jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
            
             //ストリームを閉じる
             imageStream.Close();
         }
     }
}
```

### Aspose.PDF for .NET を使用してサムネイル イメージを作成するためのサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//特定のディレクトリ内のすべての PDF ファイルの名前を取得します
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
//配列内のすべてのファイルエントリを反復処理します。
for (int counter = 0; counter < fileEntries.Length; counter++)
{
	//開いた文書
	Document pdfDocument = new Document(fileEntries[counter]);
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "\\Thumbanils" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
		{
			//解像度オブジェクトの作成
			Resolution resolution = new Resolution(300);
			//JpegDevice jpegDevice = new JpegDevice(500, 700, 解像度, 100);
			JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
			//特定のページを変換し、画像をストリームに保存します
			jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
			//ストリームを閉じる
			imageStream.Close();
		}
	}
}
System.Console.WriteLine("PDF pages are converted to thumbnails successfully!");
```

## 結論

おめでとうございます！ Aspose.PDF for .NET を使用して、PDF ファイルから画像サムネイルを正常に作成できました。画像のサムネイルは指定したディレクトリに保存されます。これらのサムネイルを使用して、PDF ファイルの視覚的なプレビューを表示できるようになりました。

### PDFファイルにサムネイル画像を作成する場合のFAQ

#### Q: Aspose.PDF for .NET を使用して PDF ファイルからサムネイル画像を作成する目的は何ですか?

A: PDF ファイルからサムネイル画像を作成すると、PDF 内の各ページの小さな視覚的なプレビューを生成できます。これは、コンテンツをすばやくプレビューして移動するのに役立ちます。

#### Q: Aspose.PDF for .NET を使用すると、PDF ファイルからのサムネイル イメージの作成がどのように容易になりますか?

A: Aspose.PDF for .NET は、PDF ドキュメントを開き、そのページを繰り返し処理し、サムネイル画像を作成し、それらを指定のディレクトリに保存するための段階的なプロセスを提供します。`JpegDevice`クラス。

#### Q: サムネイル画像の作成を開始する前にドキュメント ディレクトリを定義することが重要なのはなぜですか?

A: ドキュメント ディレクトリを指定すると、PDF ファイルが正しく配置され、結果のサムネイル画像が目的の出力パスに保存されます。

####  Q: どうやって`Document` class in Aspose.PDF for .NET help in the creation of thumbnail images?

 A:`Document`クラスを使用すると、PDF ドキュメントを開いて操作できます。この場合、サムネイル画像の作成元となる PDF ファイルをロードするために使用されます。

####  Q：どのような役割をするのですか`JpegDevice` class play in the creation of thumbnail images?

 A:`JpegDevice`このクラスは、PDF ページをサムネイル画像として使用される JPEG 画像に変換する役割を果たします。幅、高さ、解像度、品質などの属性を指定できます。

#### Q: PDF ドキュメントの各ページはどのようにして個別のサムネイル画像に変換されますか?

 A: ネストされた`for`ループは、各 PDF ファイルとそのページを反復処理するために使用されます。ページごとに、指定された属性を使用して JPEG デバイスが作成され、`Process`メソッドを使用して、ページをサムネイル画像に変換し、ストリームに保存します。

#### Q: 作成プロセス中に、結果として得られるサムネイル画像の解像度や品質を調整できますか?

 A: はい、解像度、幅、高さ、品質などの属性は、`JpegDevice`各ページを変換する前のオブジェクト。

#### Q: 生成されたサムネイル画像は、作成プロセス後にプロジェクトまたはアプリケーションでどのように利用できますか?

A: 生成されたサムネイル画像を使用して PDF ファイルの視覚的なプレビューを提供し、ユーザーがコンテンツをすばやく識別して移動できるようにします。

#### : この作成プロセスで PDF ファイルから生成できるサムネイル画像の数に制限はありますか?

A: 生成されるサムネイル画像の数は、各 PDF ドキュメントのページ数によって異なります。各ページは個別のサムネイル画像に変換されます。