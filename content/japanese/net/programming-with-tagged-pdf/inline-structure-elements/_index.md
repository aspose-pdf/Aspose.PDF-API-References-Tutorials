---
title: インライン構造要素
linktitle: インライン構造要素
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET でオンライン構造要素を使用するためのステップバイステップ ガイド。見出しと段落を使用して PDF を整理します。
type: docs
weight: 110
url: /ja/net/programming-with-tagged-pdf/inline-structure-elements/
---
## 導入

今日のデジタル環境では、アクセスしやすく、構造化されたドキュメントを作成することが重要です。PDF をスクロールしてテキストの海に迷い込んだ経験があれば、適切な構成の重要性がおわかりでしょう。PDF 内の要素にタグを付けると、アクセシビリティが向上し、スクリーン リーダーがコンテンツを解釈しやすくなります。このガイドでは、Aspose.PDF for .NET を使用してタグ付き PDF ドキュメントを作成し、ドキュメント構造の最新標準を満たす方法について説明します。

## 前提条件

実際に行動に移る前に、必要な物がすべて揃っていることを確認しましょう。

1. C# の基礎知識: C# プログラミングと .NET フレームワークの基礎に精通していることが必須です。
2. Visual Studio がインストールされている: コードを記述して実行するには、Visual Studio などの IDE が必要です。
3.  Aspose.PDF for .NET: Aspose.PDF for .NETをダウンロードしてインストールしてください。[ダウンロードリンク](https://releases.aspose.com/pdf/net/).
4. 一時ライセンス：これはオプションですが、すべての機能を制限なく評価したい場合は、一時ライセンスを取得することを検討してください。[一時ライセンス](https://purchase.aspose.com/temporary-license/).

これらの前提条件が満たされると、最初のタグ付き PDF ドキュメントを作成する準備が整います。

## パッケージのインポート

まず、必要なパッケージをインポートしましょう。これにより、プロジェクトで Aspose.PDF ライブラリの機能を活用できるようになります。

1. Visual Studio プロジェクトを開きます。
2. Aspose.PDF ライブラリへの参照を追加します。まだ追加していない場合は、NuGet パッケージ マネージャーを使用してインストールできます。
3. C# ファイルの先頭に次の名前空間を含めます。

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

これらのインポートが準備されていれば、成功への準備は完了です。

## コードの詳細: タグ付き PDF を作成するためのステップバイステップ ガイド

準備が整ったので、コードをステップごとに分解してみましょう。ヘッダーや段落などの構造化された要素を含むタグ付き PDF を作成し、アクセシビリティを向上させます。

### ステップ1: ドキュメントディレクトリを設定する

まず、ドキュメントを保存するパスを設定します。整理されたファイル構造を維持することをお勧めします。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; //実際のパスに置き換えてください
```

### ステップ2: PDFドキュメントインスタンスを作成する

次に、`Document` PDF コンテンツのコンテナーとして機能するクラスです。

```csharp
Document document = new Document();
```

### ステップ3: タグ付けされたコンテンツにアクセスする

次に、ドキュメントのタグ付けされたコンテンツにアクセスします。ここで魔法が起こります。コンテンツにタグを付けることで、アクセシビリティが向上します。

```csharp
ITaggedContent taggedContent = document.TaggedContent;    
```

### ステップ4: タイトルと言語を設定する

PDF ドキュメントのタイトルと言語を設定することは、ユーザーとスクリーン リーダーの両方にとって重要です。これにより、ドキュメントの情報量とアクセシビリティが向上します。

```csharp
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
```

### ステップ5: ルート構造要素を取得する

ドキュメントに要素を追加してみましょう。まず、ドキュメントの構造を構築するための基礎となる、タグ付けされたコンテンツのルート構造要素を取得します。

```csharp
StructureElement rootElement = taggedContent.RootElement;
```

### ステップ6: ヘッダー要素を作成する

次に、ヘッダー要素を作成します。これにより、コンテンツを階層的に整理しやすくなります。6 レベルのヘッダーを作成します。

```csharp
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
```

### ステップ7: ルート要素にヘッダーを追加する

ヘッダー要素を作成したら、それをルート要素に追加します。これにより、ドキュメントの構造階層が構築されます。

```csharp
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
```

### ステップ8: 各ヘッダーにテキストを追加する

次に、各ヘッダーにテキストを追加してみましょう。これは簡単なプロセスですが、ドキュメントを有用なものにするためには不可欠です。 

```csharp
// H1
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1. ");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 Header");
h1.AppendChild(spanH12);

//上記のようにH2～H6を繰り返します。
```

### ステップ9: 段落要素を作成する

次に、段落要素を追加しましょう。これが PDF のメインコンテンツ領域として機能します。 

```csharp
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. ");
rootElement.AppendChild(p);
```

### ステップ10: 段落にテキストを追加する

段落要素ができたので、次はテキストを入力します。複数のスパンを追加してコンテンツを構成できます。

```csharp
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit. ");
p.AppendChild(span1);
//必要に応じてスパンを追加し続ける
```

### ステップ11: タグ付きPDF文書を保存する

最後に、すべてのコンテンツを追加したら、ドキュメントを保存する必要があります。これで終わりです。

```csharp
document.Save(dataDir + "InlineStructureElements.pdf");
```

出来上がり! 構造化されアクセス可能なタグ付き PDF ドキュメントが完成しました。

## 結論

タグ付き PDF ドキュメントの作成は難しそうに思えるかもしれませんが、Aspose.PDF for .NET を使えば簡単です。このステップ バイ ステップ ガイドに従うことで、ドキュメント構造の基本を習得できます。PDF に適切なタグを付けるとアクセシビリティが向上し、貴重なコンテンツが幅広いユーザーに届くようになります。さあ、PDF を美しいだけでなく、ユーザー フレンドリーなものにしましょう。

## よくある質問

### タグ付き PDF とは何ですか?
タグ付き PDF は、ドキュメントの構造に関する情報が含まれた PDF であり、障害を持つユーザーがアクセスしやすくなります。

### PDF でタグ付けが重要なのはなぜですか?
タグ付けによりアクセシビリティが向上し、スクリーン リーダーがドキュメントを明確に解釈できるようになり、障害を持つユーザーに優れたエクスペリエンスを提供できるようになります。

### Aspose.PDF を無料で使用できますか?
はい、Aspose.PDF for .NETは、[無料トライアル](https://releases.aspose.com/).

### Aspose.PDF のサポートはどこで受けられますか?
サポートは以下からアクセスできます。[Aspose サポート フォーラム](https://forum.aspose.com/c/pdf/10).

### Aspose.PDF for .NET ライセンスを購入するにはどうすればよいですか?
ライセンスは直接購入することができます[購入ページ](https://purchase.aspose.com/buy).