---
title: PDF注釈を追加
linktitle: 注釈の追加
second_title: Aspose.PDF for .NET API リファレンス
description: この C# ソース コードを使用して、Aspose.PDF for .NET でテキスト PDF 注釈を追加する方法を学びます。特定の詳細とアイコンを使用して注釈をカスタマイズします。
type: docs
weight: 10
url: /ja/net/annotations/addannotation/
---
PDF ドキュメントへの注釈の追加は、コラボレーションとレビュー プロセスを強化できる強力な機能です。 Aspose.PDF for .NET を使用すると、C# を使用してプログラムで PDF ドキュメントに注釈を簡単に追加できます。このガイドでは、Aspose.PDF for .NET を使用して PDF ドキュメントに注釈を追加する方法を段階的に説明します。

## ステップ 1: 新しいプロジェクトを作成し、Aspose.PDF for .NET をインストールする

注釈を追加するコードを書き始める前に、新しいプロジェクトを作成し、Aspose.PDF for .NET をインストールする必要があります。 Aspose.PDF for .NET をインストールするには、次の手順に従います。

1. Visual Studio を開き、新しい C# プロジェクトを作成します。
2. ソリューション エクスプローラーでプロジェクトを右クリックし、[NuGet パッケージの管理] を選択します。
3. 「Aspose.PDF」を検索し、「インストール」を選択します。

インストールが完了したら、コードの記述を開始できます。

## ステップ 2: PDF ドキュメントを開く

注釈を追加する最初のステップは、PDF ドキュメントを開くことです。次のコードを使用してドキュメントを開くことができます。

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");
```

このコードでは、開きたい PDF ドキュメントへのパスを指定します。 「YOUR DATA DIRECTORY」をデータ ディレクトリへの実際のパスに置き換えてください。

## ステップ 3: 注釈を作成する

注釈を追加するには、`TextAnnotation`クラス。次のコードを使用して、新しいテキスト注釈を作成できます。

```csharp
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;
```

このコードでは、PDF ドキュメントの 2 ページ目に新しいテキスト注釈を作成します。注釈のタイトル、件名、状態、内容、開く、およびアイコンのプロパティも設定します。

## ステップ 4: 注釈をカスタマイズする

注釈の外観をカスタマイズするには、`Border`クラス。次のコードを使用して、注釈の境界線をカスタマイズできます。

```csharp
Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);
```

このコードでは、新しい`Border`オブジェクトを選択し、その幅とダッシュのプロパティを設定します。次に、`Border`新しい注釈のプロパティ`Border`物体。最後に、`Rect`注釈のプロパティを使用して、その位置とサイズを指定します。

## ステップ 5: PDF ドキュメントに注釈を追加する

注釈を作成してカスタマイズしたら、それを PDF ドキュメントに追加する必要があります。次のコードを使用して、PDF ドキュメントに注釈を追加できます。

```csharp
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

このコードでは、PDF ドキュメントの 2 ページ目の注釈コレクションに注釈を追加します。

## ステップ 6: 出力ファイルを保存する

最後に、注釈を追加して PDF ドキュメントを保存する必要があります。次のコードを使用して出力ファイルを保存できます。

```csharp
dataDir = dataDir + "AddAnnotation_out.pdf";
pdfDocument.Save(dataDir);
```
### Aspose.PDF for .NET を使用して注釈を追加するためのソース コードの例


```csharp   
 //ドキュメントディレクトリへのパス。
string dataDir = "YOUR DATA DIRECTORY";

//開いた文書
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");

//注釈の作成
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;

Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);

//ページの注釈コレクションに注釈を追加します
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddAnnotation_out.pdf";
//出力ファイルを保存する
pdfDocument.Save(dataDir);
```
このコードは、Aspose.PDF for .NET を使用して、特定のタイトル、件名、状態、内容、アイコンを含むテキスト注釈を PDF ページに追加する方法を示します。 PDF ドキュメントに注釈を追加するための要件に応じて、このコードを変更できます。 YOUR DATA DIRECTORY を、PDF ファイルが配置され、出力ファイルを保存する実際のディレクトリ パスに置き換えることを忘れないでください。

## 結論

Aspose.PDF for .NET を使用して PDF ドキュメントに注釈を追加すると、ドキュメントのコラボレーションとレビュー プロセスを強化するための貴重なツールが提供されます。この記事に記載されているステップバイステップ ガイドに従うことで、開発者は注釈機能を C# アプリケーションにシームレスに統合できます。

### よくある質問

#### Q: Aspose.PDF for .NET を使用して追加できる注釈の種類は何ですか?

A: Aspose.PDF for .NET は、テキスト注釈、スタンプ、リンク、図形などを含む、さまざまなタイプの注釈をサポートしています。開発者は、特定のニーズに合わせてこれらの注釈の外観とプロパティをカスタマイズできます。

#### Q: 複数ページの PDF ドキュメント内の特定のページに注釈を追加できますか?

A: はい、Aspose.PDF for .NET を使用すると、注釈を追加するページを指定できます。必要に応じて、特定のページを選択したり、複数のページに注釈を追加したりできます。

#### Q: 注釈の外観をカスタマイズするにはどうすればよいですか?

A: 注釈は、境界線の幅、色、ダッシュ スタイル、テキスト スタイルなどのプロパティを使用してカスタマイズできます。 Aspose.PDF for .NET は、注釈の外観を調整するための豊富なオプション セットを提供します。

#### Q: Aspose.PDF for .NET を使用してハイパーリンクを注釈として追加することはできますか?

A: はい、Aspose.PDF for .NET を使用して PDF ドキュメントにハイパーリンクを注釈として追加できます。ハイパーリンク注釈を使用して、外部 URL または同じドキュメント内の特定の場所にリンクできます。

#### Q: 元のコンテンツを変更せずに、既存の PDF ドキュメントに注釈を追加できますか?

A: はい、Aspose.PDF for .NET は、PDF ドキュメントの元のコンテンツを変更することなく、追加要素として注釈を追加します。元の PDF コンテンツはそのまま残ります。