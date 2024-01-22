---
title: 音符構造要素の作成
linktitle: 音符構造要素の作成
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ドキュメント内に構造化されたメモ アイテムを作成するためのステップバイステップ ガイド。
type: docs
weight: 30
url: /ja/net/programming-with-tagged-pdf/create-note-structure-element/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内にメモ構造要素を作成する方法について段階的なガイドを提供します。 Aspose.PDF は、PDF ドキュメントをプログラムで作成、操作、変換できる強力なライブラリです。 Aspose.PDF のマークされたコンテンツ構造機能を使用すると、PDF ドキュメントに構造化されたメモを追加できます。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

1. Visual Studio には .NET Framework がインストールされています。
2. .NET 用の Aspose.PDF ライブラリ。

## ステップ 1: プロジェクトのセットアップ

まず、Visual Studio で新しいプロジェクトを作成し、Aspose.PDF for .NET ライブラリへの参照を追加します。 Aspose 公式 Web サイトからライブラリをダウンロードして、マシンにインストールできます。

## ステップ 2: 必要な名前空間をインポートする

C# コード ファイルで、Aspose.PDF が提供するクラスとメソッドにアクセスするために必要な名前空間をインポートします。

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## ステップ 3: PDF ドキュメントとノート構造化要素の作成

次のコードを使用して PDF ドキュメントを作成し、メモ構造化要素を追加します。

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

このコードは空の PDF ドキュメントを作成し、構造化されたメモ要素を段落に追加します。各メモは、Aspose.PDF が提供するメソッドを使用して作成されます。

## ステップ 4: PDF ドキュメントを保存する

次のコードを使用して PDF ドキュメントを保存します。

```csharp
document. Save(outFile);
```

このコードは、メモ構造化要素を含む PDF ドキュメントを指定されたファイルに保存します。

### Aspose.PDF for .NET を使用してノート構造要素を作成するためのサンプル ソース コード 

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
//PDFドキュメントの作成
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
//段落要素の追加
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
//Note要素の追加
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
//Note要素の追加
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
//Note要素の追加
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
//例外をスローする必要があります - Aspose.Pdf.Tagged.TaggedException : ID='note_002' の構造要素がすでに存在します
//note3.SetId("note_002");
// Note 構造要素に ClearId() が使用されている場合、結果のドキュメントは PDF/UA に準拠していません
//note3.ClearId();
//タグ付き PDF ドキュメントを保存
document.Save(outFile);
//PDF/UA 準拠の確認
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内にノート構造要素を作成する方法を学習しました。構造化メモ要素を使用すると、PDF ドキュメントに追加の構造化情報を追加できます。

### よくある質問

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメント内にノート構造要素を作成する目的は何ですか?

A: Aspose.PDF for .NET を使用して PDF ドキュメント内にメモ構造要素を作成すると、ドキュメントのコンテンツに構造化されたメモを追加できます。これらのメモは、コンテンツの特定の部分への追加のコンテキスト、説明、または参照を提供できます。

#### Q: Aspose.PDF ライブラリは、PDF ドキュメント内でのノート構造要素の作成をどのように支援しますか?

A: Aspose.PDF for .NET は、PDF ドキュメントをプログラムで作成、操作、変換する機能を提供する強力なライブラリです。このチュートリアルでは、ライブラリのマーク付きコンテンツ構造機能を使用して、PDF ドキュメントのコンテンツ内に構造化されたメモ要素を作成します。

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメント内にノート構造要素を作成するための前提条件は何ですか?

A: 始める前に、Visual Studio が .NET Framework とともにインストールされていること、およびプロジェクト内で .NET 用の Aspose.PDF ライブラリが参照されていることを確認してください。

#### Q: 提供されている C# コードは、PDF ドキュメントのコンテンツ内にノート構造要素をどのように作成しますか?

A: このコードは、PDF ドキュメントを作成し、メモ構造化要素を定義し、それらを段落に追加する方法を示しています。各メモは Aspose.PDF が提供するメソッドを使用して作成され、構造化されたメモをコンテンツに組み込むことができます。

#### Q: 作成したノート構造要素のコンテンツとプロパティをカスタマイズできますか?

A: はい、Aspose.PDF ライブラリが提供するメソッドとプロパティを使用して、ノート構造要素のコンテンツとプロパティをカスタマイズできます。このコードは、メモ要素のテキストと ID を設定する方法を示していますが、必要に応じてさらにカスタマイズできます。

#### Q: ノート構造要素とドキュメントのコンテンツとの間に階層関係はどのように確立されますか?

 A: 階層関係は、ノート構造要素を段落などの他の構造化要素の子として追加することによって確立されます。コードでは、note 要素が段落要素に追加されます。`AppendChild`方法。

#### Q: ノート構造要素に一意の ID を割り当てることはできますか?

A: はい、メモの構造要素に一意の ID を割り当てることができます。`SetId`方法。このコードは、note 要素の ID を一意の値に設定する方法を示しています。

#### Q: ノート構造要素に重複した ID を割り当てようとするとどうなりますか?

A: メモ構造要素に重複した ID を割り当てようとすると、例外が発生します。チュートリアルで提供されるコードには、このシナリオを説明するコメントが含まれています。

#### Q: ノート構造要素を作成するときに PDF/UA への準拠を保証するにはどうすればよいですか?

 A: チュートリアルで提供されるコードは、`Validate`方法。 PDF/UA 標準に対してドキュメントを検証することで、追加されたメモ構造要素がアクセシビリティ ガイドラインに準拠していることを確認できます。

#### Q: このアプローチを使用して、既存の PDF ドキュメントにメモ構造要素を追加できますか?

A: はい、提供されているアプローチを変更して、既存の PDF ドキュメントにメモ構造要素を追加できます。新しいドキュメントを作成する代わりに、Aspose.PDF を使用して既存のドキュメントをロードし、同様の手順に従ってメモ要素を追加します。
