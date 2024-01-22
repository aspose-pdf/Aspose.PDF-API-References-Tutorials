---
title: すべての添付ファイルを PDF ファイルで取得する
linktitle: すべての添付ファイルを PDF ファイルで取得する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内のすべての添付ファイルを取得する方法を学びます。簡単に操作できるステップバイステップのガイド。
type: docs
weight: 40
url: /ja/net/programming-with-attachments/get-all-the-attachments/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイル内のすべての添付ファイルを取得するために、次の C# ソース コードを段階的に説明します。

始める前に、Aspose.PDF ライブラリをインストールし、開発環境をセットアップしていることを確認してください。 C# プログラミングの基本的な知識も必要です。

### ステップ 1: ドキュメント ディレクトリのセットアップ

提供されたソース コードでは、添付ファイルを取得する PDF ファイルが配置されているディレクトリを指定する必要があります。 「dataDir」変数を目的のディレクトリに変更します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### ステップ 2: 既存の PDF ドキュメントを開く

指定されたパスを使用して既存の PDF ドキュメントを開きます。

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### ステップ 3: 添付ファイルのコレクションを取得する

ドキュメントから添付ファイルのコレクションを取得します。

```csharp
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
```

### ステップ 4: 添付ファイルを取得する

コレクションを調べてすべての添付ファイルを取得し、その情報を表示します。添付ファイルも個別のファイルに保存されます。

```csharp
int count = 1;
foreach(FileSpecification fileSpecification in embeddedFiles)
{
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

//オブジェクトパラメータに追加情報が含まれているかどうかを確認する
if (fileSpecification.Params != null)
{
Console.WriteLine("CheckSum: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}

//添付ファイルを取得してファイルに保存する
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

count += 1;
}
```


### Aspose.PDF for .NET を使用してすべての添付ファイルを取得するためのサンプル ソース コード 

```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開いた文書
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
//埋め込みファイルのコレクションを取得する
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
//埋め込まれたファイルの数を取得する
Console.WriteLine("Total files : {0}", embeddedFiles.Count);
int count = 1;
//コレクションをループしてすべての添付ファイルを取得します
foreach (FileSpecification fileSpecification in embeddedFiles)
{
	Console.WriteLine("Name: {0}", fileSpecification.Name);
	Console.WriteLine("Description: {0}",
	fileSpecification.Description);
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
	fileSpecification.Contents.Read(fileContent, 0,
	fileContent.Length);
	FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt",
	FileMode.Create);
	fileStream.Write(fileContent, 0, fileContent.Length);
	fileStream.Close();
	count+=1;
}

```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルからすべての添付ファイルを取得する方法を説明しました。この知識を利用して、PDF ファイルから添付ファイルを抽出して操作できるようになりました。

## すべての添付ファイルを PDF ファイルで取得するための FAQ

#### Q: PDF ドキュメントからすべての添付ファイルを取得する必要があるのはなぜですか?

A: 添付ファイルを取得すると、PDF 内に埋め込まれた追加ファイルにアクセスして操作できるようになり、アーカイブ、共有、またはさらなる処理に役立ちます。

#### Q: PDF ドキュメントにはどのような種類のファイルを添付できますか?

A: PDF ドキュメントには、画像、ドキュメント、スプレッドシート、音声ファイルなどを含む幅広い添付ファイルを含めることができます。

#### Q: このチュートリアルは、Aspose.PDF for .NET を使用して PDF から添付ファイルを取得するのにどのように役立ちますか?

A: このチュートリアルでは、PDF ドキュメント内のすべての添付ファイルにアクセスして取得するための段階的な手順と C# ソース コードを提供します。

#### Q: このチュートリアルを使用して、すべての添付ファイルではなく特定の添付ファイルを取得できますか?

A: はい、提供されたコードを変更して、要件に基づいて添付ファイルを選択的に取得できます。

#### Q: このチュートリアルを使用すると、各添付ファイルについてどのような情報を取得できますか?

A: このチュートリアルでは、添付ファイルの名前、説明、MIME タイプ、作成日、変更日、サイズなどの詳細を取得して表示する方法を説明します。

#### Q: このチュートリアルを使用して、取得した添付ファイルはどのように保存されますか?

A: このチュートリアルでは、取得した各添付ファイルを指定されたディレクトリに別個のファイルとして保存する方法を説明します。

#### Q: この知識を利用して、パスワードで保護された PDF ファイルから添付ファイルを抽出できますか?

A: はい、同様の原則を適用して、Aspose.PDF for .NET を使用してパスワードで保護された PDF ファイルから添付ファイルを取得できます。

#### Q: Aspose.PDF for .NET は添付ファイルの取得をどのように容易にしますか?

A: Aspose.PDF for .NET は、PDF ドキュメント内の添付ファイルに簡単にアクセスして操作できる直感的な API を提供します。

#### Q: 添付ファイルの取得が推奨される特定のシナリオはありますか?

A: 添付ファイルの取得は、画像、音声ファイル、追加ドキュメントの抽出など、PDF 内に埋め込まれたファイルにアクセスする必要がある場合に便利です。