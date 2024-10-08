---
title: イラスト構造要素
linktitle: イラスト構造要素
second_title: Aspose.PDF for .NET API リファレンス
description: ステップバイステップのチュートリアルに従って、Aspose.PDF for .NET でイラスト要素を含む構造化 PDF を作成します。
type: docs
weight: 100
url: /ja/net/programming-with-tagged-pdf/illustration-structure-elements/
---
## 導入

.NET アプリケーションで、魅力的で構造化された PDF を作成する準備はできていますか? コンテンツのタグ付けが必要なプロジェクトに取り組んでいる場合でも、単に PDF を次のレベルに引き上げたい場合でも、Aspose.PDF for .NET には、イラスト構造要素を操作するために必要なすべてのツールが用意されています。このチュートリアルでは、最も複雑な部分も明確に理解できるように、プロセスを段階的に説明します。

## 前提条件

詳細に入る前に、スムーズに進めるために必要なものがすべて揃っていることを確認しましょう。

1.  Aspose.PDF for .NET – Aspose.PDFライブラリをインストールする必要があります。まだインストールしていない場合は、[ここからダウンロード](https://releases.aspose.com/pdf/net/)まずは試してみたい場合は、[無料トライアル](https://releases.aspose.com/).
2. Visual Studio – C# でコーディングするため、Visual Studio または互換性のある IDE がインストールされていることを確認してください。
3. .NET Framework – Aspose.PDF for .NET と互換性のあるバージョンがあることを確認してください。
4. 一時ライセンス – Aspose.PDFは試用モードではいくつかの制限がありますので、[一時ライセンス](https://purchase.aspose.com/temporary-license/)全機能のロックを解除します。

以上です。必要な名前空間をインポートしてコーディングを進めましょう。

## 名前空間のインポート

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

これが基礎です。これらの名前空間をインポートしないと、Aspose.PDF の機能を操作したり、タグ付き PDF コンテンツを処理したりすることはできません。では、手順を詳しく見ていきましょう。

## ステップ1: ドキュメントディレクトリの設定

PDF の作成を開始する前に、ファイルを保存するドキュメント ディレクトリへのパスを指定する必要があります。これは、画像やその他のアセットが保存されるシステム上のフォルダーです。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

このステップはシンプルですが、重要です。プログラムに、作業するファイルの場所と保存場所を指示します。PDFのホームベースを用意するようなものです。`"YOUR DOCUMENT DIRECTORY"`マシン上の実際のパスを使用します。

## ステップ2: 新しいPDFドキュメントを作成する

次に、PDF ドキュメントを作成します。この手順では、空の PDF ドキュメントを作成し、後続の手順でこれを変更および拡張します。
 ドキュメントを作成する

```csharp
Document document = new Document();
```

この行は魔法のようなものです。完全に空白の新しい PDF ファイルを作成し、コンテンツを追加するのを待ちます。新しいキャンバスを開くようなものだと考えてください。

## ステップ3: タグ付きPDFコンテンツにアクセスする

イラスト構造要素を操作するには、ドキュメントのタグ付きコンテンツを活用する必要があります。これにより、特定のタグを定義して、PDF をより構造化してアクセスしやすくすることができます。

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

ここで魔法が起こるのです！`TaggedContent`オブジェクトを使用すると、PDF 内の要素がどのように解釈されるかを定義できます。アクセシビリティや構造を扱う場合、この手順は非常に重要です。

## ステップ4: ドキュメントのタイトルと言語を設定する

構造化された PDF を作成するため、タイトルと言語を定義することが不可欠です。これにより、アクセシビリティが向上するだけでなく、ドキュメントがよりプロフェッショナルで検索しやすくなります。

```csharp
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
```

タイトルと言語を指定すると、本質的に PDF に個性を与えることになります。タイトルはドキュメントのプロパティに表示され、言語を設定するとスクリーン リーダーやその他のアクセシビリティ ツールとの互換性が確保されます。

## ステップ5: イラスト（図）要素の作成

次は、イラストを追加するという楽しい部分です。この場合は、画像、代替テキストの説明、タイトルを含む図要素を作成します。

```csharp
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
```

このコードは新しい図要素を作成し、それをドキュメントのルート要素に追加します。これは、ドキュメントに画像プレースホルダーを追加するものと考えてください。

## ステップ6: 代替テキスト、タイトル、画像の追加

PDF がアクセス可能であることを確認するには、イラストに代替テキストとタイトルを含める必要があります。画像も添付します。

```csharp
figure1.AlternativeText = "Figure One";
figure1.Title = "Image 1";
figure1.SetTag("Fig1");
figure1.SetImage(dataDir + "image.jpg");
```

これが最後の仕上げです。画像に説明的な代替テキスト（スクリーンリーダーに便利です）とタイトルを付け、実際の画像ファイルを設定します。`SetTag`メソッドは図にタグを付け、後で参照しやすくします。

重要な注意: 画像のパスが`SetImage`マシン上の有効なイメージ ファイルを指します。

## ステップ7: タグ付きPDF文書を保存する

すべてのコンテンツを追加して構造化したら、PDF を保存します。この手順ですべてが確定し、実際のファイルが生成されます。

```csharp
document.Save(dataDir + "IllustrationStructureElements.pdf");
```

簡単ですよね? このコマンドは、これまでに行ったすべての作業を取得し、前に指定したディレクトリに新しい PDF ファイルを作成します。次に、フォルダーを確認すると、イラスト要素を含む構造化された PDF が完成します。

## 結論

おめでとうございます! Aspose.PDF for .NET を使用して、イラスト構造要素を含むタグ付き PDF を作成する方法を学習しました。このアプローチにより、PDF は見た目が魅力的になるだけでなく、構造化され、アクセスしやすくなります。コンテンツにタグを付け、代替テキストを追加することで、支援技術を使用するユーザーを含むすべてのユーザーがドキュメントを楽しめるようになります。

## よくある質問

### タグ付き PDF コンテンツとは何ですか?
タグ付き PDF は、見出し、段落、図などのさまざまな要素を識別するためのタグまたはラベルが含まれ、ドキュメントのアクセシビリティが向上した PDF です。

### 代替テキストを設定するとどのような効果がありますか?
代替テキストは画像の説明を提供し、スクリーン リーダーで読み取ることができるため、視覚障害のあるユーザーのアクセシビリティが向上します。

### タグ付き PDF に複数の画像を追加できますか?
はい！複数作成できます`FigureElement`オブジェクトを作成し、単一の画像の場合と同じように、各オブジェクトをドキュメントに追加します。

### Aspose.PDF for .NET を使用するにはライセンスが必要ですか?
はい、Aspose.PDFは有料のライブラリですが、[一時ライセンス](https://purchase.aspose.com/temporary-license/)または[無料トライアル](https://releases.aspose.com/).

### PDF を作成した後に図の要素を変更することは可能ですか?
PDF を保存すると、それを直接変更することはできませんが、Aspose.PDF を使用してドキュメントを再度開き、変更を加えて再度保存することができます。