---
title: PDF ファイルに日付時刻スタンプを追加する
linktitle: PDF ファイルに日付時刻スタンプを追加する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルに日付とタイムスタンプを簡単に追加する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
この記事では、Aspose.PDF for .NET を使用して PDF ファイルに日付とタイムスタンプを追加する方法を段階的に説明します。提供されている C# ソース コードを使用して、既存の PDF ファイルに日付とタイム スタンプを追加する方法を示します。

## 要件

始める前に、以下のものがあることを確認してください。

- インストールされた .NET 開発環境。
- .NET 用の Aspose.PDF ライブラリがダウンロードされ、プロジェクトで参照されます。

## ステップ 1: 環境をセットアップする

PDF ドキュメントに日付とタイムスタンプを追加するには、開発環境をセットアップする必要があります。従うべき手順は次のとおりです。

1. お気に入りの IDE (統合開発環境) を開きます。
2. 新しい C# プロジェクトを作成します。
3. .NET 用の Aspose.PDF ライブラリへの参照を追加していることを確認してください。

## ステップ 2: Aspose.PDF ライブラリを追加する

プロジェクトで PDF ドキュメントを操作するには、.NET 用の Aspose.PDF ライブラリが必要です。

## ステップ 3: PDF ドキュメントをロードする

日付とタイムスタンプを追加する最初のステップは、既存の PDF ドキュメントをプロジェクトにロードすることです。その方法は次のとおりです。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//文書を開く
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

「YOUR DOCUMENTS DIRECTORY」を、PDF ドキュメントが配置されているディレクトリへの実際のパスに必ず置き換えてください。

## ステップ 4: 日付とタイムスタンプの作成

これでドキュメントのアップロードが完了しました

  PDF に日付とタイムスタンプを追加して作成できます。その方法は次のとおりです。

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

//テキストバッファを作成する
TextStamp textStamp = new TextStamp(annotationText);
```

上記のコードは、現在の日付と時刻を含む新しいテキスト バッファーを作成します。

## ステップ 5: スタンプのプロパティの構成

PDF ドキュメントにスタンプを追加する前に、マージン、水平方向および垂直方向の配置など、スタンプのさまざまなプロパティを設定できます。その方法は次のとおりです。

```csharp
//バッファーのプロパティを設定する
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

必要に応じてこれらのプロパティを調整できます。

## ステップ 6: PDF にスタンプを追加する

日付とタイムスタンプの準備ができたので、PDF ドキュメントの特定のページに日付とタイムスタンプを追加できます。その方法は次のとおりです。

```csharp
//ページのスタンプ コレクションにスタンプを追加します
pdfDocument.Pages[1].AddStamp(textStamp);
```

上記のコードは、PDF ドキュメントの最初のページにスタンプを追加します。必要に応じて、別のページを指定できます。

## ステップ 7: 出力ドキュメントを保存する

日付とタイムスタンプを追加したら、変更した PDF ドキュメントを保存できます。その方法は次のとおりです。

```csharp
//出力ドキュメントを保存する
pdfDocument.Save(dataDir);
```

上記のコードは、編集した PDF ドキュメントを指定されたディレクトリに保存します。

### Aspose.PDF for .NET を使用した日付時刻スタンプの追加のサンプル ソース コード 
```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開いた文書
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

//テキストスタンプを作成する
TextStamp textStamp = new TextStamp(annotationText);

//スタンプのプロパティを設定する
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

//スタンプコレクションにスタンプを追加する
pdfDocument.Pages[1].AddStamp(textStamp);
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;

Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddDateTimeStamp_out.pdf";

//出力ドキュメントを保存する
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);  
          
```

## 結論

おめでとうございます！ Aspose.PDF for .NET を使用して日付とタイム スタンプを追加する方法を学習しました。この知識を独自のプロジェクトに適用して、PDF ドキュメントに日付とタイムスタンプを追加できるようになりました。

### PDF ファイルに日付タイムスタンプを追加する場合の FAQ

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメントに日付とタイムスタンプを追加する目的は何ですか?

A: PDF ドキュメントに日付とタイムスタンプを追加すると、ドキュメントがいつ変更または作成されたかを示すため、その情報価値が高まります。この機能は、ドキュメントの変更を追跡し、ドキュメント履歴の参照ポイントを提供するのに役立ちます。

#### Q: 特定の要件に合わせて日付とタイムスタンプの形式をカスタマイズできますか?

 A: はい、好みに応じて日付とタイムスタンプの形式をカスタマイズできます。提供されている C# ソース コードでは、`DateTime.Now.ToString()`特定の形式でタイムスタンプを生成するメソッド。必要に応じて、このコードを変更してタイムスタンプをフォーマットできます。

#### Q: PDF ページ上の特定の場所に日付と時刻のスタンプを追加することはできますか?

 A: もちろん、PDF ページ上の日付とタイムスタンプの配置は、プロパティを変更することで調整できます。`TextStamp`物体。チュートリアルで提供されるコードは、マージン、配置、垂直位置などのプロパティを設定する方法を示しています。

#### Q: 同じ PDF ドキュメントの異なるページに複数の日付とタイムスタンプを追加できますか?

 A: はい、同じ PDF ドキュメントの異なるページに複数の日付とタイム スタンプを追加できます。作成プロセスを繰り返すだけです。`TextStamp`オブジェクトを作成し、必要なページごとにそのプロパティを構成します。

#### Q: 日付とタイムスタンプのテキストのフォント、サイズ、色を変更するにはどうすればよいですか?

 A: 日付とタイムスタンプのテキストのフォント、サイズ、色を変更するには、`DefaultAppearance`の作成に使用されるオブジェクト`TextStamp`。フォント名、サイズ、色の値を調整して、希望の外観を実現します。

#### Q: Aspose.PDF for .NET を使用して、PDF ドキュメントに他のタイプの注釈やスタンプを追加することはできますか?

A: はい。Aspose.PDF for .NET は、テキスト注釈、スタンプ、線、図形など、PDF ドキュメントに追加できる幅広い注釈タイプを提供します。注釈の操作の詳細については、Aspose.PDF ドキュメントを参照してください。

#### Q: PDF ドキュメントに日付と時刻のスタンプを追加する場合、制限や考慮事項はありますか?

A: 日付とタイムスタンプを追加するのは簡単ですが、ドキュメントのレイアウトや既存のコンテンツなどの要素を考慮してください。スタンプの配置によって重要な情報が見えにくくなったり、文書の読みやすさに影響を与えたりしないように注意してください。

#### Q: この方法を自分のプロジェクトに統合して、PDF ドキュメントに日付とタイムスタンプを追加するにはどうすればよいですか?

A: このメソッドを統合するには、提供されている手順に従い、プロジェクトの構造に合わせてコードを調整します。既存の PDF ドキュメントに日付とタイムスタンプを追加して、ドキュメントの有用性を高め、変更の明確なタイムラインを提供できます。

#### Q: 複数の PDF ドキュメントに日付とタイムスタンプを追加するプロセスを自動化できますか?

A: はい、ドキュメントのリストを反復処理して各ドキュメントに同じスタンプ プロセスを適用するスクリプトまたはプログラムを作成することで、複数の PDF ドキュメントに日付とタイム スタンプを追加するプロセスを自動化できます。