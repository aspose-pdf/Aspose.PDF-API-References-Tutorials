---
title: 単語を消す
linktitle: 単語を消す
second_title: Aspose.PDF for .NET API リファレンス
description: この包括的なステップバイステップ ガイドでは、Aspose.PDF for .NET を使用して PDF 内の単語を取り消す方法を学習します。ドキュメント編集スキルを向上させます。
type: docs
weight: 150
url: /ja/net/annotations/strikeoutwords/
---
## 導入

PDF 内の特定のテキストを取り消し線で強調する必要に迫られたことはありませんか? ドキュメントをレビューしたり、テキストにマークを付けたり、特定のセクションを強調表示したりする場合、単語を取り消し線で強調表示することは便利なツールです。このチュートリアルでは、Aspose.PDF for .NET を使用してそれを実行する方法について説明します。この包括的なガイドでは、各手順を順を追って説明し、この機能を .NET アプリケーションに効果的に実装するために必要なすべての情報を提供します。 

## 前提条件

コードに進む前に、このチュートリアルを進めるために満たす必要のある前提条件がいくつかあります。

1.  Aspose.PDF for .NETライブラリ: Aspose.PDF for .NETライブラリがインストールされていることを確認してください。[ここからダウンロード](https://releases.aspose.com/pdf/net/).

2. .NET Framework: マシンに .NET Framework がインストールされていることを確認してください。このチュートリアルは、.NET アプリケーション向けに設計されています。

3. 開発環境: コードを記述して実行するには、Visual Studio などの IDE が必要です。

4. PDF ドキュメント: 作業に使用するサンプル PDF ファイルを用意します。これがテキストを取り消し線で消すドキュメントになります。

5. 基本的な C# の知識: このチュートリアルの手順を理解して実装するには、C# プログラミングの知識が必要です。

## パッケージのインポート

コーディングを開始する前に、.NET プロジェクトに必要な名前空間をインポートする必要があります。これにより、Aspose.PDF を使用して PDF ファイルを操作するために必要なクラスとメソッドにアクセスできるようになります。

```csharp
using System;
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

これらの名前空間は、PDF ドキュメントの操作、テキストの処理、取り消し線などの注釈の追加に不可欠です。

このセクションでは、PDF ドキュメント内の単語を取り消すプロセスを、シンプルで扱いやすいステップに分解します。各ステップには詳細な説明が付いており、すべての仕組みを理解できるようになります。

## ステップ1: PDFドキュメントを読み込む

最初のステップは、編集する PDF ドキュメントを読み込むことです。このドキュメントでは、特定の単語やフレーズを取り消すことになります。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF文書を開く
Document document = new Document(dataDir + "input.pdf");
```

- `dataDir` この変数はドキュメントディレクトリへのパスを保持します。`"YOUR DOCUMENT DIRECTORY"` PDF ファイルが保存されている実際のパスを入力します。
- `Document` : の`Document`クラスは PDF ドキュメントを表します。ファイル パスをコンストラクターに渡すことで、PDF ファイルを処理用に開きます。

## ステップ2: 特定のテキストを見つけるためのTextFragment Absorberを作成する

次に、インスタンスを作成します`TextFragmentAbsorber`PDF ドキュメント内の特定のテキスト部分を検索します。これにより、取り消し線を引くテキストを見つけることができます。

```csharp
//特定のテキストフラグメントを検索するための TextFragment Absorber インスタンスを作成する
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

- `TextFragmentAbsorber`このクラスは、PDF ドキュメント内の特定のテキスト フラグメントを検索して操作するために使用されます。この例では、「Estoque」という単語を検索しています。「Estoque」をドキュメント内で検索する単語またはフレーズに置き換えます。

## ステップ3: PDFドキュメントのページを反復処理する

今、私たちは`TextFragmentAbsorber`指定されたテキストを見つけるには、PDF ドキュメントの各ページを反復処理する必要があります。

```csharp
// PDF文書のページを反復処理する
for (int i = 1; i <= document.Pages.Count; i++)
{
    //PDF文書の現在のページを取得する
    Page page = document.Pages[i];
    page.Accept(textFragmentAbsorber);
}
```

- `for (int i = 1; i <= document.Pages.Count; i++)`このループは PDF ドキュメントの各ページを反復処理します。
- `document.Pages[i]`: 現在処理中のページを取得します。
- `page.Accept(textFragmentAbsorber)` : この方法は、`TextFragmentAbsorber`現在のページに移動し、指定されたテキストを検索します。

## ステップ4: テキストフラグメントを収集して処理する

ページを反復処理した後、見つかったテキストの断片を収集し、さらに処理できるように準備します。

```csharp
//吸収されたテキスト断片のコレクションを作成する
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- `TextFragmentCollection`このコレクションには、ドキュメント内で見つかったすべてのテキスト フラグメントが格納されます。次の手順でこのコレクションを使用して、テキストを取り消します。

## ステップ5: テキストフラグメントを反復処理して取り消し線を引く

このステップでは、コレクション内の各テキスト フラグメントをループし、取り消し線の注釈を適用します。

```csharp
//テキストフラグメントのコレクションを反復処理する
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

    //TextFragmentオブジェクトの長方形の寸法を取得します
    Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
        (float)textFragment.Position.XIndent,
        (float)textFragment.Position.YIndent,
        (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width,
        (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

    //StrikeOut Annotationインスタンスをインスタンス化する
    StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);

    //取り消し線注釈のプロパティを設定する
    strikeOut.Opacity = .80f;
    strikeOut.Border = new Border(strikeOut);
    strikeOut.Color = Aspose.Pdf.Color.Red;

    //テキストフラグメントのページの注釈コレクションに注釈を追加します
    textFragment.Page.Annotations.Add(strikeOut);
}
```

- `TextFragment textFragment = textFragmentCollection[j]`この行は現在のテキストフラグメントを取得します。
- `Aspose.Pdf.Rectangle`: テキスト フラグメントの長方形の寸法を計算して、取り消し線を適用する場所を決定します。
- `StrikeOutAnnotation`: このクラスは取り消し線注釈を表します。計算された四角形と現在のページを使用してインスタンス化します。
- `strikeOut.Opacity`: このプロパティは取り消し線の不透明度を設定し、80% 表示されるようにします。
- `strikeOut.Color`取り消し線の色を赤に設定しましたが、お好みの色に変更できます。
- `textFragment.Page.Annotations.Add(strikeOut)`: ページに取り消し線注釈が追加されます。

## ステップ6: 変更したPDF文書を保存する

最後の手順は、取り消し線を適用した変更済みの PDF ドキュメントを保存することです。

```csharp
//更新されたPDF文書を保存する
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

- `dataDir + "StrikeOutWords_out.pdf"`: 変更されたドキュメントに新しいファイル名が作成されます。元のファイルは変更されません。
- `document.Save(dataDir)`: 取り消し線付きの PDF 文書を指定した場所に保存します。

## 結論

おめでとうございます! Aspose.PDF for .NET を使用して、PDF ドキュメント内の特定の単語を取り消すことができました。このステップ バイ ステップ ガイドに従うことで、テキストを強調表示したり取り消したりして PDF ドキュメントをカスタマイズし、より動的に、ニーズに合わせてカスタマイズできるようになります。法的文書に注釈を付ける場合、レポートを準備する場合、またはレビュー用にテキストにマークアップする場合など、このチュートリアルでは、これらを効率的に行うためのスキルを身に付けることができます。

## よくある質問

### 取り消し線の色を変更できますか?

はい、色を変更するには、`strikeOut.Color`プロパティを設定します。例えば、次のように設定します。`Aspose.Pdf.Color.Blue`青い三振。

### 一度に複数の単語を取り消すことは可能ですか?

絶対に！`TextFragmentAbsorber`文書内の任意の単語やフレーズを検索するために使用できます。`TextFragmentCollection`.

### 特定のページのテキストのみを取り消し線で消したい場合はどうすればよいでしょうか?

ページを反復するループを変更して、変更したいページだけを含めることができます。たとえば、`for (int i = 1; i <= 3; i++)`最初の 3 ページにのみ取り消し線が適用されます。

### 取り消し線の太さを調整するにはどうすればよいですか?

取り消し線の太さは、`Border`の財産`StrikeOutAnnotation`これにより、取り消し線の外観をカスタマイズできます。

### 文書を保存した後に取り消し線を元に戻す方法はありますか?

文書を保存すると、取り消し線は永続的になります。取り消し線のない元のテキストを保持する必要がある場合は、変更を適用する前に元の文書のバックアップを保存することを検討してください。