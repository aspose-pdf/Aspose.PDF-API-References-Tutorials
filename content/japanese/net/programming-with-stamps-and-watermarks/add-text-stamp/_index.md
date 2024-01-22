---
title: PDF ファイルにテキストスタンプを追加
linktitle: PDF ファイルにテキストスタンプを追加
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルにテキスト スタンプを簡単に追加する方法を学びます。
type: docs
weight: 50
url: /ja/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルにテキスト スタンプを追加する方法を段階的に説明します。提供されている C# ソース コードを使用して、PDF ファイルの特定のページにカスタム テキスト スタンプを追加する方法を示します。

## ステップ 1: 環境をセットアップする

始める前に、以下のものがあることを確認してください。

- インストールされた .NET 開発環境。
- .NET 用の Aspose.PDF ライブラリがダウンロードされ、プロジェクトで参照されます。

## ステップ 2: PDF ドキュメントをロードする

最初のステップは、既存の PDF ドキュメントをプロジェクトにロードすることです。その方法は次のとおりです。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//文書を開く
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

「YOUR DOCUMENTS DIRECTORY」を、PDF ドキュメントが配置されているディレクトリへの実際のパスに必ず置き換えてください。

## ステップ 3: テキストバッファの作成

PDF ドキュメントをアップロードしたので、追加するテキスト スタンプを作成できます。その方法は次のとおりです。

```csharp
//テキストバッファを作成する
TextStamp textStamp = new TextStamp("Example Stamp");
```

上記のコードは、指定されたテキストを含む新しいテキスト バッファーを作成します。

## ステップ 4: テキストスタンプのプロパティの構成

PDF ドキュメントにテキスト スタンプを追加する前に、背景、位置、回転、フォント、サイズなど、スタンプのさまざまなプロパティを構成できます。その方法は次のとおりです。

```csharp
//テキストバッファのプロパティを構成する
textStamp. Background = true;
textStamp. XIndent = 100;
textStamp. YIndent = 100;
textStamp.Rotate = Rotate.on90;
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);
```

必要に応じてこれらのプロパティを調整できます。

## ステップ 5: PDF にテキストスタンプを追加する

テキスト スタンプの準備ができたので、PDF ドキュメントの特定のページにテキスト スタンプを追加できます。その方法は次のとおりです。

```csharp
//特定のページにテキストバッファを追加する
pdfDocument.Pages[1].AddStamp(textStamp);
```

上記のコードは、PDF ドキュメントの最初のページにテキスト スタンプを追加します。必要に応じて、別のページを指定できます。

## ステップ 6: 出力ドキュメントを保存する

テキストスタンプを追加したら、編集した PDF ドキュメントを保存できます。その方法は次のとおりです。

```csharp
//出力ドキュメントを保存する
pdfDocument.Save(dataDir);
```

上記のコードは、変更された PDF ドキュメントを指定されたディレクトリに保存します。

### Aspose.PDF for .NET を使用したテキスト スタンプの追加のサンプル ソース コード 
```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開いた文書
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

//テキストスタンプを作成する
TextStamp textStamp = new TextStamp("Sample Stamp");

//スタンプを背景にするかどうかを設定します
textStamp.Background = true;

//原点の設定
textStamp.XIndent = 100;
textStamp.YIndent = 100;

//スタンプを回転する
textStamp.Rotate = Rotation.on90;

//テキストのプロパティを設定する
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold;
textStamp.TextState.FontStyle = FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);

//特定のページにスタンプを追加する
pdfDocument.Pages[1].AddStamp(textStamp);
dataDir = dataDir + "AddTextStamp_out.pdf";

//出力ドキュメントを保存する
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            

```

## 結論

おめでとうございます！ Aspose.PDF for .NET を使用してテキスト スタンプを追加する方法を学習しました。この知識を独自のプロジェクトに適用して、PDF ドキュメントにカスタム テキスト スタンプを追加できるようになりました。

### PDF ファイルにテキストスタンプを追加する場合の FAQ

#### Q: Aspose.PDF for .NET を使用して PDF ファイルにテキスト スタンプを追加する目的は何ですか?

A: テキスト スタンプを追加すると、PDF ドキュメントの特定のページにカスタム テキストを配置できます。この機能は、ラベル、コメント、透かし、またはその他のテキスト情報を追加して、ドキュメントのコンテンツを強化し、追加のコンテキストを提供する場合に役立ちます。

#### Q: フォント、サイズ、色、回転など、テキスト スタンプの外観をカスタマイズできますか?

 A: はい、テキスト スタンプの外観を完全にカスタマイズできます。提供されている C# ソース コードは、`TextStamp`オブジェクト (フォント、フォント サイズ、フォント スタイル、テキストの色、背景色、回転など)。

#### Q: 同じ PDF ドキュメントの異なるページに複数のテキスト スタンプを追加することはできますか?

A: もちろん、同じ PDF ドキュメントの異なるページに複数のテキスト スタンプを追加できます。チュートリアルで提供されるコードを使用すると、テキスト スタンプを追加するターゲット ページを指定できるため、ドキュメント内のさまざまなページに多用途に使用できます。

#### Q: PDF ドキュメント内のテキストスタンプの位置を指定するにはどうすればよいですか?

 A: テキストスタンプの位置をカスタマイズするには、`XIndent`そして`YIndent`のプロパティ`TextStamp`物体。これらのプロパティは、ページの原点を基準としたスタンプの左上隅の座標を定義します。

#### Q: この方法を既存の PDF ドキュメントに適用してテキスト スタンプを追加できますか?

A: はい、この方法を既存の PDF ドキュメントに適用して、テキスト スタンプを追加できます。チュートリアルで提供されるコードは、既存の PDF ドキュメントをロードし、特定のページにテキスト スタンプを追加する方法を示しています。

#### Q: テキストスタンプに背景色と前景色の両方を追加できますか?

 A: はい、背景色と前景色の両方をテキスト スタンプに追加できます。を設定することで、`Background`財産を`true`では、テキスト スタンプに色付きの背景を指定できます。さらに、次のように設定できます。`TextState.ForegroundColor`プロパティを使用してテキスト自体の色を指定します。

#### Q: テキスト スタンプによって PDF ドキュメントの基礎となるコンテンツが隠されないようにするにはどうすればよいですか?

 A: テキスト スタンプを追加する場合は、重要な情報を妨げたり、文書の読みやすさに悪影響を与えたりしないように、その位置に注意してください。調整できます`XIndent`そして`YIndent`プロパティを使用してテキストスタンプを適切に配置します。

#### Q: この方法で文字以外の画像やロゴなどのスタンプを追加することはできますか?

A: この特定のチュートリアルでは、テキスト スタンプの追加に焦点を当てていますが、Aspose.PDF for .NET を使用して、画像やロゴなどの他の種類のスタンプも同様に追加できます。このプロセスには、適切なスタンプ オブジェクトの作成とそのプロパティの構成が含まれます。

#### Q: 複数の PDF ドキュメントにテキスト スタンプを追加するプロセスを自動化するにはどうすればよいですか?

A: ドキュメントのリストを反復処理して各ドキュメントに同じテキスト スタンプ プロセスを適用するスクリプトまたはプログラムを作成することで、複数の PDF ドキュメントにテキスト スタンプを追加するプロセスを自動化できます。