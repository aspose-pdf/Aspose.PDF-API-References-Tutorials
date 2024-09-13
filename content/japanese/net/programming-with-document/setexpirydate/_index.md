---
title: PDF ファイルに有効期限を設定する
linktitle: PDF ファイルに有効期限を設定する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルに有効期限を設定する方法を学びます。このステップバイステップ ガイドを使用してドキュメントのセキュリティを強化します。
type: docs
weight: 300
url: /ja/net/programming-with-document/setexpirydate/
---
## 導入

今日のデジタル時代では、ドキュメントの管理とセキュリティ保護がこれまで以上に重要になっています。特定の日付以降に自動的にアクセスできなくなる PDF を送信することを想像してみてください。まるで魔法のようですね。Aspose.PDF for .NET を使用すると、PDF ファイルの有効期限を簡単に設定できます。この機能は、特定の期間後に制限する必要がある機密文書に特に役立ちます。このチュートリアルでは、PDF ファイルに有効期限を設定するプロセスを段階的に説明します。では、コーディングの帽子をかぶって、早速始めましょう。

## 前提条件

始める前に、いくつか準備しておくべきことがあります。

1. 開発環境: .NET 開発環境が設定されていることを確認します。Visual Studio または .NET をサポートするその他の IDE を使用できます。
2.  Aspose.PDF for .NET: Aspose.PDFライブラリをインストールする必要があります。まだインストールしていない場合は、以下からダウンロードできます。[ここ](https://releases.aspose.com/pdf/net/).
3. C# の基礎知識: このチュートリアルでは、C# プログラミングの基礎知識があることを前提としています。C# を初めて使用する場合でも心配はいりません。シンプルでわかりやすい内容にしていきます。

## パッケージのインポート

Aspose.PDF を使い始めるには、C# プロジェクトに必要な名前空間をインポートする必要があります。手順は次のとおりです。

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

これらの名前空間により、Aspose.PDF で PDF ドキュメントを操作するために必要なコア機能にアクセスできるようになります。

## ステップ1: ドキュメントディレクトリを設定する

まず最初に、ドキュメント ディレクトリへのパスを指定する必要があります。これは、出力 PDF が保存される場所です。 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

交換する`"YOUR DOCUMENT DIRECTORY"` PDF ファイルを保存する実際のパスを入力します。これは、プログラムに「ここがファイルの保存場所です」と指示するようなものです。

## ステップ2: ドキュメントオブジェクトのインスタンスを作成する

次に、新しいインスタンスを作成する必要があります。`Document`クラス。これは PDF を作成するキャンバスです。

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

考えてみてください`Document`オブジェクトを白紙として表示します。好きなようにコンテンツを追加できます。

## ステップ3: PDFにページを追加する

ドキュメントの設定が完了したら、次はページを追加します。ここにコンテンツを配置します。

```csharp
doc.Pages.Add();
```

PDF に新しいページが作成されました。これは、考えを書き留めることができるノートブックに新しいページを追加するようなものです。

## ステップ4: ページにテキストを追加する

テキストを追加して、このページをもう少し面白くしてみましょう。シンプルな「Hello World」メッセージを追加します。

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

このコード行は、PDF の最初のページにテキスト フラグメントを追加します。ページの先頭にタイトルを書くようなものです。

## ステップ5: 有効期限のJavaScriptを作成する

次は楽しい部分です。PDF の有効期限をチェックする JavaScript アクションを作成します。現在の日付が有効期限を超過している場合は、ユーザーに警告メッセージが表示されます。

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
```

何が起こっているか見てみましょう:
- 有効期限の年と月を定義します。
- 今日の日付を取得します。
- 今日の日付と有効期限を比較します。
- 今日の日付が有効期限を過ぎている場合は、メッセージがポップアップ表示されます。

## ステップ6: JavaScriptをPDFオープンアクションとして設定する

ここで、JavaScript アクションを PDF ドキュメントのオープンアクションとして設定する必要があります。これは、PDF が開かれるとすぐに JavaScript が実行されることを意味します。

```csharp
doc.OpenAction = javaScript;
```

この行は、誰かが PDF を開いたときに JavaScript を実行するように指示します。カレンダーを開いたらすぐに鳴るリマインダーを設定するようなものです。

## ステップ7: PDFドキュメントを保存する

最後に、有効期限機能を使用して PDF ドキュメントを保存します。 

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
doc.Save(dataDir);
```

この行は、PDF を「SetExpiryDate_out.pdf」という名前で指定されたディレクトリに保存します。完成したアートワークを額縁に入れるようなものです。

## 結論

これで完了です。Aspose.PDF for .NET を使用して有効期限付きの PDF ファイルを作成できました。この機能はセキュリティを強化するだけでなく、機密情報を管理下に置くことも保証します。契約書、レポート、その他の重要な文書を送信する場合、有効期限を設定すると状況が一変します。

## よくある質問

### Aspose.PDF for .NET とは何ですか?
Aspose.PDF for .NET は、開発者が .NET アプリケーションで PDF ドキュメントを作成、操作、変換できるようにする強力なライブラリです。

### Aspose.PDF を無料で使用できますか?
はい、Aspose.PDFの無料試用版をご利用いただけます。ダウンロードできます。[ここ](https://releases.aspose.com/).

### Aspose.PDF を購入するにはどうすればよいですか?
Aspose.PDFは、[購入ページ](https://purchase.aspose.com/buy).

### サポートが必要な場合はどうすればいいですか?
ご質問やサポートが必要な場合は、[Aspose サポート フォーラム](https://forum.aspose.com/c/pdf/10).

### Aspose.PDF の一時ライセンスを取得できますか?
はい、一時ライセンスを申請できます[ここ](https://purchase.aspose.com/temporary-license/).