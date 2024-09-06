---
title: PDF ファイルに日付タイムスタンプを追加する
linktitle: PDF ファイルに日付タイムスタンプを追加する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルに日付と時刻のスタンプを簡単に追加する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
この記事では、Aspose.PDF for .NET を使用して PDF ファイルに日付と時刻のスタンプを追加する方法を段階的に説明します。提供されている C# ソース コードを使用して、既存の PDF ファイルに日付と時刻のスタンプを追加する方法を説明します。

## 要件

始める前に、次のものがあることを確認してください。

- インストールされた .NET 開発環境。
- .NET 用の Aspose.PDF ライブラリがダウンロードされ、プロジェクトで参照されます。

## ステップ1: 環境の設定

PDF ドキュメントに日付と時刻のスタンプを追加する前に、開発環境を設定する必要があります。次の手順に従います。

1. お気に入りの IDE (統合開発環境) を開きます。
2. 新しい C# プロジェクトを作成します。
3. .NET 用の Aspose.PDF ライブラリへの参照を追加したことを確認してください。

## ステップ2: Aspose.PDFライブラリの追加

プロジェクトで PDF ドキュメントを操作するには、.NET 用の Aspose.PDF ライブラリが必要です。

## ステップ3: PDF文書の読み込み

日付と時刻のスタンプを追加する最初の手順は、既存の PDF ドキュメントをプロジェクトに読み込むことです。手順は次のとおりです。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//文書を開く
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

「YOUR DOCUMENTS DIRECTORY」を、PDF ドキュメントが保存されているディレクトリへの実際のパスに置き換えてください。

## ステップ4: 日付と時刻のスタンプを作成する

文書をアップロードしたら

  PDF では、追加する日付と時刻のスタンプを作成できます。手順は次のとおりです。

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

//テキストバッファを作成する
TextStamp textStamp = new TextStamp(annotationText);
```

上記のコードは、現在の日付と時刻を含む新しいテキスト バッファーを作成します。

## ステップ5: スタンププロパティの設定

PDF ドキュメントにスタンプを追加する前に、余白、水平および垂直の配置など、スタンプのさまざまなプロパティを設定できます。手順は次のとおりです。

```csharp
//バッファプロパティを設定する
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

必要に応じてこれらのプロパティを調整できます。

## ステップ6: PDFにスタンプを追加する

日付と時刻のスタンプが準備できたので、それを PDF ドキュメントの特定のページに追加できます。手順は次のとおりです。

```csharp
//ページのスタンプコレクションにスタンプを追加する
pdfDocument.Pages[1].AddStamp(textStamp);
```

上記のコードは、PDF ドキュメントの最初のページにスタンプを追加します。必要に応じて別のページを指定することもできます。

## ステップ7: 出力ドキュメントを保存する

日付と時刻のスタンプを追加したら、変更した PDF ドキュメントを保存できます。手順は次のとおりです。

```csharp
//出力文書を保存する
pdfDocument.Save(dataDir);
```

上記のコードは、編集された PDF ドキュメントを指定されたディレクトリに保存します。

### Aspose.PDF for .NET を使用して日付タイムスタンプを追加するためのサンプル ソース コード 
```csharp

//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//ドキュメントを開く
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

//切手コレクションにスタンプを追加する
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

おめでとうございます! Aspose.PDF for .NET を使用して日付と時刻のスタンプを追加する方法を学習しました。これで、この知識を独自のプロジェクトに適用して、PDF ドキュメントに日付と時刻のスタンプを追加できます。

### PDF ファイルに日付タイムスタンプを追加するための FAQ

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメントに日付と時刻のスタンプを追加する目的は何ですか?

A: PDF ドキュメントに日付と時刻のスタンプを追加すると、ドキュメントがいつ変更または作成されたかがわかるため、情報価値が高まります。この機能は、ドキュメントの変更を追跡し、ドキュメント履歴の参照ポイントを提供するのに役立ちます。

#### Q: 特定の要件に合わせて日付とタイムスタンプの形式をカスタマイズできますか?

 A: はい、日付とタイムスタンプの形式はお好みに合わせてカスタマイズできます。提供されているC#ソースコードでは、`DateTime.Now.ToString()`特定の形式でタイムスタンプを生成するメソッド。このコードを変更して、必要に応じてタイムスタンプをフォーマットできます。

#### Q: PDF ページ上の特定の場所に日付と時刻のスタンプを追加することは可能ですか?

 A: もちろんです。PDFページの日付と時刻のスタンプの配置は、`TextStamp`オブジェクト。チュートリアルで提供されるコードは、余白、配置、垂直位置などのプロパティを設定する方法を示しています。

#### Q: 同じ PDF ドキュメントの異なるページに複数の日付と時刻のスタンプを追加できますか?

 A: はい、同じPDF文書の異なるページに複数の日付と時刻のスタンプを追加できます。`TextStamp`オブジェクトを作成し、目的のページごとにそのプロパティを構成します。

#### Q: 日付と時刻のスタンプのテキストのフォント、サイズ、色を変更するにはどうすればよいですか?

 A: 日付と時刻のスタンプテキストのフォント、サイズ、色を変更するには、`DefaultAppearance`作成に使用されたオブジェクト`TextStamp`フォント名、サイズ、色の値を調整して、希望する外観を実現します。

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメントに他の種類の注釈やスタンプを追加することは可能ですか?

A: はい、Aspose.PDF for .NET には、テキスト注釈、スタンプ、線、図形など、PDF ドキュメントに追加できるさまざまな注釈タイプが用意されています。注釈の操作の詳細については、Aspose.PDF のドキュメントを参照してください。

#### Q: PDF ドキュメントに日付と時刻のスタンプを追加する場合、制限や考慮事項はありますか?

A: 日付と時刻のスタンプを追加するのは簡単ですが、ドキュメントのレイアウトや既存のコンテンツなどの要素を考慮してください。スタンプの配置によって重要な情報が隠れたり、ドキュメントの読みやすさが損なわれたりしないように注意してください。

#### Q: この方法を自分のプロジェクトに統合して、PDF ドキュメントに日付と時刻のスタンプを追加するにはどうすればよいですか?

A: この方法を統合するには、提供されている手順に従い、プロジェクトの構造に合わせてコードを調整します。既存の PDF ドキュメントに日付と時刻のスタンプを追加して、その有用性を高め、変更のタイムラインを明確にすることができます。

#### Q: 複数の PDF ドキュメントに日付と時刻のスタンプを追加するプロセスを自動化できますか?

A: はい、ドキュメントのリストを反復処理し、各ドキュメントに同じスタンプ プロセスを適用するスクリプトまたはプログラムを作成することにより、複数の PDF ドキュメントに日付と時刻のスタンプを追加するプロセスを自動化できます。