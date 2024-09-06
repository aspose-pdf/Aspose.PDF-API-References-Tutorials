---
title: PDF ファイル内の隠しテキスト ブロック
linktitle: PDF ファイル内の隠しテキスト ブロック
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルに隠しテキスト ブロックを作成する方法を学習します。
type: docs
weight: 230
url: /ja/net/programming-with-text/hidden-text-block/
---
このチュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ファイルに隠しテキスト ブロックを作成する方法を説明します。隠しテキスト ブロックは、マウス カーソルを特定の領域に置いたときに表示されるフローティング テキストです。提供されている C# ソース コードを使用して、隠しテキスト ブロックを作成する手順を順を追って説明します。

## 要件

始める前に、次のものがあることを確認してください。

- Aspose.PDF for .NET ライブラリがインストールされました。
- C# プログラミングの基本的な理解。

## ステップ1: ドキュメントディレクトリを設定する

まず、生成されたPDFファイルを保存するディレクトリへのパスを設定する必要があります。`"YOUR DOCUMENT DIRECTORY"`の`dataDir`目的のディレクトリへのパスを含む変数。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: サンプルドキュメントを作成する

この手順では、サンプル PDF ドキュメントを作成し、それにテキスト フラグメントを追加します。テキスト フラグメントは、非表示のテキスト ブロックを表示するためのトリガーとして機能します。

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## ステップ3: ドキュメントを開く

さて、先ほど作成した文書を`Document`クラス。

```csharp
Document document = new Document(outputFile);
```

## ステップ4: テキストフラグメントを見つける

私たちは`TextFragmentAbsorber`オブジェクトを使用して、非表示のテキスト ブロックの表示をトリガーするテキスト フラグメントを検索します。この場合、「フローティング テキストを表示するには、マウス カーソルをここに移動してください」という正確なテキストを検索します。

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## ステップ5: 隠しテキストフィールドを作成する

私たちは`TextBoxField`隠しテキスト フィールドを表すオブジェクト。このフィールドには、マウス カーソルをトリガー テキストの上に置いたときに表示されるテキストが含まれます。

```csharp
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
floatingField.Value = "This is the \"floating text field\".";
floatingField. ReadOnly = true;
floatingField.Flags |= AnnotationFlags.Hidden;
floatingField.PartialName = "FloatingField_1";
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField. Multiline = true;
```

## ステップ6: ドキュメントに隠しテキストフィールドを追加する

隠しテキスト フィールドをドキュメントのフォーム コレクションに追加します。

```csharp
document.Form.Add(floatingField);
```

## ステップ7: 非表示ボタンを作成する

トリガー テキスト フラグメントの上に配置された非表示のボタン フィールドを作成します。このボタン フィールドには、マウスのエンター イベントとエグジット イベントに関連付けられたアクションが設定されます。

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## ステップ8: ドキュメントを保存する

最後に、隠しテキスト ブロックを含む変更されたドキュメントを保存します。

```csharp
document. Save(outputFile);
```

### Aspose.PDF for .NET を使用した隠しテキスト ブロックのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
//テキストを含むサンプルドキュメントを作成する
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
//テキストを含む文書を開く
Document document = new Document(outputFile);
//正規表現に一致するすべてのフレーズを見つけるためにTextAbsorberオブジェクトを作成します。
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
//文書ページの吸収剤を受け入れる
document.Pages.Accept(absorber);
//最初に抽出されたテキストフラグメントを取得する
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
//ページの指定された四角形内にフローティングテキスト用の隠しテキストフィールドを作成します。
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
//フィールド値として表示されるテキストを設定する
floatingField.Value = "This is the \"floating text field\".";
//このシナリオではフィールドを「読み取り専用」にすることをお勧めします
floatingField.ReadOnly = true;
//ドキュメントを開いたときにフィールドを非表示にするには、「非表示」フラグを設定します
floatingField.Flags |= AnnotationFlags.Hidden;
//一意のフィールド名を設定する必要はありませんが、設定することは可能です
floatingField.PartialName = "FloatingField_1";
//フィールドの外観の特性を設定することは必須ではないが、より良いものになる。
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
//ドキュメントにテキストフィールドを追加する
document.Form.Add(floatingField);
//テキストフラグメントの位置に非表示のボタンを作成する
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
//指定されたフィールド (注釈) と非表示フラグの新しい非表示アクションを作成します。
// (上記で指定した場合は、名前でフローティング フィールドを参照することもできます。)
//非表示のボタンフィールドでマウスのエンター/エグジットのアクションを追加する
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
//ドキュメントにボタンフィールドを追加する
document.Form.Add(buttonField);
//ドキュメントを保存
document.Save(outputFile);
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET ライブラリを使用して隠しテキスト ブロックを作成する方法を学習しました。ステップ バイ ステップ ガイドに従うことで、マウス カーソルを特定の領域に置いたときに表示される隠しテキスト フィールドを含む PDF ドキュメントを生成できます。隠しテキスト ブロックの外観と動作は、必要に応じてカスタマイズできます。

