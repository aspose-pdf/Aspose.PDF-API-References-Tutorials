---
title: PDF ファイルにテキスト スタンプを追加する
linktitle: PDF ファイルにテキスト スタンプを追加する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルにテキスト スタンプを簡単に追加する方法を学びます。
type: docs
weight: 50
url: /ja/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルにテキスト スタンプを追加する方法を段階的に説明します。提供されている C# ソース コードを使用して、PDF ファイルの特定のページにカスタム テキスト スタンプを追加する方法を説明します。

## ステップ1: 環境の設定

始める前に、次のものがあることを確認してください。

- インストールされた .NET 開発環境。
- .NET 用の Aspose.PDF ライブラリがダウンロードされ、プロジェクトで参照されます。

## ステップ2: PDF文書の読み込み

最初のステップは、既存の PDF ドキュメントをプロジェクトに読み込むことです。手順は次のとおりです。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//文書を開く
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

「YOUR DOCUMENTS DIRECTORY」を、PDF ドキュメントが保存されているディレクトリへの実際のパスに置き換えてください。

## ステップ3: テキストバッファの作成

PDF ドキュメントをアップロードしたら、追加するテキスト スタンプを作成できます。手順は次のとおりです。

```csharp
//テキストバッファを作成する
TextStamp textStamp = new TextStamp("Example Stamp");
```

上記のコードは、指定されたテキストを含む新しいテキスト バッファーを作成します。

## ステップ4: テキストスタンプのプロパティを構成する

PDF ドキュメントにテキスト スタンプを追加する前に、背景、位置、回転、フォント、サイズなど、スタンプのさまざまなプロパティを設定できます。手順は次のとおりです。

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

## ステップ5: PDFにテキストスタンプを追加する

テキスト スタンプの準備ができたので、それを PDF ドキュメントの特定のページに追加できます。手順は次のとおりです。

```csharp
//特定のページにテキストバッファを追加する
pdfDocument.Pages[1].AddStamp(textStamp);
```

上記のコードは、PDF ドキュメントの最初のページにテキスト スタンプを追加します。必要に応じて別のページを指定することもできます。

## ステップ6: 出力ドキュメントを保存する

テキスト スタンプを追加したら、編集した PDF ドキュメントを保存できます。手順は次のとおりです。

```csharp
//出力文書を保存する
pdfDocument.Save(dataDir);
```

上記のコードは、変更された PDF ドキュメントを指定されたディレクトリに保存します。

### Aspose.PDF for .NET を使用してテキスト スタンプを追加するためのサンプル ソース コード 
```csharp

//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//ドキュメントを開く
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

//テキストスタンプを作成する
TextStamp textStamp = new TextStamp("Sample Stamp");

//スタンプを背景にするかどうかを設定する
textStamp.Background = true;

//原点を設定
textStamp.XIndent = 100;
textStamp.YIndent = 100;

//スタンプを回転する
textStamp.Rotate = Rotation.on90;

//テキストプロパティを設定する
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

おめでとうございます! Aspose.PDF for .NET を使用してテキスト スタンプを追加する方法を学習しました。これで、この知識を独自のプロジェクトに適用して、PDF ドキュメントにカスタム テキスト スタンプを追加できます。

### PDF ファイルにテキスト スタンプを追加する方法に関する FAQ

#### Q: Aspose.PDF for .NET を使用して PDF ファイルにテキスト スタンプを追加する目的は何ですか?

A: テキスト スタンプを追加すると、PDF ドキュメントの特定のページにカスタム テキストを配置できます。この機能は、ラベル、コメント、透かし、その他のテキスト情報を追加して、ドキュメントのコンテンツを強化し、追加のコンテキストを提供するのに役立ちます。

#### Q: フォント、サイズ、色、回転など、テキスト スタンプの外観をカスタマイズできますか?

 A: はい、テキストスタンプの外観を完全にカスタマイズできます。提供されているC#ソースコードは、テキストスタンプのさまざまなプロパティを設定する方法を示しています。`TextStamp`フォント、フォント サイズ、フォント スタイル、テキストの色、背景色、回転などのオブジェクト。

#### Q: 同じ PDF ドキュメントの異なるページに複数のテキストスタンプを追加することは可能ですか?

A: もちろんです。同じ PDF ドキュメントの異なるページに複数のテキスト スタンプを追加できます。チュートリアルで提供されているコードを使用すると、テキスト スタンプを追加する対象ページを指定できるため、ドキュメント内のさまざまなページに柔軟に使用できます。

#### Q: PDF ドキュメント内でテキスト スタンプの位置を指定するにはどうすればよいですか?

 A: テキストスタンプの位置は、`XIndent`そして`YIndent`の特性`TextStamp`オブジェクト。これらのプロパティは、ページの原点を基準としたスタンプの左上隅の座標を定義します。

#### Q: この方法を既存の PDF ドキュメントに適用してテキスト スタンプを追加できますか?

A: はい、この方法を既存の PDF ドキュメントに適用してテキスト スタンプを追加できます。チュートリアルで提供されているコードは、既存の PDF ドキュメントを読み込み、特定のページにテキスト スタンプを追加する方法を示しています。

#### Q: テキストスタンプに背景色と前景色の両方を追加できますか?

 A: はい、テキストスタンプに背景色と前景色の両方を追加できます。`Background`財産に`true`テキストスタンプに色付きの背景を設定することができます。さらに、`TextState.ForegroundColor`テキスト自体の色を指定するプロパティ。

#### Q: テキスト スタンプによって PDF ドキュメントの基になるコンテンツが隠れないようにするにはどうすればよいですか?

A: テキストスタンプを追加するときは、重要な情報を隠したり、文書の読みやすさを損なったりしないように、配置に注意してください。`XIndent`そして`YIndent`テキストスタンプを適切に配置するためのプロパティ。

#### Q: この方法で、画像やロゴなどテキスト以外のスタンプを追加できますか?

A: このチュートリアルではテキスト スタンプの追加に焦点を当てていますが、Aspose.PDF for .NET を使用して、画像やロゴなどの他の種類のスタンプも同様に追加できます。このプロセスでは、適切なスタンプ オブジェクトを作成し、そのプロパティを構成します。

#### Q: 複数の PDF ドキュメントにテキスト スタンプを追加するプロセスを自動化するにはどうすればよいですか?

A: ドキュメントのリストを反復処理し、各ドキュメントに同じテキスト スタンプ プロセスを適用するスクリプトまたはプログラムを作成することにより、複数の PDF ドキュメントにテキスト スタンプを追加するプロセスを自動化できます。