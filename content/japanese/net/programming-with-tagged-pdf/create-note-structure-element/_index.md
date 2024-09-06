---
title: ノート構造要素の作成
linktitle: ノート構造要素の作成
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ドキュメントに構造化されたメモ項目を作成する手順ガイド。
type: docs
weight: 30
url: /ja/net/programming-with-tagged-pdf/create-note-structure-element/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントに注釈構造要素を作成する方法を段階的に説明します。Aspose.PDF は、PDF ドキュメントをプログラムで作成、操作、変換できる強力なライブラリです。Aspose.PDF のマークされたコンテンツ構造機能を使用すると、PDF ドキュメントに構造化された注釈を追加できます。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

1. .NET フレームワークとともにインストールされた Visual Studio。
2. .NET 用の Aspose.PDF ライブラリ。

## ステップ1: プロジェクトのセットアップ

まず、Visual Studio で新しいプロジェクトを作成し、Aspose.PDF for .NET ライブラリへの参照を追加します。ライブラリは Aspose の公式 Web サイトからダウンロードして、マシンにインストールできます。

## ステップ2: 必要な名前空間をインポートする

C# コード ファイルで、Aspose.PDF によって提供されるクラスとメソッドにアクセスするために必要な名前空間をインポートします。

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## ステップ3: PDFドキュメントとノート構造化要素の作成

次のコードを使用して PDF ドキュメントを作成し、ノート構造化要素を追加します。

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample Grade Items");
taggedContent.SetLanguage("fr-FR");

ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);

NoteElement note1 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note1);
note1.SetText("Note with automatically generated ID. ");

NoteElement note2 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note2);
note2.SetText("Note with ID = 'note_002'.");
note2.SetId("note_002");

NoteElement note3 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note3);
note3.SetText("Note with ID = 'note_003'.");
note3.SetId("note_003");
```

このコードは、空の PDF ドキュメントを作成し、構造化されたメモ要素を段落に追加します。各メモは、Aspose.PDF によって提供されるメソッドを使用して作成されます。

## ステップ4: PDFドキュメントを保存する

PDF ドキュメントを保存するには、次のコードを使用します。

```csharp
document. Save(outFile);
```

このコードは、ノート構造化要素を含む PDF ドキュメントを指定されたファイルに保存します。

### Aspose.PDF for .NET を使用してノート構造要素を作成するためのサンプル ソース コード 

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
//PDFドキュメントを作成
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
//段落要素を追加する
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
//注記要素を追加
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
//注記要素を追加
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
//注記要素を追加
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
//例外をスローする必要があります - Aspose.Pdf.Tagged.TaggedException: ID='note_002' の構造要素が既に存在します
//note3.SetId("note_002");
// ClearId() が Note 構造要素に使用されている場合、結果のドキュメントは PDF/UA に準拠しません。
//note3.ClearId();
//タグ付き PDF ドキュメントを保存
document.Save(outFile);
//PDF/UA準拠の確認
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントにノート構造要素を作成する方法を学習しました。構造化されたノート要素を使用すると、PDF ドキュメントに追加の構造化された情報を追加できます。

### よくある質問

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメントにノート構造要素を作成する目的は何ですか?

A: Aspose.PDF for .NET を使用して PDF ドキュメントに注釈構造要素を作成すると、ドキュメントのコンテンツに構造化された注釈を追加できます。これらの注釈は、コンテンツの特定の部分に対する追加のコンテキスト、説明、または参照を提供できます。

#### Q: Aspose.PDF ライブラリは、PDF ドキュメント内のメモ構造要素の作成にどのように役立ちますか?

A: Aspose.PDF for .NET は、PDF ドキュメントをプログラムで作成、操作、変換する機能を提供する強力なライブラリです。このチュートリアルでは、ライブラリのマークされたコンテンツ構造機能を使用して、PDF ドキュメントのコンテンツ内に構造化されたメモ要素を作成します。

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメントにノート構造要素を作成するための前提条件は何ですか?

A: 始める前に、.NET フレームワークとともに Visual Studio がインストールされており、プロジェクトで .NET 用の Aspose.PDF ライブラリが参照されていることを確認してください。

#### Q: 提供された C# コードはどのようにして PDF ドキュメントのコンテンツ内にノート構造要素を作成しますか?

A: このコードは、PDF ドキュメントを作成し、ノート構造化要素を定義して段落に追加する方法を示しています。各ノートは Aspose.PDF が提供するメソッドを使用して作成されるため、構造化ノートをコンテンツに組み込むことができます。

#### Q: 作成したノート構造要素のコンテンツとプロパティをカスタマイズできますか?

A: はい、Aspose.PDF ライブラリが提供するメソッドとプロパティを使用して、ノート構造要素のコンテンツとプロパティをカスタマイズできます。コードでは、ノート要素のテキストと ID を設定する方法が示されていますが、必要に応じてさらにカスタマイズできます。

#### Q: ノート構造要素とドキュメントのコンテンツ間の階層関係はどのように確立されますか?

 A: 階層関係は、段落などの他の構造化要素の子として注釈構造要素を追加することによって確立されます。コードでは、注釈要素は段落要素に追加されます。`AppendChild`方法。

#### Q: ノート構造要素に固有の ID を割り当てることはできますか?

A: はい、ノート構造要素に一意のIDを割り当てることができます。`SetId`メソッド。このコードは、ノート要素の ID を一意の値に設定する方法を示しています。

#### Q: ノート構造要素に重複した ID を割り当てようとするとどうなりますか?

A: ノート構造要素に重複した ID を割り当てようとすると、例外が発生します。チュートリアルで提供されているコードには、このシナリオを説明するコメントが含まれています。

#### Q: ノート構造要素を作成するときに PDF/UA 準拠を確保するにはどうすればよいですか?

 A: チュートリアルで提供されるコードは、PDF/UA準拠を検証する方法を示しています。`Validate`方法。ドキュメントを PDF/UA 標準に照らして検証することで、追加された注釈構造要素がアクセシビリティ ガイドラインに準拠していることを確認できます。

#### Q: この方法を使用して、既存の PDF ドキュメントにノート構造要素を追加できますか?

A: はい、提供されている方法を変更して、既存の PDF ドキュメントにメモ構造要素を追加できます。新しいドキュメントを作成する代わりに、Aspose.PDF を使用して既存のドキュメントを読み込み、同様の手順に従ってメモ要素を追加します。
