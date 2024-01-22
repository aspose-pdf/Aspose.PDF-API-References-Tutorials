---
title: PDF ファイル内の強調表示されたテキストを抽出する
linktitle: PDF ファイル内の強調表示されたテキストを抽出する
second_title: Aspose.PDF for .NET API リファレンス
description: このステップバイステップのガイドでは、Aspose.PDF for .NET を使用して PDF ファイル内の強調表示されたテキストを抽出する方法を学びます。
type: docs
weight: 60
url: /ja/net/annotations/extracthighlightedtext/
---
PDF ファイル内の強調表示されたテキストを抽出するには、Aspose.PDF for .NET API を使用できます。この API は、ドキュメント内で強調表示されているすべてのテキストを取得する簡単な方法を提供します。

## ステップ 1: PDF ドキュメントをロードする

PDF ファイル内の強調表示されたテキストを抽出する最初のステップは、Aspose.PDF for .NET API を使用してドキュメントをロードすることです。これを行うには、`Document`クラスを作成し、PDF ドキュメントへのパスをパラメータとして渡します。 

```csharp
//ドキュメントディレクトリへのパス。
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

## ステップ 2: すべての注釈をループする

次のステップでは、PDF ドキュメント内のすべての注釈をループします。これを行うには、`foreach`次のようにループします。

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	//ここにコードが入ります
}
```

## ステップ 3: テキスト マークアップの注釈をフィルタリングする

内部`foreach`ループを実行するには、テキスト マークアップ注釈ではないすべての注釈をフィルターで除外する必要があります。これを行うには、注釈が`TextMarkupAnnotation`クラス。

```csharp
if (annotation is TextMarkupAnnotation)
{
	//ここにコードが入ります
}
```

## ステップ 4: ハイライトされたテキストの断片を取得する

すべてのテキスト マークアップ注釈をフィルターで除外すると、各注釈の強調表示されたテキスト フラグメントを取得できます。これを行うには、`GetMarkedTextFragments()`のメソッド`TextMarkupAnnotation`物体。

```csharp
TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
```

## ステップ 5: ハイライトされたテキストを表示する

最後に、強調表示されたテキストをユーザーに表示できます。それぞれをループすることでこれを行うことができます`TextFragment`のオブジェクト`TextFragmentCollection`そして、`Text`財産。

```csharp
foreach (TextFragment tf in collection)
{
	Console.WriteLine(tf.Text);
}
```

### Aspose.PDF for .NET を使用して強調表示されたテキストを抽出するソース コードの例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");

foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	if (annotation is TextMarkupAnnotation)
	{
		TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
		TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
		foreach (TextFragment tf in collection)
		{
			Console.WriteLine(tf.Text);
		}
	}
}
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントから強調表示されたテキストを抽出する方法を検討しました。ステップバイステップのガイドに従い、提供されている C# ソース コードを使用することで、開発者は PDF ドキュメント内の強調表示されたテキストを簡単に抽出して管理できます。

### PDF ファイル内の強調表示されたテキストを抽出するための FAQ

#### Q: PDF ドキュメント内のテキスト マークアップ注釈とは何ですか?

A: テキスト マークアップ注釈は、PDF ドキュメント内の特定のテキストを強調表示またはマークする注釈です。テキスト マークアップの注釈の例には、ハイライト、下線、取り消し線などがあります。

#### Q: Aspose.PDF for .NET を使用して、他のタイプの注釈からテキストを抽出できますか?

A: はい、Aspose.PDF for .NET は、テキスト マークアップ注釈、フリー テキスト注釈など、さまざまな種類の注釈からテキストを抽出するためのさまざまな方法を提供します。

#### Q: Aspose.PDF for .NET は、パスワードで保護された PDF ファイルからのテキストの抽出をサポートしていますか?

 A: はい、Aspose.PDF for .NET は、パスワードで保護された PDF ファイルからのテキストの抽出をサポートしています。を使用して PDF ドキュメントをロードするときは、正しいパスワードを入力する必要があります。`Document`クラス。

#### Q: 色や作成者などの他の基準に基づいて、強調表示されたテキストをフィルタリングできますか?

A: はい、色、作成者、作成日などの他の条件に基づいて、強調表示されたテキストをフィルターできます。 Aspose.PDF for .NET は、注釈にアクセスし、そのプロパティに基づいて注釈をフィルタリングするメソッドを提供します。

#### Q: 抽出した強調表示されたテキストを別のファイルに保存することはできますか?

A: はい、抽出した強調表示されたテキストを別のファイルに保存したり、さらなる処理や分析のためにデータ構造に保存したりできます。
