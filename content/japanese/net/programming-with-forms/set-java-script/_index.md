---
title: Java Scriptを設定する
linktitle: Java Scriptを設定する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET のパワーを解き放ちましょう。ステップバイステップ ガイドを使用して、フォーム フィールドに JavaScript を設定する方法を学びます。
type: docs
weight: 270
url: /ja/net/programming-with-forms/set-java-script/
---
## 導入

動的でインタラクティブな PDF を作成すると、特にドキュメント内にフォームとフィールドを統合する場合に、ユーザー エクスペリエンスを大幅に向上できます。これを可能にする強力なライブラリの 1 つが Aspose.PDF for .NET です。この記事では、Aspose.PDF を使用してフォーム フィールドの JavaScript を設定する方法について詳しく説明し、PDF が見栄えが良いだけでなく、機能も優れていることを確認します。

## 前提条件

コーディングを始める前に、スムーズに進めるために必要なものがすべて揃っていることを確認しましょう。

- Visual Studio (または任意の .NET IDE): 正しくインストールされ、設定されていることを確認します。
  
-  Aspose.PDFライブラリ: このライブラリの最新バージョンが必要になります。ダウンロードできます。[ここ](https://releases.aspose.com/pdf/net/).

- C# の基礎知識: C# プログラミングに精通していると、コード スニペットをよりよく理解できるようになります。

-  PDFファイル: テスト用にPDFファイルを用意する必要があります。この例では、次のファイルを使用します。`SetJavaScript.pdf`.

- ドキュメント ディレクトリ: ドキュメント ファイルが保存されている場所を把握します。コード内でこのパスを参照します。

これらの前提条件が準備できたら、どのツールを活用すればよいでしょうか? Aspose.PDF で何ができるのか見てみましょう。

## パッケージのインポート

まず、C# プロジェクトに必要な名前空間を含める必要があります。メインの C# ファイルを開き、次のインポート ステートメントを追加します。

```csharp
using System;
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

これらの名前空間は、Aspose.PDF ライブラリ内の PDF およびフォーム関連の機能へのアクセスを提供します。

PDF をインタラクティブにする準備はできましたか? コーディングの準備をして、ステップごとに説明しましょう。

## ステップ1: ドキュメントパスを定義する

まず、PDF ファイルの場所を指定する必要があります。これにより、以降のすべての作業の準備が整います。手順は次のとおりです。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

交換する`"YOUR DOCUMENT DIRECTORY"` PDF ファイルが保存されている実際のパスを入力します。これは宝の地図の座標を設定するようなもので、「X」印がどこにあるかを知っておく必要があります。

## ステップ2: PDFドキュメントを読み込む

ディレクトリを定義したら、PDF ファイルを読み込みます。 

```csharp
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

この行は、指定された PDF ファイルを開き、操作できるように準備します。 

## ステップ3: フォームフィールドにアクセスする

次に、JavaScript を適用するフォーム フィールドにアクセスします。 

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

ここでは、PDFに次の名前のテキストボックスがあると仮定します。`textbox1`この名前のフィールドがない場合は、名前を変更するか、それに応じてコードを調整することができます。 

## ステップ4: JavaScriptアクションを設定する

それでは、テキスト ボックスに機能を追加してみましょう。特定のイベントでトリガーされる JavaScript アクションを設定します。 

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

何が起こっているか見てみましょう:
- OnModifyCharacter: この JavaScript 関数は、文字が変更された場合のフィールドの動作を指定します。この場合、数字の後に区切り記号なしで 2 つの小数点を使用できます。
- OnFormat: これにより、ユーザーが数値をフォーマットするときに、同じルールが遵守されるようになります。

これらのアクションを設定することで、テキスト ボックスに個性を与えることができます。ダンスの動きを教えるようなものです。

## ステップ5: フィールド値を初期化する

次に、初期値を設定してテキスト ボックスに開始点を設定します。 

```csharp
field.Value = "123";
```

この行は、テキスト ボックス内の事前入力値として「123」を設定します。これは、パフォーマンスのためにステージを準備するようなものです。

## ステップ6: 変更したPDFを保存する

最後に、これらすべての変更を行った後、ドキュメントを保存する必要があります。

```csharp
dataDir = dataDir + "Restricted_out.pdf";
doc.Save(dataDir);
```

これにより、元のファイルに変更が反映され、次のように保存されます。`Restricted_out.pdf`これを PDF の運命を決定づけるものと考えてください。保存すれば、世界に公開する準備が整います。

## ステップ7: 成功を確認する

最後に、すべてがスムーズに進んだかどうかを確認しましょう。 

```csharp
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

このメッセージを実行すると、素晴らしいパフォーマンスの後に観客から拍手を受けるのと同じように、操作が正常に完了したことを確認できます。

## 結論

おめでとうございます! Aspose.PDF for .NET を使用して、PDF のフォーム フィールドに JavaScript を正常に設定しました。このチュートリアルでは、ユーザー インタラクションを強化するツールを紹介しただけでなく、プロのようにドキュメントをパーソナライズする方法について学びました。請求書、アンケート、その他のインタラクティブな PDF のフォームを扱う場合でも、可能性は無限です。

### よくある質問

### Aspose.PDF for .NET とは何ですか?  
Aspose.PDF は、.NET アプリケーション内で PDF ファイルを作成、編集、操作するために設計されたライブラリであり、強力な PDF 機能を提供します。

### Aspose.PDF を使用するにはライセンスが必要ですか?  
無料トライアルは利用可能ですが、制限なくフル機能を使用するにはライセンスが必要です。ライセンスを購入することができます。[ここ](https://purchase.aspose.com/buy).

### 他の種類のフォーム フィールドに JavaScript を設定できますか?  
もちろんです! Aspose.PDF では、チェックボックス、ラジオ ボタン、ドロップダウンなどのさまざまなフォーム フィールドで JavaScript アクションを実行できます。

### Aspose.PDF の問題に関するサポートを受けるにはどうすればよいですか?  
サポートは、[フォーラム](https://forum.aspose.com/c/pdf/10)ご質問や問題がございましたら、

### 購入せずに Aspose.PDF をテストする方法はありますか?  
はい！Asposeは[無料トライアル](https://releases.aspose.com/)購入する前にライブラリの機能をテストします。