---
title: PDF ファイルにサムネイル画像を作成する
linktitle: PDF ファイルにサムネイル画像を作成する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、PDF ファイルにサムネイル画像を簡単に作成できます。
type: docs
weight: 100
url: /ja/net/programming-with-images/create-thumbnail-images/
---
このガイドでは、Aspose.PDF for .NET を使用して PDF ファイルにサムネイル画像を作成する方法を段階的に説明します。環境がすでに設定されていることを確認し、以下の手順に従ってください。

## ステップ1: ドキュメントディレクトリを定義する

始める前に、ドキュメントの正しいディレクトリを設定してください。`"YOUR DOCUMENT DIRECTORY"`コード内に、PDF ファイルを含むディレクトリへのパスを含めます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: ディレクトリ内のすべてのPDFファイルの名前を取得する

このステップでは、C#を使用して、指定されたディレクトリにあるすべてのPDFファイルの名前を取得します。`Directory`クラス。ファイルは文字列の配列に保存されます。

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## ステップ3: すべてのPDFファイルとそのページを参照する

このステップでは、すべてのPDFファイルとそのページを調べて画像のサムネイルを作成します。`for`すべてのファイルを反復処理するループ。

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     // PDF文書を開く
     Document pdfDocument = new Document(fileEntries[counter]);
    
     //文書の全ページを確認する
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         //サムネイル画像を保存するためのストリームを作成する
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             //解決オブジェクトを作成する
             Resolution resolution = new Resolution(300);
            
             //指定された属性を持つJPEGデバイスを作成する
             JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
            
             //特定のページを変換し、画像をストリームに保存する
             jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
            
             //ストリームを閉じる
             imageStream.Close();
         }
     }
}
```

### Aspose.PDF for .NET を使用してサムネイル画像を作成するためのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//特定のディレクトリ内のすべてのPDFファイルの名前を取得します
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
//配列内のすべてのファイルエントリを反復処理する
for (int counter = 0; counter < fileEntries.Length; counter++)
{
	//ドキュメントを開く
	Document pdfDocument = new Document(fileEntries[counter]);
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "\\Thumbanils" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
		{
			//解決オブジェクトを作成する
			Resolution resolution = new Resolution(300);
			//JpegDevice jpegDevice = new JpegDevice(500, 700, 解像度, 100);
			JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
			//特定のページを変換し、画像をストリームに保存する
			jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
			//ストリームを閉じる
			imageStream.Close();
		}
	}
}
System.Console.WriteLine("PDF pages are converted to thumbnails successfully!");
```

## 結論

おめでとうございます! Aspose.PDF for .NET を使用して PDF ファイルから画像のサムネイルを正常に作成しました。画像のサムネイルは指定されたディレクトリに保存されます。これで、これらのサムネイルを使用して PDF ファイルの視覚的なプレビューを表示できます。

### PDF ファイルにサムネイル画像を作成するための FAQ

#### Q: Aspose.PDF for .NET を使用して PDF ファイルからサムネイル画像を作成する目的は何ですか?

A: PDF ファイルからサムネイル画像を作成すると、PDF 内の各ページの小さな視覚的なプレビューを生成できます。これは、コンテンツをすばやくプレビューしたりナビゲートしたりするのに役立ちます。

#### Q: Aspose.PDF for .NET ではどのようにして PDF ファイルからのサムネイル画像の作成が容易になりますか?

 A: Aspose.PDF for .NETは、PDFドキュメントを開き、ページを反復処理し、サムネイル画像を作成し、指定されたディレクトリに保存するためのステップバイステップのプロセスを提供します。`JpegDevice`クラス。

#### Q: サムネイル画像の作成を開始する前にドキュメント ディレクトリを定義することが重要なのはなぜですか?

A: ドキュメント ディレクトリを指定すると、PDF ファイルが正しく配置され、結果のサムネイル画像が目的の出力パスに保存されます。

####  Q:`Document` class in Aspose.PDF for .NET help in the creation of thumbnail images?

 A:`Document`クラスを使用すると、PDF ドキュメントを開いて操作できます。この場合、サムネイル画像が作成される PDF ファイルを読み込むために使用されます。

####  Q:`JpegDevice` class play in the creation of thumbnail images?

 A:`JpegDevice`クラスは、PDF ページをサムネイル画像として使用される JPEG 画像に変換する役割を担います。幅、高さ、解像度、品質などの属性を指定できます。

#### Q: PDF ドキュメントの各ページはどのようにして個別のサムネイル画像に変換されるのですか?

 A: ネストされた`for`ループは各PDFファイルとそのページを反復処理するために使用されます。各ページに対して、指定された属性を持つJPEGデバイスが作成され、`Process`メソッドは、ページをサムネイル画像に変換し、ストリームに保存するために使用されます。

#### Q: 作成プロセス中に、結果として得られるサムネイル画像の解像度や品質を調整できますか?

A: はい、解像度、幅、高さ、品質などの属性は、`JpegDevice`各ページを変換する前にオブジェクトを作成します。

#### Q: 作成プロセス後に生成されたサムネイル画像をプロジェクトやアプリケーションで利用するにはどうすればよいですか?

A: 生成されたサムネイル画像を使用すると、PDF ファイルの視覚的なプレビューが提供され、ユーザーがコンテンツをすばやく識別してナビゲートするのに役立ちます。

#### : この作成プロセスを使用して PDF ファイルから生成できるサムネイル画像の数に制限はありますか?

A: 生成されるサムネイル画像の数は、各 PDF ドキュメントのページ数によって異なります。各ページは個別のサムネイル画像に変換されます。