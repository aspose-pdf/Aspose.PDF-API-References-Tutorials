---
title: カスタムタグ名
linktitle: カスタムタグ名
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET でカスタム タグ名を使用するためのステップ バイ ステップ ガイド。カスタム タグを使用して PDF の構造を改善します。
type: docs
weight: 90
url: /ja/net/programming-with-tagged-pdf/custom-tag-name/
---
## 導入

今日のデジタル時代では、PDF はどこにでもあります。レポートからマニュアルまで、さまざまな業界でさまざまな目的に使用されています。しかし、これらのドキュメントが障害のある人を含むすべての人にアクセス可能であることを確認することは非常に重要です。ここで、タグ付き PDF が役立ちます。これにより、スクリーン リーダーやその他の支援技術がドキュメントのコンテンツを効果的に解釈しやすくなります。

## 前提条件

コーディングを始める前に、すべての準備が整っていることを確認することが重要です。必要なものは次のとおりです。

1. Visual Studio - 最新バージョンであればどれでも構いませんが、最適な機能を得るには最新バージョンを使用することをお勧めします。
2.  Aspose.PDF for .NET - 最新バージョンは、[ダウンロードリンク](https://releases.aspose.com/pdf/net/).
3. C# の基礎知識 - C# プログラミングの基礎を理解していると、コードを実装する際に役立ちます。

## パッケージのインポート

環境を設定したら、次のステップでは Aspose.PDF を使用するために必要なパッケージをインポートします。これは、Aspose.PDF ライブラリをプロジェクトに追加することで実行できます。

### NuGet 経由で Aspose.PDF をインストールする

1. Visual Studio プロジェクトを開きます。まだプロジェクトを作成していない場合は、新しいプロジェクトを作成してください。
2. NuGet パッケージ マネージャーにアクセスします。ソリューション エクスプローラーでプロジェクトを右クリックし、「NuGet パッケージの管理」を選択します。
3. Aspose.PDF を検索: 検索バーに「Aspose.PDF」と入力します。
4. パッケージをインストールします: 「インストール」をクリックして、パッケージをプロジェクトに追加します。インストールしたら、準備完了です。

### Using ディレクティブの追加

コードで Aspose の機能を利用するには、ファイルの先頭に必要な using ディレクティブを追加する必要があります。

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

これらの手順を完了すると、タグ付き PDF の作成に取り組む準備が整います。

これですべての設定が完了したので、メインのタスクであるタグ付き PDF ドキュメントの作成に取り掛かりましょう。Aspose.PDF for .NET を使用してこれを実行する手順を次に示します。

## ステップ1: ドキュメントディレクトリを定義する

まず、PDF を保存するパスを指定する必要があります。ここでデータ ディレクトリを定義します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

説明: 「YOUR DOCUMENT DIRECTORY」を、PDF ファイルを保存する実際のパスに置き換えます。実行時例外を回避するには、このディレクトリに書き込み権限を持っていることが重要です。

## ステップ2: 新しいPDFドキュメントを作成する

次に、`Document`クラス。

```csharp
Document document = new Document();
```

説明: この行は、新しい PDF ドキュメントを初期化します。これは、PDF のコンテンツを描画する空白のキャンバスを作成するものと考えてください。

## ステップ3: タグ付きコンテンツを作成する

さて、いよいよタグ付けの核心に迫ります。ドキュメントのタグ付けされたコンテンツを取得します。

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

説明:`TaggedContent`オブジェクトを使用すると、コンテンツを階層的に整理して、PDF の論理構造とアクセシビリティを操作できます。

## ステップ4: タイトルと言語を設定する

次に、ドキュメントのタイトルと言語属性を設定できます。これにより、スクリーン リーダーがドキュメントを正しく処理できるようになります。

```csharp
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
```

説明: ここでは、この PDF を読むすべての人にタイトルと言語を知らせます。これは、特にアクセシビリティ ツールの理解に役立ちます。

## ステップ5: 論理構造要素を作成する

次に、PDF 内に構造化された要素を作成します。

```csharp
SectElement sect = taggedContent.CreateSectElement();
taggedContent.RootElement.AppendChild(sect);
```

説明: このステップでは、コンテンツを追加できるセクション要素を導入します。`RootElement`あなたのホームベースです。

## ステップ6: 段落要素を作成する

ここで、さまざまな段落要素を作成し、そのテキスト コンテンツを設定します。

```csharp
ParagraphElement p1 = taggedContent.CreateParagraphElement();
ParagraphElement p2 = taggedContent.CreateParagraphElement();
ParagraphElement p3 = taggedContent.CreateParagraphElement();
ParagraphElement p4 = taggedContent.CreateParagraphElement();
p1.SetText("P1. ");
p2.SetText("P2. ");
p3.SetText("P3. ");
p4.SetText("P4. ");
```

説明: 各段落は物語の文章に似ており、場面を設定してドキュメントに意味を与えます。

## ステップ7: 段落にタグを割り当てる

PDF のアクセシビリティのために、各段落に適切なタグを付けることが重要です。

```csharp
p1.SetTag("P1");
p2.SetTag("Para");
p3.SetTag("Para");
p4.SetTag("Paragraph");
```

説明: タグでラベルを付けることにより、支援技術がコンテンツの構造を理解できるようになります。これは、支援技術に領域をナビゲートするためのロードマップを提供するようなものです。

## ステップ8: セクションに段落を追加する

ここで、これらの段落を以前に作成したセクションに追加します。

```csharp
sect.AppendChild(p1);
sect.AppendChild(p2);
sect.AppendChild(p3);
sect.AppendChild(p4);
```

説明: このアクションは、セクション内の段落を整理し、フローを論理的かつわかりやすくします。

## ステップ9: スパン要素を作成する

段落と同様に、スパンはテキスト コンテンツに細かい詳細を追加します。

```csharp
SpanElement span1 = taggedContent.CreateSpanElement();
SpanElement span2 = taggedContent.CreateSpanElement();
SpanElement span3 = taggedContent.CreateSpanElement();
SpanElement span4 = taggedContent.CreateSpanElement();
span1.SetText("Span 1.");
span2.SetText("Span 2.");
span3.SetText("Span 3.");
span4.SetText("Span 4.");
```

説明: スパンは詳細を微調整するようなものです。各段落内で伝えたい内容に具体性を加えます。

## ステップ10: スパン要素にタグを割り当てる

段落の場合と同様に、理解を助けるために span 要素にタグを付ける必要があります。

```csharp
span1.SetTag("SPAN");
span2.SetTag("Sp");
span3.SetTag("Sp");
span4.SetTag("TheSpan");
```

説明: スパンを適切にタグ付けすると、すべてのニュアンスが正確に表現され、そのドキュメントを閲覧するすべての人にとって充実した内容のドキュメントが作成されます。

## ステップ11: 段落にスパンを追加する

次に、それぞれの段落に span 要素を追加してみましょう。

```csharp
p1.AppendChild(span1);
p2.AppendChild(span2);
p3.AppendChild(span3);
p4.AppendChild(span4);
```

説明: この統合により、本に脚注を追加して理解を深めるのと同じように、追加情報を重ねて段落が強化されます。

## ステップ12: タグ付きPDF文書を保存する

ついに傑作を保存する時が来ました!

```csharp
document.Save(dataDir + "CustomTag.pdf");
```

説明: この行は、タグ付き PDF を指定されたディレクトリに保存します。これで、タグ付き PDF ドキュメントの作成が完了しました。

## 結論

Aspose.PDF for .NET を使用してタグ付き PDF ドキュメントを作成するのは、単にコンテンツを追加するだけではありません。すべてのユーザーが利用できるエクスペリエンスを作り出すことです。わずか数ステップで、ドキュメントがすべての人に伝わるようにし、障壁を取り除き、理解を深めることができます。 

## よくある質問

### タグ付き PDF とは何ですか?  
タグ付き PDF には、ドキュメントのコンテンツの構造とアクセシビリティを記述する追加のメタデータが含まれており、支援技術による解釈が容易になります。

### Aspose.PDF for .NET が必要な理由は何ですか?  
Aspose.PDF for .NET は、開発者が豊富な機能を使用して PDF ドキュメントをプログラムで作成、変更、操作できるようにする強力なライブラリです。

### Aspose.PDF の試用版を入手するにはどうすればよいですか?  
 Aspose.PDFの無料トライアルは、次のサイトから入手できます。[このリンク](https://releases.aspose.com/).

### Aspose.PDF のサポートを受けることはできますか?  
はい、サポートを受けるには[Aspose フォーラム](https://forum.aspose.com/c/pdf/10).

### Aspose.PDF の詳細なドキュメントはどこで入手できますか?  
完全なドキュメントは以下にあります。[ここ](https://reference.aspose.com/pdf/net/).