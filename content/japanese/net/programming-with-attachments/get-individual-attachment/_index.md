---
title: PDF ファイルで個別の添付ファイルを取得する
linktitle: PDF ファイルで個別の添付ファイルを取得する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内の個別の添付ファイルを取得する方法を学びます。
type: docs
weight: 60
url: /ja/net/programming-with-attachments/get-individual-attachment/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルの個別の添付ファイルを取得するために、次の C# ソース コードを段階的に説明します。

始める前に、Aspose.PDF ライブラリをインストールし、開発環境をセットアップしていることを確認してください。 C# プログラミングの基本的な知識も必要です。

### ステップ 1: ドキュメント ディレクトリのセットアップ

提供されたソース コードでは、個々の添付ファイルを取得する PDF ファイルが配置されているディレクトリを指定する必要があります。 「dataDir」変数を目的のディレクトリに変更します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### ステップ 2: 既存の PDF ドキュメントを開く

指定されたパスを使用して既存の PDF ドキュメントを開きます。

```csharp
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
```

### ステップ 3: 特定の添付ファイルの取得

ドキュメントの添付ファイル コレクションから特定の添付ファイルを取得します。この例では、インデックス 1 を使用して最初の添付ファイルを取得します。

```csharp
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
```

### ステップ 4: ファイルのプロパティを取得する

名前、説明、MIME タイプ、コントロール ハッシュ、作成日、変更日、サイズなどの添付ファイルのプロパティが表示されます。

```csharp
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

//オブジェクトパラメータに追加情報が含まれているかどうかを確認する
if (fileSpecification.Params != null)
{
Console.WriteLine("Check Hash: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}
```

### ステップ 5: 添付ファイルを取得してファイルに保存する

添付ファイルの内容を取得し、テキスト ファイルに保存します。この例では、ファイルは「test_out.txt」という名前で保存されます。

```csharp
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();
```

### Aspose.PDF for .NET を使用した個別の添付ファイルの取得のサンプル ソース コード 

```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開いた文書
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
//特定の埋め込みファイルを取得する
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
//ファイルのプロパティを取得する
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("Mime Type: {0}", fileSpecification.MIMEType);
//パラメータオブジェクトにパラメータが含まれているかどうかを確認します
if (fileSpecification.Params != null)
{
	Console.WriteLine("CheckSum: {0}",
	fileSpecification.Params.CheckSum);
	Console.WriteLine("Creation Date: {0}",
	fileSpecification.Params.CreationDate);
	Console.WriteLine("Modification Date: {0}",
	fileSpecification.Params.ModDate);
	Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}
//添付ファイルを取得してファイルまたはストリームに書き込みます
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルから個々の添付ファイルを取得する方法を説明しました。この知識を利用して、PDF ファイルから添付ファイルを抽出して保存できるようになりました。

### PDF ファイルで個別の添付ファイルを取得するための FAQ

#### Q: PDF ドキュメントから個別の添付ファイルを取得する目的は何ですか?

A: 個別の添付ファイルを取得すると、PDF 内の特定の埋め込みファイルを抽出して保存できるため、さらなる分析や操作に役立ちます。

#### Q: PDF 関連のタスクにおいてこのチュートリアルはどのように活用できますか?

A: このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントから特定の添付ファイルを取得して保存するための段階的な手順と C# ソース コードを提供します。

#### Q: このチュートリアルを使用してアクセスできる添付ファイルのプロパティは何ですか?

A: 特定の添付ファイルの名前、説明、MIME タイプ、コントロール ハッシュ、作成日、変更日、サイズなどの添付ファイルのプロパティにアクセスできます。

#### Q: 最初の添付ファイル以外の添付ファイルを取得するようにコードを変更できますか?

 A: もちろん、インデックスを調整することはできます (例:`pdfDocument.EmbeddedFiles[1]`) PDF 内の異なるインデックスで添付ファイルを取得します。

#### Q: 取得した添付ファイルをファイルに保存するにはどうすればよいですか?

A: このチュートリアルでは、添付ファイルのコンテンツを取得し、指定した名前でテキスト ファイルに保存するコードを提供します。

#### Q: 添付ファイル情報の「Check Hash」プロパティの意味は何ですか?

A: 「ハッシュの確認」プロパティは、添付ファイルの制御ハッシュ値を表し、添付ファイルの整合性を検証するために使用できます。

#### Q: この知識を拡張して、ファイル タイプなどの特定の基準で添付ファイルを抽出することはできますか?

A: はい、コードを拡張して、ファイル タイプやその他のプロパティなどの特定の基準に基づいて添付ファイルをフィルタリングすることができます。

#### Q: Aspose.PDF for .NET は、個々の添付ファイルを抽出するプロセスをどのように簡素化しますか?

A: Aspose.PDF for .NET は、PDF ドキュメント内の添付ファイルの抽出と操作を容易にするユーザーフレンドリーな API を提供します。

#### Q: このチュートリアルは、パスワードで保護された PDF ファイルにも適用されますか?

A: はい、Aspose.PDF for .NET を使用して、同様の手法を応用して、パスワードで保護された PDF ファイルから個々の添付ファイルを取得できます。
