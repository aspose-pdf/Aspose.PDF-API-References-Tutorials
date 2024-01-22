---
title: PDF ファイルのブックマークを展開する
linktitle: PDF ファイルのブックマークを展開する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、PDF ファイル内のブックマークを簡単に展開してナビゲーションを改善できます。
type: docs
weight: 50
url: /ja/net/programming-with-bookmarks/expand-bookmarks/
---
PDF ファイル内のブックマークを展開すると、デフォルトで開いているブックマークがすべて表示されます。 Aspose.PDF for .NET を使用すると、次のソース コードに従ってブックマークを簡単に展開できます。

## ステップ 1: 必要なライブラリをインポートする

始める前に、C# プロジェクトに必要なライブラリをインポートする必要があります。必要なインポートディレクティブは次のとおりです。

```csharp
using Aspose.Pdf;
```

## ステップ 2: ドキュメントフォルダーへのパスを設定する

この手順では、ブックマークを展開する PDF ファイルが含まれるフォルダーへのパスを指定する必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`次のコードでは、ドキュメント フォルダーへの実際のパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 3: PDF ドキュメントを開く

次に、次のコードを使用して、ブックマークを展開する PDF ドキュメントを開きます。

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## ステップ 4: ページ表示モードを設定する

このステップでは、デフォルトでブックマークを表示するようにページ表示モードを設定します。私たちが使用するのは、`PageMode`の財産`doc`オブジェクトを使用して、目的のページ モードを設定します。対応するコードは次のとおりです。

```csharp
doc.PageMode = PageMode.UseOutlines;
```

## ステップ 5: ブックマークを参照して展開します。

次に、ドキュメントのブックマーク コレクション内の各ブックマーク項目をループし、各項目の開いた状態を次のように設定します。`true`デフォルトで展開します。対応するコードは次のとおりです。

```csharp
foreach(OutlineItemCollection item in doc.Outlines)
{
     item. Open = true;
}
```

## ステップ 6: 更新されたファイルを保存する

最後に、更新された PDF ファイルを次のコマンドを使用して保存します。`Save`の方法`doc`物体。対応するコードは次のとおりです。

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

### Aspose.PDF for .NET を使用したブックマークの展開のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開いた文書
Document doc = new Document(dataDir + "input.pdf");
//ページ表示モードを設定します。つまり、サムネイルを表示、全画面表示、添付パネルを表示します。
doc.PageMode = PageMode.UseOutlines;
// PDF ファイルのアウトライン コレクション内の各 Ouline アイテムを参照します。
foreach (OutlineItemCollection item in doc.Outlines)
{
	//アウトラインアイテムのオープンステータスを設定する
	item.Open = true;
}
dataDir = dataDir + "ExpandBookmarks_out.pdf";
//出力の保存
doc.Save(dataDir);
Console.WriteLine("\nBookmarks expanded successfully.\nFile saved at " + dataDir);
```

## 結論

おめでとうございます！これで、Aspose.PDF for .NET を使用してブックマークを開発するためのステップバイステップ ガイドが完成しました。このコードを使用すると、PDF ドキュメント内のすべてのデフォルトのブックマークを表示できます。

高度なブックマーク操作機能の詳細については、公式の Aspose.PDF ドキュメントを必ずご確認ください。

### PDF ファイルのブックマークの展開に関する FAQ

#### Q: PDF ファイルのブックマークとは何ですか?

A: PDF ファイル内のブックマークは、ユーザーが文書内の特定のセクションやページにすばやくジャンプできるようにするナビゲーション補助機能です。これらは、ドキュメントのさまざまな部分にアクセスするための便利な方法を提供します。

#### Q: PDF ファイル内のブックマークを展開したいのはなぜですか?

A: ブックマークを展開すると、デフォルトですべてのブックマークが展開された状態で表示されるため、ユーザー エクスペリエンスが向上します。これにより、ユーザーはドキュメントの構造の概要が明確になり、別のセクションに簡単に移動できるようになります。

#### Q: C# プロジェクトに必要なライブラリをインポートするにはどうすればよいですか?

A: C# プロジェクトに必要なライブラリをインポートするには、次のインポート ディレクティブを使用します。

```csharp
using Aspose.Pdf;
```

このディレクティブを使用すると、Aspose.PDF for .NET によって提供されるクラスとメソッドを利用できるようになります。

#### Q: ドキュメントフォルダーへのパスを指定するにはどうすればよいですか?

 A: 提供されたソース コードで、次の部分を置き換えます。`"YOUR DOCUMENT DIRECTORY"`作業する PDF ファイルが含まれるフォルダーへの実際のパスを置き換えます。これにより、コードはターゲット PDF ファイルを確実に見つけることができます。

#### Q: PDF ドキュメントを開いてブックマークを展開するにはどうすればよいですか?

A: PDF ドキュメントを開いてブックマークを展開するには、次のコードを使用します。

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

交換する`"input.pdf"`実際のファイル名を付けます。

#### Q: デフォルトでブックマークを表示するようにページ表示モードを設定するにはどうすればよいですか?

A: デフォルトでブックマークを表示するようにページ表示モードを設定するには、`PageMode`の財産`doc`物体：

```csharp
doc.PageMode = PageMode.UseOutlines;
```

#### Q: PDF ドキュメント内のすべてのブックマークを展開するにはどうすればよいですか?

 A: すべてのブックマークを展開するには、ドキュメントのアウトライン コレクション内の各ブックマーク項目をループして、`Open`財産を`true`:

```csharp
foreach (OutlineItemCollection item in doc.Outlines)
{
    item.Open = true;
}
```

#### Q: ブックマークにネストされた子ブックマークがある場合はどうなりますか?

A: ブックマークにネストされた子ブックマークがある場合、親ブックマークを展開すると子ブックマークも展開され、ドキュメントの構造を包括的に表示できます。

#### Q: ブックマークを展開した後、更新された PDF ファイルを保存するにはどうすればよいですか?

A: ブックマークを展開した後に更新された PDF ファイルを保存するには、次のコードを使用します。

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

#### Q: 展開されたブックマークの外観をカスタマイズできますか?

A: このチュートリアルではデフォルトでブックマークを展開することに重点を置いていますが、Aspose.PDF の他の機能とプロパティを使用してブックマークの外観をカスタマイズできます。