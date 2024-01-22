---
title: PDF ファイルのブックマークのページ番号を取得する
linktitle: PDF ファイルのブックマークのページ番号を取得する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、PDF ファイル内のブックマークのページ番号を簡単に取得できます。
type: docs
weight: 60
url: /ja/net/programming-with-bookmarks/get-bookmark-page-number/
---
PDF ファイル内のブックマークに関連付けられたページ番号を取得すると、ナビゲーションに役立ちます。 Aspose.PDF for .NET を使用すると、次のソース コードに従ってブックマークのページ番号を簡単に取得できます。

## ステップ 1: 必要なライブラリをインポートする

始める前に、C# プロジェクトに必要なライブラリをインポートする必要があります。必要なインポートディレクティブは次のとおりです。

```csharp
using Aspose.Pdf.Facades;
```

## ステップ 2: ドキュメントフォルダーへのパスを設定する

この手順では、ブックマークのページ番号を抽出する PDF ファイルが含まれるフォルダーへのパスを指定する必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`次のコードでは、ドキュメント フォルダーへの実際のパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 3: ブックマークエディタを作成する

次に、`PdfBookmarkEditor`オブジェクトを使用してドキュメントのブックマークを操作します。次のコードを使用します。

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

## ステップ 4: PDF ファイルを開く

このステップでは、次のコマンドを使用して PDF ファイルを開きます。`BindPdf`ブックマークエディタのメソッド。対応するコードは次のとおりです。

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

## ステップ 5: ブックマークを抽出する

ここで、次のコマンドを使用してドキュメントからブックマークを抽出します。`ExtractBookmarks`ブックマークエディタのメソッド。対応するコードは次のとおりです。

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

## ステップ 6: ブックマークを参照してページ番号を取得する

最後に、抽出されたブックマークをループし、次のメソッドを使用して各ブックマークに関連付けられたページ番号を取得します。`foreach`ループ。対応するコードは次のとおりです。

```csharp
foreach (Bookmark bookmark in bookmarks)
{
     string strLevelSeprator = string.Empty;
     for (int i = 1; i < bookmark.Level; i++)
     {
         strLevelSeprator += "----";
     }
     Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
     Console.WriteLine("{0}Page number: {1}", strLevelSeprator, bookmark.PageNumber);
     Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

### Aspose.PDF for .NET を使用したブックマーク ページ番号の取得のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//PDFブックマークエディタの作成
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
//PDFファイルを開く
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
//ブックマークの抽出
Aspose.Pdf.Facades.Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
foreach (Aspose.Pdf.Facades.Bookmark bookmark in bookmarks)
{
	string strLevelSeprator = string.Empty;
	for (int i = 1; i < bookmark.Level; i++)
	{
		strLevelSeprator += "----";
	}
	Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
	Console.WriteLine("{0}Page Number: {1}", strLevelSeprator, bookmark.PageNumber);
	Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

## 結論

おめでとうございます！これで、Aspose.PDF for .NET を使用してブックマークのページ番号を取得するためのステップバイステップのガイドが完成しました。このコードを使用すると、PDF ドキュメント内の各ブックマークに関連付けられたナビゲーション情報を取得できます。

高度なブックマーク操作機能の詳細については、公式の Aspose.PDF ドキュメントを必ずご確認ください。

### PDF ファイルのブックマークのページ番号を取得するための FAQ

#### Q: PDF ファイルのブックマークとは何ですか?

A: PDF ファイル内のブックマークは、ユーザーが文書内の特定のセクションやページにすばやくジャンプできるようにするナビゲーション補助機能です。関連コンテンツへのショートカットを提供することで、ユーザー エクスペリエンスが向上します。

#### Q: PDF ファイルからブックマークのページ番号を取得したいのはなぜですか?

A: ブックマークのページ番号を取得すると、ユーザーがドキュメント内をより効果的に移動できるようになり、各ブックマークの行き先が明確に示されます。これは、複数のセクションを含む長い文書の場合に特に便利です。

#### Q: C# プロジェクトに必要なライブラリをインポートするにはどうすればよいですか?

A: C# プロジェクトに必要なライブラリをインポートするには、次のインポート ディレクティブを使用します。

```csharp
using Aspose.Pdf.Facades;
```

このディレクティブを使用すると、Aspose.PDF for .NET によって提供されるクラスとメソッドを利用できるようになります。

#### Q: ドキュメントフォルダーへのパスを指定するにはどうすればよいですか?

 A: 提供されたソース コードで、次の部分を置き換えます。`"YOUR DOCUMENT DIRECTORY"`ブックマークのページ番号を抽出する PDF ファイルが含まれるフォルダーへの実際のパスを置き換えます。これにより、コードはターゲット PDF ファイルを確実に見つけることができます。

#### Q: ブックマーク エディタを作成するにはどうすればよいですか?

A: ブックマーク エディタを作成するには、次のコードを使用します。

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

#### Q: PDF ファイルを開いてブックマークを操作するにはどうすればよいですか?

A: PDF ファイルを開いてブックマーク情報を抽出するには、次のコードを使用します。

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

交換する`"GetBookmarks.pdf"`実際のファイル名を付けます。

#### Q: PDF ファイルからブックマークを抽出するにはどうすればよいですか?

 A: PDF ファイルからブックマークを抽出するには、`ExtractBookmarks`ブックマークエディタのメソッド:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

#### Q: ブックマークのページ番号を取得して表示するにはどうすればよいですか?

 A: 抽出されたブックマークをループします。`foreach`ループしてアクセスします`PageNumber`各ブックマークのプロパティを使用して、関連するページ番号を取得して表示します。

```csharp
foreach (Bookmark bookmark in bookmarks)
{
    Console.WriteLine("Title: " + bookmark.Title);
    Console.WriteLine("Page Number: " + bookmark.PageNumber);
    Console.WriteLine("Page Action: " + bookmark.Action);
}
```

#### Q: この方法を使用してブックマークのプロパティを変更できますか?

 A: このチュートリアルではブックマークのページ番号を取得することに重点を置いていますが、同じプロパティを使用して他のブックマークのプロパティを変更することもできます。`Bookmark`オブジェクトと関連プロパティ。

#### Q: ブックマーク情報を抽出した後、更新された PDF ファイルを保存するにはどうすればよいですか?

A: ブックマークの抽出では、元の PDF ファイルは変更されません。変更を保存したい場合は、Aspose.PDF for .NET が提供する他の方法を使用して保存できます。