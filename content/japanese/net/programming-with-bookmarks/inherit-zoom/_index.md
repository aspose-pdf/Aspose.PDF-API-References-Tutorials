---
title: PDF ファイルを拡大して継承
linktitle: PDF ファイルを拡大して継承
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、PDF ファイルのブックマーク ズームを簡単に継承できます。
type: docs
weight: 90
url: /ja/net/programming-with-bookmarks/inherit-zoom/
---
PDF ファイルのズーム継承により、ブックマークのデフォルトのズーム レベルを指定できます。 Aspose.PDF for .NET を使用すると、次のソース コードに従ってズームを簡単に継承できます。

## ステップ 1: 必要なライブラリをインポートする

始める前に、C# プロジェクトに必要なライブラリをインポートする必要があります。必要なインポートディレクティブは次のとおりです。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## ステップ 2: ドキュメントフォルダーへのパスを設定する

このステップでは、ズームを継承する PDF ファイルが含まれるフォルダーへのパスを指定する必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`次のコードでは、ドキュメント フォルダーへの実際のパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 3: PDF ドキュメントを開く

次に、次のコードを使用して、ズームを継承する PDF ドキュメントを開きます。

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## ステップ 4: ブックマーク コレクションを取得する

このステップでは、ドキュメントのブックマークまたはランドマークのコレクションを取得します。`Outlines`の財産`doc`物体。対応するコードは次のとおりです。

```csharp
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
```

## ステップ 5: ズームレベルを設定する

次に、`XYZExplicitDestination`指定された x、y、z 座標を持つオブジェクト。ここでは、ズーム 2 で座標 (100, 100, 0) を使用します。対応するコードは次のとおりです。

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

## ステップ 6: ズーム レベルをブックマークに追加する

このステップでは、`XYZExplicitDestination`のブックマークに対するアクションとしてオブジェクトを追加します。`item`コレクション。対応するコードは次のとおりです。

```csharp
item. Action = new GoToAction(dest);
```

## ステップ 7: 更新されたブックマークをドキュメントに追加する

最後に、更新されたブックマークをドキュメントのブックマーク コレクションに追加します。`Add`の方法`doc.Outlines`物体。対応するコードは次のとおりです。

```csharp
doc. Outlines. Add(item);
```

## ステップ 8: 更新されたファイルを保存する

次に、更新された PDF ファイルを保存しましょう。`Save`の方法`doc`物体。対応するコードは次のとおりです。

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

### Aspose.PDF for .NET を使用した Inherit Zoom のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開いた文書
Document doc = new Document(dataDir + "input.pdf");
//PDFファイルのアウトライン/ブックマーク集を取得
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
//ズームレベルを0に設定します
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
//XYZExplicitDestination を PDF のアウトライン コレクションにアクションとして追加します
item.Action = new GoToAction(dest);
//PDF ファイルのアウトライン コレクションに項目を追加します
doc.Outlines.Add(item);
dataDir = dataDir + "InheritZoom_out.pdf";
//出力の保存
doc.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## 結論

おめでとうございます！これで、Aspose.PDF for .NET で Zoom を継承するためのステップバイステップ ガイドが完成しました。このコードを使用して、PDF ドキュメント内のブックマークのデフォルトのズーム レベルを指定できます。

高度なブックマーク操作機能の詳細については、公式の Aspose.PDF ドキュメントを必ずご確認ください。

### PDF ファイルのズーム継承に関する FAQ

#### Q: PDF ファイルのズーム継承とは何ですか?

A: ズームの継承とは、PDF ドキュメント内のブックマークのデフォルトのズーム レベルを指定する機能を指します。これにより、ユーザーがブックマークを操作する際に、一貫性のあるユーザーフレンドリーなナビゲーションが可能になります。

#### Q: ブックマークのズーム レベルを継承したいのはなぜですか?

A: ズーム レベルを継承すると、ユーザーは PDF ドキュメント内のブックマーク間を移動する際に一貫した表示エクスペリエンスを得ることができます。これは、ドキュメントのさまざまなセクションに特定のビューを提供する場合に特に便利です。

#### Q: C# プロジェクトに必要なライブラリをインポートするにはどうすればよいですか?

A: C# プロジェクトに必要なライブラリをインポートするには、次のインポート ディレクティブを含めます。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

これらのディレクティブを使用すると、PDF ドキュメントとブックマークを操作するために必要なクラスとメソッドにアクセスできます。

#### Q: ドキュメントフォルダーへのパスを指定するにはどうすればよいですか?

 A: 提供されたソース コードで、次の部分を置き換えます。`"YOUR DOCUMENT DIRECTORY"`ズーム レベルを継承する PDF ファイルを含むフォルダーへの実際のパスを置き換えます。

#### Q: PDF ドキュメントを開いてズーム レベルを継承するにはどうすればよいですか?

A: ズーム レベルを継承するために PDF ドキュメントを開くには、次のコードを使用します。

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

交換する`"input.pdf"`実際のファイル名を付けます。

#### Q: ブックマークのズーム レベルを設定するにはどうすればよいですか?

 A: ズーム レベルを設定するには、`XYZExplicitDestination`目的の座標とズーム率を持つオブジェクトを選択します。以下に例を示します。

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

これにより、座標 (100, 100) でズーム レベルが 2 に設定されます。

#### Q: ズーム レベルをブックマークに追加するにはどうすればよいですか?

 A: を追加します。`XYZExplicitDestination`オブジェクトをブックマーク コレクションへのアクションとして使用します。

```csharp
item.Action = new GoToAction(dest);
```

どこ`item`です`OutlineItemCollection`ブックマークを表します。

#### Q: 更新された PDF ファイルを保存するにはどうすればよいですか?

 A: 更新された PDF ファイルを保存するには、`Save`の方法`doc`物体：

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

#### Q: さまざまなブックマークのズーム レベルをカスタマイズできますか?

 A: はい、複数のブックマークを作成することで、さまざまなブックマークのズーム レベルをカスタマイズできます。`XYZExplicitDestination`異なる座標とズーム率を持つオブジェクト。

#### Q: ズーム継承を適用できるブックマークの数に制限はありますか?

A: 通常、ズーム継承を適用できるブックマークの数に厳密な制限はありません。ただし、過剰な数のブックマークを含む非常に大きなドキュメントの場合は、効率的なメモリ管理が必要になる場合があります。

#### Q: ズーム継承が適用されていることを確認するにはどうすればよいですか?

A: 生成された PDF ファイルを開いて、指定したズーム レベルがブックマークに継承されていることを確認します。