---
title: PDF ファイルに Java Script を追加する
linktitle: Java Script PDF ファイルを追加
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルに JavaScript を追加する方法を学びます。ドキュメントおよびページ レベルのスクリプトのコード チュートリアルを含むステップ バイ ステップ ガイドです。
type: docs
weight: 10
url: /ja/net/programming-with-document/addjavascripttopage/
---
## 導入

ポップアップ アラートや自動印刷機能などのインタラクティブな要素を使用して PDF を強化する方法を考えたことがありますか? 朗報です。それが可能です! Aspose.PDF for .NET を使用すると、PDF ドキュメントに JavaScript をシームレスに追加できます。タスクを自動化する場合でも、動的なユーザー エクスペリエンスを作成する場合でも、PDF に JavaScript を埋め込むと、ファイルにさらに高度な機能が追加されます。

## 前提条件

コーディング部分に進む前に、設定しておく必要のあるものがいくつかあります。

-  Aspose.PDF for .NET: ライブラリをダウンロード[Aspose リリース](https://releases.aspose.com/pdf/net/)または[無料トライアル](https://releases.aspose.com/).
- 開発環境: Visual Studio などの .NET 互換 IDE。
- 基本的な C# の知識: このガイドでは、基本的な C# 構文に精通していることを前提としています。
- 一時ライセンス（オプション）：[一時ライセンス](https://purchase.aspose.com/temporary-license/)開発中に制限を回避したい場合。

## パッケージのインポート

コードの記述を開始する前に、Aspose.PDF ライブラリから必要な名前空間をインポートする必要があります。これらの名前空間を使用すると、PDF を操作したり、JavaScript アクションを簡単に追加したりできるようになります。

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

適切な名前空間をインポートしたので、コーディングを開始する準備が整いました。

## ステップ1: 既存のPDFを読み込む

まず最初に、JavaScript を追加する PDF ドキュメントを読み込む必要があります。このステップは、以降のすべての変更の準備となります。ドキュメントを開いたときに自動的に印刷するなど、動的な機能で拡張したい PDF があるとします。

PDF ファイルを読み込む方法は次のとおりです。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//既存のPDFファイルを読み込む
Document doc = new Document(dataDir + "input.pdf");
```

このコードスニペットでは、`Document`クラスを使用して、指定されたディレクトリから既存のPDFファイルを読み込みます。`"YOUR DOCUMENT DIRECTORY"` PDF ファイルへの実際のパスを入力します。

## ステップ2: ドキュメントレベルでJavaScriptを追加する

次に、ドキュメントが開いたときにトリガーされる JavaScript を追加しましょう。この例では、ユーザーが PDF を開くとすぐに印刷ダイアログを開くスクリプトを記述します。

ドキュメント レベルの JavaScript は、PDF 全体に適用するアクションに最適です。ドキュメントのグローバル ルールを設定するようなものと考えてください。

コードは次のとおりです:

```csharp
//ドキュメントレベルでのJavaScriptの追加
//希望するJavaScriptステートメントでJavascriptActionをインスタンス化する
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

//JavascriptActionオブジェクトをドキュメントのOpenActionに割り当てる
doc.OpenAction = javaScript;
```

このステップでは、`JavascriptAction`ドキュメントを開いたときに印刷ダイアログを開くJavaScript関数を定義するオブジェクト。`doc.OpenAction`次に、この JavaScript アクションがプロパティに割り当てられます。

## ステップ3: ページレベルでJavaScriptを追加する

すべてのアクションがドキュメント全体に影響する必要はありません。特定のページを開いたり閉じたりするときに、特定のアクションを実行したい場合があります。ここでは、特定のページ (たとえばページ 2) を開いたり閉じたりするときに実行される JavaScript アクションを設定します。

ページ レベルの JavaScript は、対象を絞ったインタラクションに役立ちます。ユーザーがページに移動したときにメッセージを表示することから、フォーム フィールドの自動入力などのカスタム アクションまで、あらゆる操作が可能です。

やり方は次のとおりです:

```csharp
//ページレベルでのJavaScriptの追加
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('Page 2 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('Page 2 closed')");
```

このコード スニペットでは、2 つの JavaScript アクションを追加します。
1. OnOpen アクション: ユーザーがページ 2 を開いたときに、「ページ 2 が開きました」というアラートを表示します。
2. OnClose アクション: ユーザーがページ 2 から移動したときに、「ページ 2 が閉じられました」というアラートを表示します。

これにより、PDF にインタラクティブなレイヤーが追加されます。ユーザーがページに入ったりページを離れたりするときにポップアップ表示されるアラートを使用して、さまざまなページで一連の手順をユーザーに案内することを想像してみてください。

## ステップ4: PDFドキュメントを保存する

これで、ドキュメントと特定のページの両方に JavaScript が追加されました。最後の手順は、変更した PDF を目的の場所に保存することです。この部分は簡単ですが、非常に重要です。作業内容を保存することを忘れないでください。

コードは次のとおりです:

```csharp
//出力ファイルのパスを指定する
dataDir = dataDir + "JavaScript-Added_out.pdf";

//更新されたPDF文書を保存する
doc.Save(dataDir);

Console.WriteLine("\nJavaScript added successfully to the PDF.\nFile saved at " + dataDir);
```

このスニペットでは、JavaScriptを追加した更新されたドキュメントを、次の名前の新しいファイルに保存します。`"JavaScript-Added_out.pdf"`これにより、元のファイルが上書きされることがなくなり、作業に使用できるバックアップが提供されます。

## 結論

Aspose.PDF for .NET を使用して PDF ファイルに JavaScript を追加することは、インタラクティブで動的な PDF を作成するための強力な方法です。印刷やカスタム アラートの作成などのタスクを自動化する場合でも、PDF に JavaScript を埋め込む機能により、ドキュメントがより魅力的で機能的になります。

## よくある質問

### PDF 内の異なるページに複数の JavaScript アクションを追加できますか?
はい、個々のページまたはドキュメント全体に異なる JavaScript アクションを割り当てることができます。

### PDF に追加した後で JavaScript を削除することは可能ですか?
はい、既存のJavaScriptアクションを削除または変更するには、`Actions`ドキュメントまたはページのプロパティ。

### PDF ではどのような JavaScript 関数を使用できますか?
印刷、アラート、フォーム操作など、Adobe Acrobat の JavaScript エンジンでサポートされている任意の JavaScript を使用できます。

### JavaScript はすべての PDF ビューアで動作しますか?
ほとんどの JavaScript アクションは、Adobe Acrobat などのインタラクティブ PDF をサポートする PDF ビューアで動作します。ただし、一部の基本的な PDF リーダーは JavaScript をサポートしていない場合があります。

### PDF 内のユーザー入力に基づいて JavaScript アクションをトリガーできますか?
はい、JavaScript をフォーム フィールドにバインドして、ユーザー入力に基づいてアクションをトリガーできます。