---
title: PDF ファイルのファイル圧縮を無効にする
linktitle: PDF ファイルのファイル圧縮を無効にする
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルのファイル圧縮を無効にする方法を学びます。簡単に操作できるステップバイステップのガイド。
type: docs
weight: 30
url: /ja/net/programming-with-attachments/disable-files-compression/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF のファイル圧縮を無効にする次の C# ソース コードを段階的に説明します。

始める前に、Aspose.PDF ライブラリをインストールし、開発環境をセットアップしていることを確認してください。 C# プログラミングの基本的な知識も必要です。

### ステップ 1: ドキュメント ディレクトリのセットアップ

提供されたソース コードでは、ファイル圧縮を無効にする PDF ファイルが配置されているディレクトリを指定する必要があります。 「dataDir」変数を目的のディレクトリに変更します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### ステップ 2: 既存の PDF ドキュメントを開く

指定されたパスを使用して既存の PDF ドキュメントを開きます。

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### ステップ 3: 添付ファイルとして追加する新しいファイルを設定する

添付ファイルとして追加する新しいファイルを構成します。この例では、「test_out.txt」という名前と「サンプル テキスト ファイル」という説明を持つテキスト ファイルを追加します。

```csharp
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
```

### ステップ 4: ファイル圧縮を無効にする

FileSpecific オブジェクトの Encoding プロパティを FileEncoding.None に設定することで、ファイル圧縮を無効にします。

```csharp
fileSpecification.Encoding = FileEncoding.None;
```

### ステップ 5: ドキュメントの添付ファイル コレクションに添付ファイルを追加する

添付ファイルをドキュメントの添付ファイル コレクションに追加します。

```csharp
pdfDocument.EmbeddedFiles.Add(fileSpecification);
```

### ステップ 6: 新しい出力ファイルを保存する

最後に、結果の新しい PDF ファイルを「DisableFilesCompression_out.pdf」という名前で指定したディレクトリに保存します。

```csharp
pdfDocument.Save(dataDir + "DisableFilesCompression_out.pdf");
```


### Aspose.PDF for .NET を使用してファイル圧縮を無効にするサンプル ソース コード 

```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
//添付ファイルとして追加する新しいファイルを設定します
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
//Encoding プロパーティを FileEncoding.None に設定して指定します。
fileSpecification.Encoding = FileEncoding.None;
//ドキュメントの添付ファイル コレクションに添付ファイルを追加する
pdfDocument.EmbeddedFiles.Add(fileSpecification);
dataDir = dataDir + "DisableFilesCompression_out.pdf";
//新しい出力を保存する
pdfDocument.Save(dataDir);
Console.WriteLine("\nFile compression disabled successfully.\nFile saved at " + dataDir);

```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF のファイル圧縮を無効にする方法を説明しました。この知識を利用して、圧縮せずに添付ファイルの整合性を維持できるようになりました。

## PDF ファイルのファイル圧縮を無効にするための FAQ

#### Q: PDF ドキュメントのファイル圧縮を無効にする必要があるのはなぜですか?

A: ファイル圧縮を無効にすると、PDF ドキュメント内の添付ファイルは圧縮されず、元の品質と内容が維持されます。

#### Q: ファイル圧縮を無効にすると、PDF 添付ファイルにどのようなメリットがありますか?

A: 圧縮を無効にすると、圧縮プロセス中に発生する可能性のあるデータや品質の損失が防止され、添付ファイルがそのまま表示されます。

#### Q: このチュートリアルを使用して、特定の添付ファイルの圧縮を選択的に無効にすることはできますか?

A: はい。このチュートリアルでは、PDF ドキュメント内の個々の添付ファイルのファイル圧縮を無効にして、きめ細かい制御を提供する方法を説明します。

#### Q: どのような種類の添付ファイルの圧縮を無効にできますか?

A: 画像、ドキュメント、スプレッドシートなど、あらゆる種類の添付ファイルの圧縮を無効にして、その整合性を確保できます。

#### Q: 圧縮を無効にすると、PDF ドキュメント全体のファイル サイズに影響しますか?

A: 添付ファイルの圧縮を無効にすると、非圧縮ファイルがより多くのスペースを占有するため、PDF ドキュメント全体のファイル サイズが若干増加する可能性があります。

#### Q: Aspose.PDF for .NET は、ファイル圧縮を無効にするプロセスをどのように容易にしますか?

A: Aspose.PDF for .NET は、提供されたソース コードで示されているように、添付ファイルのファイル圧縮を無効にすることができる使いやすい API を提供します。

#### Q: 必要に応じて、後で添付ファイルの圧縮を再度有効にすることはできますか?

A: はい、必要に応じて添付ファイルの設定を変更して圧縮を再度有効にすることができます。

#### Q: 圧縮をサポートするデバイスまたはソフトウェアで PDF を開くとどうなりますか?

A: 圧縮をサポートするデバイスまたはソフトウェアで PDF を開くと、添付ファイルが圧縮されずに表示される可能性があり、ファイル サイズとレンダリング パフォーマンスに影響を与える可能性があります。

#### Q: 圧縮を無効にすることが推奨される特定のシナリオはありますか?

A: 高解像度の画像や機密文書など、元の品質とデータの整合性を維持することが優先される添付ファイルについては、圧縮を無効にすることをお勧めします。