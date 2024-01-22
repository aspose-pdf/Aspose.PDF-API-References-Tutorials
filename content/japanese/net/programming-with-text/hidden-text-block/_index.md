---
title: PDF ファイル内の隠しテキスト ブロック
linktitle: PDF ファイル内の隠しテキスト ブロック
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルに隠しテキスト ブロックを作成する方法を学びます。
type: docs
weight: 230
url: /ja/net/programming-with-text/hidden-text-block/
---
このチュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ファイルに隠しテキスト ブロックを作成する方法を説明します。非表示のテキスト ブロックは、マウス カーソルを特定の領域の上に置くと表示されるフローティング テキストです。提供された C# ソース コードを使用して、隠しテキスト ブロックを作成するプロセスを段階的に説明します。

## 要件

始める前に、以下のものがあることを確認してください。

- Aspose.PDF for .NET ライブラリがインストールされています。
- C# プログラミングの基本的な理解。

## ステップ 1: ドキュメント ディレクトリを設定する

まず、生成された PDF ファイルを保存するディレクトリへのパスを設定する必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`の中に`dataDir`変数を目的のディレクトリへのパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: サンプルドキュメントを作成する

このステップでは、サンプル PDF ドキュメントを作成し、それにテキスト フラグメントを追加します。テキストフラグメントは、非表示のテキストブロックを表示するためのトリガーとして機能します。

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## ステップ 3: ドキュメントを開く

ここで、以前に作成したドキュメントを次のコマンドを使用して開きます。`Document`クラス。

```csharp
Document document = new Document(outputFile);
```

## ステップ 4: テキストの断片を見つける

私たちは、`TextFragmentAbsorber`オブジェクトを使用して、非表示のテキスト ブロックの表示をトリガーするテキスト フラグメントを見つけます。この場合、「フローティング テキストを表示するには、マウス カーソルをここに移動してください」という正確なテキストを検索しています。

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## ステップ 5: 隠しテキストフィールドを作成する

私たちは`TextBoxField`隠しテキストフィールドを表すオブジェクト。このフィールドには、マウス カーソルをトリガー テキストの上に置いたときに表示されるテキストが含まれます。

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

## ステップ 6: 文書に隠しテキストフィールドを追加する

非表示のテキスト フィールドをドキュメントのフォーム コレクションに追加します。

```csharp
document.Form.Add(floatingField);
```

## ステップ 7: 非表示ボタンを作成する

トリガー テキスト フラグメントの上に配置される非表示のボタン フィールドを作成します。このボタン フィールドには、マウスの出入りイベントに関連付けられたアクションが含まれます。

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## ステップ 8: ドキュメントを保存する

最後に、変更したドキュメントを非表示のテキスト ブロックとともに保存します。

```csharp
document. Save(outputFile);
```

### Aspose.PDF for .NET を使用した隠しテキスト ブロックのサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
//テキストを含むサンプルドキュメントを作成する
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
//テキストを含む文書を開く
Document document = new Document(outputFile);
//TextAbsorber オブジェクトを作成して、正規表現に一致するすべてのフレーズを検索します
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
//文書ページの吸収材を受け入れる
document.Pages.Accept(absorber);
//最初に抽出されたテキスト断片を取得する
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
//ページの指定された四角形にフローティング テキスト用の隠しテキスト フィールドを作成します
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
//フィールド値として表示するテキストを設定します
floatingField.Value = "This is the \"floating text field\".";
//このシナリオではフィールドを「読み取り専用」にすることをお勧めします
floatingField.ReadOnly = true;
//「非表示」フラグを設定して、ドキュメントを開いたときにフィールドを非表示にします
floatingField.Flags |= AnnotationFlags.Hidden;
//一意のフィールド名の設定は必須ではありませんが、許可されています
floatingField.PartialName = "FloatingField_1";
//フィールドの外観の特性を設定する必要はありませんが、より良くすることができます
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
//ドキュメントにテキストフィールドを追加する
document.Form.Add(floatingField);
//テキストフラグメントの位置に非表示のボタンを作成します
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
//指定されたフィールド (注釈) と非表示フラグの新しい非表示アクションを作成します。
//(上で指定した場合は、フローティング フィールドを名前で参照することもできます。)
//目に見えないボタンフィールドにマウスの入力/終了時のアクションを追加します
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
//ボタンフィールドをドキュメントに追加する
document.Form.Add(buttonField);
//文書の保存
document.Save(outputFile);
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET ライブラリを使用して隠しテキスト ブロックを作成する方法を学習しました。ステップバイステップのガイドに従うことで、マウス カーソルを特定の領域の上に置くと表示される非表示のテキスト フィールドを含む PDF ドキュメントを生成できます。要件に応じて、隠しテキスト ブロックの外観と動作をカスタマイズできます。

### よくある質問

#### Q: 「PDF ファイル内の隠しテキスト ブロック」チュートリアルの目的は何ですか?

A: 「PDF ファイルの隠しテキスト ブロック」チュートリアルでは、.NET 用の Aspose.PDF ライブラリを使用して PDF ファイルに隠しテキスト ブロックを作成する方法を説明しています。非表示のテキスト ブロックは、マウス カーソルを特定の領域の上に置くと表示されるフローティング テキストです。このチュートリアルでは、C# ソース コードを使用したステップバイステップのガイドを提供します。

#### Q: PDF ファイルに隠しテキスト ブロックを作成する必要があるのはなぜですか?

A: 隠しテキスト ブロックの作成は、ユーザーが指定された領域上にマウス カーソルを置いたときにのみ表示される追加情報やコンテキストを提供するインタラクティブな PDF ドキュメントに役立ちます。

#### Q: ドキュメント ディレクトリはどのように設定すればよいですか?

A: ドキュメント ディレクトリを設定するには:

1. 交換する`"YOUR DOCUMENT DIRECTORY"`の中に`dataDir`変数には、生成された PDF ファイルを保存するディレクトリへのパスを指定します。

#### Q: サンプルドキュメントを作成し、それにテキストフラグメントを追加するにはどうすればよいですか?

A: チュートリアルでは、`Document`クラスを使用してサンプル PDF ドキュメントを作成し、テキスト フラグメントを追加します。このテキスト フラグメントは、隠しテキスト ブロックを表示するためのトリガーとして機能します。

#### Q: 隠しテキスト ブロックをトリガーするテキスト フラグメントを見つけるにはどうすればよいですか?

 A: チュートリアルでは、`TextFragmentAbsorber`オブジェクトを使用して、非表示のテキスト ブロックの表示をトリガーするテキスト フラグメントを見つけます。 PDF ドキュメント内の特定のテキスト文字列を検索します。

#### Q: 隠しテキストフィールドを作成およびカスタマイズするにはどうすればよいですか?

 A: あなたが作成するのは、`TextBoxField`隠しテキストフィールドを表すオブジェクト。このチュートリアルでは、非表示のテキスト フィールドの位置、値、外観、動作などのさまざまなプロパティを設定するコードを提供します。

#### Q: 非表示のテキスト ブロックに関連付けられた非表示のボタンを作成するにはどうすればよいですか?

 A: 非表示のボタン フィールドは、`ButtonField`クラス。このボタン フィールドはトリガー テキスト フラグメントの上部に配置され、マウスの出入りイベントに関連付けられたアクションを持ちます。これらのアクションは、非表示のテキスト ブロックの表示/非表示を制御します。

#### Q: 隠しテキスト ブロックとトリガー領域の外観をカスタマイズできますか?

A: はい、非表示のテキスト フィールドと非表示のボタンの両方のフォント、色、サイズ、位置などのさまざまなプロパティをカスタマイズできます。

#### Q: 非表示のテキスト ブロックを含む変更されたドキュメントを保存するにはどうすればよいですか?

 A: このチュートリアルでは、`Save`の方法`Document`クラス。