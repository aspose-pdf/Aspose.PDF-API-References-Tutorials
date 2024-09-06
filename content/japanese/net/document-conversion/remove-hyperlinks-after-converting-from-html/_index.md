---
title: HTML から変換した後ハイパーリンクを削除する
linktitle: HTML から変換した後ハイパーリンクを削除する
second_title: Aspose.PDF for .NET API リファレンス
description: このステップバイステップ ガイドでは、Aspose.PDF for .NET を使用して PDF に変換した後、HTML ドキュメントからハイパーリンクを削除する方法を学習します。
type: docs
weight: 250
url: /ja/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
## 導入

デジタル時代では、HTML ドキュメントを PDF に変換することは一般的な作業です。ただし、読みやすさの向上や不要なナビゲーションの防止など、さまざまな理由から、変換された PDF からハイパーリンクを削除したい場合があります。このチュートリアルでは、Aspose.PDF for .NET を使用してこれを実現する方法について説明します。 

## 前提条件

コードに進む前に、次の前提条件を満たしていることを確認してください。

1. Visual Studio: マシンに Visual Studio がインストールされていることを確認してください。これが開発環境になります。
2.  Aspose.PDF for .NET: Aspose.PDFライブラリが必要です。ダウンロードはこちらから[ここ](https://releases.aspose.com/pdf/net/).
3. C# の基礎知識: C# プログラミングに精通していると、コードをよりよく理解できるようになります。

## パッケージのインポート

まず、C# プロジェクトに必要なパッケージをインポートする必要があります。手順は次のとおりです。

1. Visual Studio プロジェクトを開きます。
2. ソリューション エクスプローラーでプロジェクトを右クリックし、[NuGet パッケージの管理] を選択します。
3. 検索する`Aspose.PDF`インストールしてください。

```csharp
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
using System.IO;
```

これですべての設定が完了したので、HTML ファイルを PDF に変換した後にハイパーリンクを削除するプロセスを詳しく説明します。

## ステップ1: ドキュメントディレクトリを設定する

まず最初に、ドキュメント ディレクトリへのパスを指定する必要があります。これは HTML ファイルが保存される場所であり、出力 PDF が保存される場所です。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

交換する`"YOUR DOCUMENT DIRECTORY"` HTML ファイルが保存されている実際のパスを入力します。

## ステップ2: HTMLドキュメントを読み込む

次に、HTML文書をロードします。`Document` Aspose.PDF のクラス。このクラスを使用すると、PDF ドキュメントを簡単に操作できます。

```csharp
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
```

ここでは、次のHTMLファイルをロードしています。`SampleHtmlFile.html`指定したディレクトリにこのファイルが存在することを確認してください。

## ステップ3: ドキュメントをメモリストリームに保存する

注釈の処理を開始する前に、ドキュメントをメモリ ストリームに保存する必要があります。この手順は、ドキュメントをさらに操作できるように準備するため、非常に重要です。

```csharp
doc.Save(new MemoryStream());
```

この行はドキュメントをメモリに保存し、まだディスクに書き込まなくても操作できるようにします。

## ステップ4: 注釈を反復処理する

ここで、ドキュメント内の注釈を反復処理します。注釈は、リンク、コメント、ハイライトなどの要素です。ここでは、特にリンク注釈に注目します。

```csharp
foreach (Annotation a in doc.Pages[1].Annotations)
{
    if (a.AnnotationType == AnnotationType.Link)
    {
        //リンク注釈を処理する
    }
}
```

このループでは、注釈タイプがリンクであるかどうかを確認します。リンクである場合は、次の手順に進みます。

## ステップ5: ハイパーリンクアクションを削除する

各リンク注釈について、ハイパーリンク アクションがあるかどうかを確認する必要があります。ハイパーリンク アクションがある場合は、URI を空の文字列に設定してハイパーリンクを削除します。

```csharp
LinkAnnotation la = (LinkAnnotation)a;
if (la.Action is GoToURIAction)
{
    GoToURIAction gta = (GoToURIAction)la.Action;
    gta.URI = "";
```

このコード スニペットにより、ハイパーリンク アクションが効果的に削除されます。

## ステップ6: テキストの断片を吸収する

次に、リンク注釈に関連付けられたテキストフラグメントを吸収します。これにより、テキストの外観を操作できるようになります。

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
doc.Pages[a.PageIndex].Accept(tfa);
```

ここでは、`TextFragmentAbsorber`検索オプションを注釈の四角形に設定します。これにより、リンクされたテキストを見つけやすくなります。

## ステップ7: テキストの外観を変更する

テキストフラグメントを取得したら、その外観を変更できます。この場合、下線を削除し、テキストの色を黒に変更します。

```csharp
foreach (TextFragment tf in tfa.TextFragments)
{
    tf.TextState.Underline = false;
    tf.TextState.ForegroundColor = Color.Black;
}
```

この手順では、ハイパーリンクのスタイルを削除することでテキストの読みやすさが向上します。

## ステップ8: 注釈を削除する

テキストを変更した後、ドキュメントからリンク注釈を安全に削除できます。

```csharp
doc.Pages[a.PageIndex].Annotations.Delete(a);
}
```

この行は PDF からハイパーリンクを削除し、最終出力にハイパーリンクが存在しないようにするものです。

## ステップ9: 変更したドキュメントを保存する

最後に、変更したドキュメントを新しい PDF ファイルに保存する必要があります。これがプロセスの最後のステップです。

```csharp
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

この行はハイパーリンクを削除した文書を保存し、新しいPDFファイルを作成します。`RemoveHyperlinksFromText_out.pdf`.

## 結論

これで完了です。Aspose.PDF for .NET を使用して HTML ドキュメントを PDF に変換した後、ハイパーリンクを正常に削除できました。このプロセスにより、PDF の読みやすさが向上するだけでなく、表示するコンテンツを制御できるようになります。 

## よくある質問

### PDF ドキュメントからハイパーリンクを削除できますか?
はい、Aspose.PDF for .NET を使用して、任意の PDF ドキュメントからハイパーリンクを削除できます。

### Aspose.PDF は無料で使用できますか?
 Aspose.PDFは無料トライアルを提供していますが、フル機能を使用するにはライセンスを購入する必要があります。[購入ページ](https://purchase.aspose.com/buy).

### Aspose.PDF の使用中に問題が発生した場合はどうすればよいですか?
ヘルプが必要な場合は、[サポートフォーラム](https://forum.aspose.com/c/pdf/10).

### Aspose を使用して他のファイル形式を PDF に変換できますか?
はい、Aspose は PDF への変換にさまざまなファイル形式をサポートしています。

### Aspose.PDF for .NET はどこからダウンロードできますか?
ダウンロードはこちらから[ダウンロードリンク](https://releases.aspose.com/pdf/net/).