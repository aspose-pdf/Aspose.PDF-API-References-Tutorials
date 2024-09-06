---
title: PDF ドキュメントに Javascript を追加/削除する
linktitle: ドキュメントにJavascriptを追加/削除する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ドキュメントに JavaScript を追加および削除する方法を学びます。ドキュメント レベルのスクリプトのコード チュートリアルを含むステップ バイ ステップ ガイドです。
type: docs
weight: 30
url: /ja/net/programming-with-document/addremovejavascripttodoc/
---
## 導入

このガイドでは、Aspose.PDF for .NET を使用して PDF ファイルに JavaScript を挿入する方法と、必要に応じて JavaScript を削除する方法について説明します。このチュートリアルの最後には、PDF で JavaScript を簡単に操作する方法を明確に理解できるようになります。

## 前提条件

コードに進む前に、設定しておく必要のあるものがいくつかあります。

1.  Aspose.PDF for .NET: プロジェクトにAspose.PDF for .NETライブラリがインストールされている必要があります。まだインストールしていない場合は、次の場所からライブラリを入手してください。[Aspose.PDF for .NET ダウンロード ページ](https://releases.aspose.com/pdf/net/).
2. IDE またはテキスト エディター: Visual Studio などの .NET 互換の IDE を使用できます。
3. 基本的な C# の知識: このチュートリアルでは、読者が C# に慣れており、PDF の操作に精通していることを前提としています。
4. ライセンス: 制限を回避するために有効なライセンスを適用してください。一時ライセンスは以下から取得できます。[ここ](https://purchase.aspose.com/temporary-license/).

## パッケージのインポート

Aspose.PDF for .NET の使用を開始するには、必要な名前空間をプロジェクトにインポートする必要があります。手順は次のとおりです。

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
using System.Collections;
```

これら 2 つの名前空間は不可欠です。`Aspose.Pdf` PDF文書を扱うことができ、`System.Collections` JavaScript キーの処理に使用されます。

PDF に JavaScript を追加したり削除したりするプロセス全体を、わかりやすい手順に分解してみましょう。

## ステップ1: 新しいPDFドキュメントを初期化する

最初に行う必要があるのは、新しい PDF ドキュメントを作成することです。このドキュメントは、JavaScript を追加するための空白のキャンバスとして機能します。

```csharp
Document doc = new Document();
doc.Pages.Add();
```

ここでは、新しい`Document`オブジェクトを作成し、そこに空白ページを追加します。これを PDF の基礎と考えてください。

## ステップ2: PDFにJavaScriptを追加する

ドキュメントが完成したので、次は JavaScript を追加します。PDF 内の JavaScript を使用すると、アラートやフォーム検証などのカスタム動作を追加できます。

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
```

このコードスニペットでは、2つのJavaScript関数（`func1`そして`func2` ）をPDFに追加します。これらの関数は、必要に応じてさまざまなタスクを実行できます。ここでは、プレースホルダー関数を呼び出しています。`hello()`.

## ステップ3: JavaScriptを使用してPDFを保存する

必要な JavaScript を追加したら、PDF を保存します。

```csharp
doc.Save(dataDir + "AddJavascript.pdf");
```

これにより、JavaScriptを含むドキュメントが次の名前で保存されます。`AddJavascript.pdf`指定されたディレクトリ（`dataDir`）。

## ステップ4: 既存のPDFにJavaScriptを読み込んで表示する

既存の PDF 内の JavaScript 関数を確認または変更する必要がある場合、最初の手順は PDF ファイルを読み込み、JavaScript キーにアクセスすることです。

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
```

既存のものをロードしています`AddJavascript.pdf`JavaScriptのキーをリストに保存します。`Keys`プロパティは、ドキュメントに添付されているすべての JavaScript 関数の名前を返します。

## ステップ5: JavaScript関数を表示する

次に、JavaScript 関数を反復処理して、ドキュメント内で何が使用可能かを確認します。

```csharp
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}
```

これにより、各 JavaScript 関数名とそれに対応するコードがコンソールに出力されます。ドキュメントに現在どのような関数が含まれているかを確認する場合に便利です。

## ステップ6: PDFからJavaScriptを削除する

さて、次のような特定のJavaScript関数を削除したいとします。`func1`方法は次のとおりです。

```csharp
doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
```

の`Remove`メソッドは JavaScript 関数の名前を引数として受け取り、それをドキュメントから削除します。

## ステップ7: JavaScriptの削除を確認する

JavaScriptを削除した後、残りの関数を再印刷して確認することができます。`func1`正常に削除されました。

```csharp
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}
Console.WriteLine("Javascript added/removed successfully.");
```

このコードの最後の部分により、すべてが適切に行われ、JavaScript 関数が正しく更新されることが保証されます。

## 結論

おめでとうございます。Aspose.PDF for .NET を使用して PDF ドキュメントに JavaScript を追加および削除する方法を学習しました。この強力な機能は、動的なメッセージの追加からカスタム計算や検証の実行まで、さまざまなタスクに利用できます。PDF 内で JavaScript を操作することで、ユーザー エクスペリエンスを大幅に向上できます。

## よくある質問

### 1 つの PDF に複数の JavaScript 関数を追加できますか?
もちろんです！JavaScript関数を必要なだけ追加できます。`doc.JavaScript`コレクション。

### 存在しない JavaScript 関数を削除しようとするとどうなりますか?
関数が存在しない場合は、`Remove`メソッドはエラーをスローしませんが、何も削除されません。

### PDF を開いたらすぐに JavaScript を実行することは可能ですか?
はい。ドキュメントを開いたり、ボタンをクリックしたりするなど、特定のトリガーで JavaScript が実行されるように構成できます。

### PDF に追加した後で JavaScript を編集できますか?
はい、既存の PDF を読み込み、その JavaScript にアクセスし、コードを変更して、ドキュメントを再度保存することができます。

### JavaScript を削除すると、PDF コンテンツの残りの部分に影響しますか?
いいえ、JavaScript を削除してもスクリプトにのみ影響します。PDF の内容は変更されません。