---
title: PDF ファイルにローカル ハイパーリンクを作成する
linktitle: PDF ファイルにローカル ハイパーリンクを作成する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルにローカル ハイパーリンクを簡単に作成する方法を、ステップ バイ ステップ ガイドで学習します。
type: docs
weight: 40
url: /ja/net/programming-with-links-and-actions/create-local-hyperlink/
---
## 導入

このガイドでは、Aspose.PDF for .NET を使用して PDF ファイルにローカル ハイパーリンクを作成する手順を説明します。各手順を明確に説明しているので、PDF 操作の世界に不慣れな場合でも、簡単に理解できます。

## 前提条件

コードに飛び込む前に、必要なものがすべて揃っていることを確認しましょう。

1.  Visual Studio: .NETアプリケーションを開発するにはこれが必要です。[Webサイト](https://visualstudio.microsoft.com/).
2.  Aspose.PDF for .NET: このライブラリは、[ダウンロードリンクはこちら](https://releases.aspose.com/pdf/net/)PDF 操作のための豊富な機能が搭載されています。
3. C# の基礎知識: C# プログラミングに少し精通していると役立ちますが、心配しないでください。コードを 1 行ずつ確認していきます。
4.  .NET Framework: .NET Frameworkがマシンにインストールされていることを確認してください。要件はAspose.PDFで確認できます。[ドキュメント](https://reference.aspose.com/pdf/net/).

これらの前提条件が設定されたら、PDF ドキュメントにローカル ハイパーリンクを作成する方法を学習する準備が整います。

## パッケージのインポート

準備ができたので、C# プロジェクトに必要なパッケージをインポートします。Aspose.PDF ライブラリには必要なクラスがすべて含まれています。手順は次のとおりです。

### プロジェクトを開く

Visual Studio で既存の .NET プロジェクトを開くか、新しいプロジェクトを作成します。最初から始める場合は、起動画面から [新しいプロジェクトの作成] を選択します。

### Aspose.PDF への参照を追加する

ソリューションエクスプローラーのプロジェクトフォルダの「依存関係」を右クリックします。「NuGetパッケージの管理」を選択し、`Aspose.PDF`最新バージョンをインストールしてください。これにより、PDF の作成と操作に必要なすべてのツールが提供されます。

### 名前空間のインポート

.cs ファイルの先頭に、次のように Aspose.PDF ライブラリの using ディレクティブを追加します。

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

こうすることで、ライブラリの機能にアクセスできるようになります。

ローカル ハイパーリンクを作成するプロセスを簡単なステップに分解してみましょう。各ステップは、その背後にあるロジックを理解できるように包括的に説明されます。

## ステップ1: ドキュメントインスタンスの設定

この手順では、操作する PDF ファイルを表す Document クラスの新しいインスタンスを作成します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; //ドキュメントディレクトリを設定する
Document doc = new Document(); //ドキュメントインスタンスを作成する
```
の`dataDir`変数は新しく作成されたPDFが格納される場所です。`"YOUR DOCUMENT DIRECTORY"`システム上の実際のパスに置き換えてください。`Document`クラスは、ページとリンクを追加できる新しい PDF ドキュメントを作成します。

## ステップ2: ドキュメントにページを追加する

次に、PDF ドキュメントにページを追加します。 

```csharp
Page page = doc.Pages.Add(); //ページコレクションにページを追加する
```
の`Pages.Add()`メソッドはドキュメントに新しいページを追加します。ここにすべてのコンテンツが保存されます。

## ステップ3: テキストフラグメントを作成する

次に、クリック可能なリンクとして機能するテキストを作成しましょう。

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
```
の`TextFragment` PDF 内のテキストのセグメントを表します。ここでは、ユーザーに 7 ページ目に移動することを示すリンクを作成しています。

## ステップ4: ローカルハイパーリンクを作成する

ここで魔法が起こります! テキスト フラグメントが指す場所を指示するローカル ハイパーリンクを作成する必要があります。

```csharp
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink(); //ローカルハイパーリンクを作成する
link.TargetPageNumber = 7; //リンクインスタンスのターゲットページを設定する
text.Hyperlink = link; //TextFragmentハイパーリンクを設定する
```
の`LocalHyperlink`クラスは同じ文書内の他のページを指すために使われます。`TargetPageNumber` 7 では、ハイパーリンクをクリックすると特定のページにジャンプするように指示します。

## ステップ5: ページにテキストフラグメントを追加する

ハイパーリンクを設定したら、作成したページにテキスト フラグメントを追加します。

```csharp
page.Paragraphs.Add(text); //ページの段落コレクションにテキストを追加する
```
この行は、クリック可能なテキストをページの段落のコレクションに追加します。

## ステップ 6: 別のテキスト フラグメントを作成する (オプション)

ページ 1 に戻るためのハイパーリンクをもう 1 つ追加してみましょう。

```csharp
text = new TextFragment("link page number test to page 1"); //新しいテキストフラグメントを作成する
text.IsInNewPage = true; //新しいページに追加
```
新しいものを作成する`TextFragment`2番目のリンクでは、`IsInNewPage` true に設定すると、このテキストは新しいページに配置されることを示します。

## ステップ 7: 2 番目のローカル ハイパーリンクを設定する

前と同じように、ページ 1 に別のローカル ハイパーリンクを作成します。

```csharp
link = new LocalHyperlink(); //別のローカルハイパーリンクインスタンスを作成する
link.TargetPageNumber = 1; //2番目のハイパーリンクのターゲットページを設定する
text.Hyperlink = link; //2番目のTextFragmentのリンクを設定する
```
このハイパーリンクはページ 1 を対象としており、ユーザーは 2 ページ目に到達したときに元のページに戻ることができます。

## ステップ8: 新しいページに2番目のテキストフラグメントを追加する

それでは、このテキストをページに追加してみましょう。

```csharp
page.Paragraphs.Add(text); //ページオブジェクトの段落コレクションにテキストを追加する
```
手順 5 と同様に、この行は新しく作成されたページに新しいハイパーリンク テキストを追加します。

## ステップ9: ドキュメントを保存する

ついに、あなたの努力を保存する時が来ました! 

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf"; //出力ファイル名を指定
doc.Save(dataDir); //更新されたドキュメントを保存する
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);
```
これはディレクトリパスとファイル名を組み合わせたものです。`Save()`メソッドによりドキュメントが保存され、確認メッセージが表示され、すべてがスムーズに実行されたことが通知されます。

## 結論

Aspose.PDF for .NET を使用して PDF ファイルにローカル ハイパーリンクを作成するのは、単なるクールなトリックではありません。ナビゲーションとユーザー エクスペリエンスを強化する実用的な機能です。これで、読者が必要な情報に直接アクセスできるようにするための知識が身につきました。最初の例えを思い出してください。無限のページをさまよう迷える魂はもうありません。

## よくある質問

### Aspose.PDF for .NET とは何ですか?
Aspose.PDF for .NET は、開発者が .NET フレームワークを使用してプログラムで PDF ドキュメントを作成、操作、変換できるようにするライブラリです。

### 外部 Web ページへのハイパーリンクを作成できますか?
はい、Aspose.PDF は、PDF 内のローカル ハイパーリンクの他に、外部 URL へのハイパーリンクの作成もサポートしています。

### Aspose.PDF の無料トライアルはありますか?
もちろんです！無料トライアルは[サイト](https://releases.aspose.com/).

### Aspose はどのようなプログラミング言語をサポートしていますか?
AsposeはJava、Cなどさまざまなプログラミング言語用のライブラリを提供しています。++、Python などがあります。

### Aspose 製品のサポートを受けるにはどうすればよいですか?
サポートを受けるには、[Aspose フォーラム](https://forum.aspose.com/c/pdf/10).