---
title: タグ付きテキストを含むPDFを作成する
linktitle: タグ付きテキストを含むPDFを作成する
second_title: Aspose.PDF for .NET API リファレンス
description: この包括的なステップバイステップのチュートリアルでは、Aspose.PDF for .NET を使用して、アクセス可能なコンテンツを含むタグ付き PDF を作成する方法を学習します。
type: docs
weight: 50
url: /ja/net/programming-with-tagged-pdf/create-pdf-with-tagged-text/
---
## 導入

今日のデジタル時代では、PDF ドキュメントは、コンテンツを共有および表示するための最も一般的な形式の 1 つになっています。ビジネス レポート、学術論文、ユーザー マニュアルなど、PDF はどこにでもあります。しかし、優れた PDF と優れた PDF を区別するのは、アクセシビリティと構造です。その通りです。タグ付き PDF により、スクリーン リーダーや支援技術がコンテンツを理解し、ナビゲートしやすくなります。このチュートリアルでは、Aspose.PDF for .NET を使用してタグ付き PDF を作成するプロセスを段階的に説明します。 

では、お気に入りの飲み物を手に取り、落ち着いて、タグ付き PDF の世界に飛び込みましょう。

## 前提条件

始める前に、いくつか準備しておく必要があります。

1. Visual Studio - マシンに Visual Studio がインストールされていることを確認してください。.NET をサポートする任意のバージョンを使用できます。
2.  Aspose.PDF for .NET - Aspose.PDF for .NETの最新バージョンをこちらからダウンロードしてください。[Webサイト](https://releases.aspose.com/pdf/net/)無料トライアルを選択して、その機能を試すこともできます。
3. .NET Framework - これらの例は .NET 用に構築されます。互換性のあるバージョンがマシンにインストールされていることを確認してください。
4. C# の基礎知識 - C# プログラミングの知識は、コードを書くときに役立ちます。

すべて揃いましたか? 素晴らしい! コーディングを始めましょう!

## パッケージのインポート

前提条件が整理されたので、楽しい部分、つまり必要なパッケージのインポートに進みましょう。Aspose.PDF を使用するには、ライブラリをプロジェクトに追加する必要があります。 

### 新しいプロジェクトを作成する

まず、Visual Studio を起動し、新しい C# プロジェクトを作成します。

1. Visual Studio を開きます。
2. 「新しいプロジェクトの作成」をクリックします。
3. 「コンソール アプリ (.NET)」を選択し、「次へ」をクリックします。
4. プロジェクトに名前を付けます（例：`TaggedPdfExample`）をクリックして、その場所を設定します。
5. 「作成」をクリックします。

### Aspose.PDF 参照の追加

次に、Aspose.PDF ライブラリを追加します。

1. ソリューション エクスプローラーでプロジェクトを右クリックします。
2. 「NuGet パッケージの管理」を選択します。
3. 「Aspose.PDF」を検索し、最新バージョンをインストールしてください。

### 必要な名前空間をインポートする

メインプログラムファイルの先頭（`Program.cs`)、次の名前空間をインポートします。

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

これですべての設定が完了したので、コードを理解しやすい部分に分解し、タグ付き PDF を段階的に作成しましょう。

## ステップ1: ドキュメントディレクトリを定義する

コーディングを始める前に、PDF ファイルを保存するドキュメント ディレクトリを定義しましょう。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY"; //これをあなたのパスに更新してください
```

交換する`"YOUR DOCUMENT DIRECTORY"`PDF を保存する実際のパスを入力します。

## ステップ2: PDFドキュメントを作成する

新しい PDF ドキュメント インスタンスを作成しましょう。これは、コンテンツを追加する空白のキャンバスを描くようなものです。 

```csharp
// PDFドキュメントを作成
Document document = new Document();
```

## ステップ3: ドキュメントのタグ付けされたコンテンツを取得する

次に、ドキュメントのタグ付けされたコンテンツを取得する必要があります。タグ付けされたコンテンツは、アクセスを可能にする基礎構造であると考えてください。方法は次のとおりです。

```csharp
// TaggedPdfで作業用のコンテンツを取得する
ITaggedContent taggedContent = document.TaggedContent;
```

## ステップ4: ドキュメントのタイトルと言語を設定する

それでは、ドキュメントのタイトルと言語を設定しましょう。これはアクセシビリティにとって非常に重要です。

```csharp
//ドキュメントのタイトルと言語を設定する
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
```

## ステップ5: テキストブロックレベルの構造要素を作成する

ここでコンテンツを作成します。ヘッダーと段落を、ビルディング ブロックのように作成します。

### ステップ5.1: ヘッダー要素を作成する

まず、ヘッダー要素を作成しましょう。

```csharp
//テキストブロックレベルの構造要素を作成する
HeaderElement headerElement = taggedContent.CreateHeaderElement();
headerElement.ActualText = "Heading 1";
```

### ステップ5.2: 段落要素を作成する

次に、段落をいくつか追加しましょう。いくつか追加しておきますが、必要に応じてカスタマイズできます。

```csharp
ParagraphElement paragraphElement1 = taggedContent.CreateParagraphElement();
paragraphElement1.ActualText = "test1";

ParagraphElement paragraphElement2 = taggedContent.CreateParagraphElement();
paragraphElement2.ActualText = "test 2";

ParagraphElement paragraphElement3 = taggedContent.CreateParagraphElement();
paragraphElement3.ActualText = "test 3";

ParagraphElement paragraphElement4 = taggedContent.CreateParagraphElement();
paragraphElement4.ActualText = "test 4";

ParagraphElement paragraphElement5 = taggedContent.CreateParagraphElement();
paragraphElement5.ActualText = "test 5";

ParagraphElement paragraphElement6 = taggedContent.CreateParagraphElement();
paragraphElement6.ActualText = "test 6";

ParagraphElement paragraphElement7 = taggedContent.CreateParagraphElement();
paragraphElement7.ActualText = "test 7";
```

## ステップ6: PDFドキュメントを保存する

最後に、この傑作を保存しましょう。タグ付き PDF を保存する方法は次のとおりです。

```csharp
// PDF文書を保存
document.Save(dataDir + "PDFwithTaggedText.pdf");
```

タグ付き PDF が作成されました。 

## 結論

Aspose.PDF for .NET でタグ付き PDF を作成するのは、一度コツをつかめばとても簡単です。ドキュメントがユーザーフレンドリーになるだけでなく、より幅広いユーザーがアクセスできるようになります。特にコンテンツのアクセシビリティが不可欠な業界の場合は、セマンティック構造を重視すると確実に効果があります。 

## よくある質問

### タグ付き PDF とは何ですか?  
タグ付き PDF には、スクリーン リーダーや支援技術がコンテンツを効果的にナビゲートしやすくする構造化データが含まれています。

### Aspose.PDF を使用するには購入する必要がありますか?  
無料トライアルから始めることもできますが、長期使用にはライセンスが必要です。詳細はこちらをご覧ください。[ここ](https://purchase.aspose.com/buy).

### PDF 内の構造要素をカスタマイズできますか?  
もちろんです！さまざまな要素を操作し、要件に応じて複雑な構造を作成できます。

### Aspose.PDF はすべての .NET アプリケーションと互換性がありますか?  
はい、Aspose.PDF は、.NET Framework、.NET Core など、さまざまな .NET プラットフォームで動作するように設計されています。

### Aspose.PDF のサポートはどこで受けられますか?  
訪問することができます[Aspose サポート フォーラム](https://forum.aspose.com/c/pdf/10)ご質問や問題が発生した場合には、