### よくある質問

#### Q: 「PDF ファイル内の隠しテキスト ブロック」チュートリアルの目的は何ですか?

A: 「PDF ファイル内の隠しテキスト ブロック」チュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ファイルに隠しテキスト ブロックを作成する方法について説明します。隠しテキスト ブロックは、マウス カーソルを特定の領域に置いたときに表示されるフローティング テキストです。このチュートリアルでは、C# ソース コードを使用してステップ バイ ステップ ガイドを提供します。

#### Q: PDF ファイルに隠しテキスト ブロックを作成するのはなぜですか?

A: 隠しテキスト ブロックを作成すると、ユーザーがマウス カーソルを指定された領域に置いたときにのみ表示される追加情報やコンテキストを提供したいインタラクティブな PDF ドキュメントに役立ちます。

#### Q: ドキュメント ディレクトリを設定するにはどうすればよいですか?

A: ドキュメントディレクトリを設定するには:

1. 交換する`"YOUR DOCUMENT DIRECTORY"`の`dataDir`生成された PDF ファイルを保存するディレクトリへのパスを持つ変数。

#### Q: サンプル ドキュメントを作成し、それにテキスト フラグメントを追加するにはどうすればよいですか?

 A: チュートリアルでは、`Document`クラスを使用してサンプル PDF ドキュメントを作成し、テキスト フラグメントを追加します。このテキスト フラグメントは、非表示のテキスト ブロックを表示するためのトリガーとして機能します。

#### Q: 隠しテキスト ブロックをトリガーするテキスト フラグメントを見つけるにはどうすればよいですか?

 A: チュートリアルでは、`TextFragmentAbsorber`隠しテキスト ブロックの表示をトリガーするテキスト フラグメントを検索するオブジェクト。PDF ドキュメント内の特定のテキスト文字列を検索します。

#### Q: 隠しテキスト フィールドを作成してカスタマイズするにはどうすればよいですか?

 A: 作成する`TextBoxField`隠しテキスト フィールドを表すオブジェクト。チュートリアルでは、隠しテキスト フィールドの位置、値、外観、動作などのさまざまなプロパティを設定するコードを提供します。

#### Q: 隠しテキスト ブロックに関連付けられた非表示のボタンを作成するにはどうすればよいですか?

 A: 目に見えないボタンフィールドは、`ButtonField`クラス。このボタン フィールドはトリガー テキスト フラグメントの上に配置され、マウスの Enter イベントと Exit イベントに関連付けられたアクションがあります。これらのアクションは、非表示のテキスト ブロックの表示を制御します。

#### Q: 隠しテキスト ブロックとトリガー領域の外観をカスタマイズできますか?

A: はい、フォント、色、サイズ、位置など、隠しテキスト フィールドと非表示ボタンの両方のさまざまなプロパティをカスタマイズできます。

#### Q: 隠しテキスト ブロックを含む変更されたドキュメントを保存するにはどうすればよいですか?

 A: チュートリアルでは、変更した文書を`Save`方法の`Document`クラス。