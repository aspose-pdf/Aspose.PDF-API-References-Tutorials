---
title: PDF ファイル内のテキストにツールヒントを追加する
linktitle: PDF ファイル内のテキストにツールヒントを追加する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内のテキストにツールヒントを追加する方法を学びます。情報豊富なホバー テキストを簡単に追加して PDF を強化できます。
type: docs
weight: 90
url: /ja/net/programming-with-text/add-tooltip-to-text/
---
## 導入

魅力的でインタラクティブな PDF を作成する場合、ツールヒントは非常に役立ちます。マウスを何かの上に置いたときに追加情報を提供する小さなポップアップ ボックスをご存知ですか? ドキュメントを乱雑にすることなく、コンテキスト、説明、またはちょっとしたアドバイスを提供できます。このチュートリアルでは、Aspose.PDF for .NET ライブラリを使用して PDF ファイル内のテキストにツールヒントを追加する方法について説明します。経験豊富な開発者でも、PDF の世界に足を踏み入れたばかりでも、適切な場所にいます。それでは始めましょう!

## 前提条件

コーディング部分に進む前に、スムーズに進めるために必要なものがすべて揃っていることを確認しましょう。

### Visual Studio がインストールされている
Visual Studio は .NET アプリケーションの主な開発環境となるため、マシンにインストールしておくことが不可欠です。

### Aspose.PDF for .NET ライブラリ
また、Aspose.PDFライブラリも必要です。[ここからダウンロード](https://releases.aspose.com/pdf/net/)プロジェクトの参照に必ず含めてください。

### C#の基礎知識
C# でコーディングするので、C# の経験があると非常に役立ちます。でも心配しないでください。すべての手順をガイドします!

### 作業用のPDFドキュメント
この例のように、空白の PDF ドキュメントから始めることも、必要に応じて既存のドキュメントを使用することもできます。

それでは、コーディングの部分に移りましょう。

## パッケージのインポート 

コーディングの冒険の最初のステップは、必要なパッケージをインポートすることです。Visual Studioプロジェクトを開き、C#ファイルの先頭に次のコードを追加します。`using`指令:

```csharp
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

これらのパッケージを使用すると、PDF ドキュメントの作成と操作に必要なすべてのクラスと機能にアクセスできます。

## ステップ1: ドキュメントディレクトリを設定する

まず最初に、ドキュメントを保存するパスを設定する必要があります。これは、すべての作品が保存されるファイル システム内の快適な場所を見つけることだと考えてください。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
```

必ず交換してください`YOUR DOCUMENT DIRECTORY`マシン上の実際のパスを使用します。

## ステップ2: サンプルPDFドキュメントを作成する

次に、テキストを含む簡単な PDF を作成します。ここからクリエイティブなプロセスが始まります。

```csharp
//テキストを含むサンプルドキュメントを作成する
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

この手順では、ドキュメントを作成し、2 つのテキスト フラグメントを追加して、以前に指定したパスに保存します。

## ステップ3: 処理のためにドキュメントを開く

ドキュメントが作成されたので、それを開いてツールチップを作成してみましょう。

```csharp
//テキストを含む文書を開く
Document document = new Document(outputFile);
```

ここでは、作成したドキュメントを読み込むだけです。

## ステップ4: テキスト断片を見つけるためのテキストアブソーバーを作成する

ツールチップを追加するテキストの断片を見つける必要があります。これは、虫眼鏡を使用して大きな地図の特定の部分を強調表示するようなものです。 

```csharp
//正規表現に一致するすべてのフレーズを見つけるためにTextAbsorberオブジェクトを作成します。
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorber);
```

## ステップ5: テキストフラグメントの抽出

次に、前のステップで見つかったテキストの断片を抽出します。

```csharp
//抽出されたテキストフラグメントを取得する
TextFragmentCollection textFragments = absorber.TextFragments;
```

このスニペットにより、関心のあるテキスト断片の参照を保持できるようになります。

## ステップ6: フラグメントをループしてツールチップを追加する

次は楽しい部分です。各テキスト フラグメントをループし、それぞれにツールヒントを追加します。特定のアイテム (テキスト フラグメント) の周りに小さなギフト (ツールヒント) をラッピングすることを想像してください。

```csharp
//フラグメントをループする
foreach (TextFragment fragment in textFragments)
{
	//テキストフラグメントの位置に非表示のボタンを作成する
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	//AlternateName 値はビューアアプリケーションによってツールチップとして表示されます。
	field.AlternateName = "Tooltip for text.";
	//ドキュメントにボタンフィールドを追加する
	document.Form.Add(field);
}
```

各反復で、テキスト フラグメントの位置に対応するボタン フィールドを作成し、それにツールチップ テキストを割り当てます。

## ステップ7: 長いツールチップについても繰り返します

シンプルなツールチップを追加したのと同じように、長いテキストにも同じことができます。創造性を広げましょう!

```csharp
//次は、非常に長いツールチップのサンプルです
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	//非常に長いテキストを設定する
	field.AlternateName = "Lorem ipsum dolor sit amet, consectetur adipiscing elit," +
							" sed do eiusmod tempor incididunt ut labore et dolore magna" +
							" aliqua. Ut enim ad minim veniam, quis nostrud exercitation" +
							" ullamco laboris nisi ut aliquip ex ea commodo consequat." +
							" Duis aute irure dolor in reprehenderit in voluptate velit" +
							" esse cillum dolore eu fugiat nulla pariatur. Excepteur sint" +
							" occaecat cupidatat non proident, sunt in culpa qui officia" +
							" deserunt mollit anim id est laborum.";
	document.Form.Add(field);
}
```

ここでは、以前と同じ種類の作業を行っていますが、ツールチップははるかに拡張されています。

## ステップ8: ドキュメントを保存する

最後のステップは、新しいツールチップをすべて含めてドキュメントを保存することです。 

```csharp
//ドキュメントを保存
document.Save(outputFile);
```

これで完了です。PDF にツールヒントが追加され、よりユーザーフレンドリーでインタラクティブになりました。

## 結論

以上が、Aspose.PDF for .NET を使用して PDF ファイル内のテキストにツールヒントを追加する方法に関するわかりやすいガイドです。この手法により、ユーザー エクスペリエンスが大幅に向上し、一度に大量のテキストを表示して読者を圧倒することなく、ドキュメントの情報を充実させることができます。 

単語やフレーズにマウスを合わせるだけで、読者は混乱することなく価値ある関連情報を得ることができます。ぜひ腕まくりして試してみてください。あっという間に、目を引く魅力的なドキュメントをいろいろ作成できるでしょう。

## よくある質問

### Aspose.PDF for .NET とは何ですか?
Aspose.PDF for .NET は、開発者が .NET アプリケーションで PDF ドキュメントを作成、操作、変換できるようにするライブラリです。

### Aspose.PDF を無料で使用できますか?
はい、Asposeでは機能を試すための無料トライアルを提供しています。[ここ](https://releases.aspose.com/).

### Aspose.PDF には利用できるライセンス オプションはありますか?
はい、ライセンスを購入するか、一時ライセンスを取得できます。オプションを確認してください[ここ](https://purchase.aspose.com/).

### Aspose.PDF を使用してツールヒント以外のインタラクティブな要素を追加できますか?
もちろんです! Aspose.PDF では、ハイパーリンク、ボタン、フォームなどのさまざまなインタラクティブ要素を追加できます。

### Aspose.PDF に関する詳細なドキュメントはどこで入手できますか?
ドキュメントをご覧ください[ここ](https://reference.aspose.com/pdf/net/)より詳しいガイダンスについては、こちらをご覧ください。