---
title: PDF ファイルにテキスト スタンプを追加する
linktitle: PDF ファイルにテキスト スタンプを追加する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルにテキスト スタンプを追加する方法をステップ バイ ステップ ガイドで学習し、ドキュメントのプレゼンテーションを向上させましょう。
type: docs
weight: 50
url: /ja/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
## 導入

今日のデジタル時代では、PDF はドキュメントの共有や配信によく使われる形式です。開発者、コンテンツ作成者、または PDF ファイルを強化したいだけの人にとって、プログラムで PDF を操作する方法を知っていれば状況は一変します。ぜひ活用したい便利な機能の 1 つは、PDF ファイルにテキスト スタンプを追加する機能です。テキスト スタンプを追加すると、ドキュメントにプロフェッショナルな雰囲気を与えたり、「サンプル」、「機密」、透かしなどの重要な情報を伝えたりできます。

## 前提条件

コードに進む前に、すべてが正しく設定されていることを確認するための前提条件がいくつかあります。必要なものは次のとおりです。

1.  Aspose.PDF for .NET: プロジェクトにAspose.PDFライブラリがインストールされていることを確認してください。まだインストールしていない場合は、[Aspose ウェブサイト](https://releases.aspose.com/pdf/net/).
2. Visual Studio または互換性のある IDE: .NET コードを記述して実行するには開発環境が必要です。開発者の間で最も一般的な選択肢は Visual Studio です。
3. C# の基礎知識: C# とオブジェクト指向プログラミングの原則を理解していると、例をよりよく理解できるようになります。
4. サンプル PDF ファイル: 作業に使用できる PDF ファイルを用意する必要があります。基本的な PDF を作成することも、既存の PDF を使用して機能をテストすることもできます。

これらの前提条件を整理したら、コーディングに進むことができます。

## パッケージのインポート

次に、必要なパッケージをインポートします。この手順は、Aspose ライブラリのクラスとメソッドをプロジェクトで使用できるようにするため、非常に重要です。

### Aspose.PDF アセンブリをインポートする

まず、Aspose.PDF 名前空間をインポートする必要があります。C# ファイルの先頭に、次の using ディレクティブを追加します。

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

これにより、PDF ドキュメントの作成と操作に不可欠なクラスにアクセスできるようになります。

それでは、チュートリアルの本題に入りましょう。プロセスを明確で簡潔なステップに分解します。各ステップでは、PDF ファイルにテキスト スタンプを追加するためのコードについて説明します。

## ステップ1: ドキュメントディレクトリを設定する

まず、PDF ドキュメントが保存されているディレクトリを確立する必要があります。つまり、編集する PDF ファイルがどこにあるかをコードが認識している必要があります。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

説明: 置き換え`"YOUR DOCUMENT DIRECTORY"` PDFファイルの実際のパス（`AddTextStamp.pdf`) が保存されます。このパスは、後で変更された PDF を開いて保存するときに使用されます。

## ステップ2: PDFドキュメントを開く

次に、PDF文書を`Document`Aspose.PDF 名前空間からのクラス。

```csharp
//ドキュメントを開く
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

説明: ここでは、`Document`クラスを作成し、PDF ファイルへのパスを渡します。これにより、PDF が読み込まれ、操作できるようになります。

## ステップ3: テキストスタンプを作成する

ここで、後で PDF ドキュメントに適用するテキスト スタンプを作成します。

```csharp
//テキストスタンプを作成する
TextStamp textStamp = new TextStamp("Sample Stamp");
```

説明:`TextStamp`表示したいテキストを含むオブジェクトが作成されます。この場合、スタンプのテキストとして「サンプル スタンプ」を使用します。

## ステップ4: スタンプのプロパティを設定する

スタンプをカスタマイズするには、背景色、位置、回転などのさまざまなプロパティを設定できます。では、実際にやってみましょう。

```csharp
//スタンプを背景にするかどうかを設定する
textStamp.Background = true;

//原点を設定
textStamp.XIndent = 100;
textStamp.YIndent = 100;

//スタンプを回転する
textStamp.Rotate = Rotation.on90;
```

説明：
- 背景: これを設定する`true`つまり、スタンプは PDF コンテンツの背後に表示されます。
- XIndent と YIndent: これらのプロパティは、ページ上のスタンプの位置を決定します。この例では、スタンプはページの左端と上端から 100 単位の位置に配置されます。
- 回転: スタンプを 90 度回転します。デザイン要件に応じて、さまざまな回転オプションを選択できます。

## ステップ5: テキストプロパティをカスタマイズする

次に、スタンプ内のテキストの外観をカスタマイズして創造性を発揮してみましょう。

```csharp
//テキストプロパティを設定する
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(Color.Aqua);
```

説明：
- フォント: Arial フォントを使用し、太字と斜体にしています。
- フォントサイズ: 14 ポイントに設定されています。
- ForegroundColor: RGB を使用してテキストの色をアクアに設定します。ブランドやデザインのニーズに合わせて自由に色を変更できます。

## ステップ6: PDFページにスタンプを追加する

ここで、PDF ドキュメントの特定のページにスタンプを追加します。

```csharp
//特定のページにスタンプを追加する
pdfDocument.Pages[1].AddStamp(textStamp);
```

説明: この例では、スタンプは PDF の最初のページに追加されます (ページは 1 からインデックスされます)。ドキュメントの必要に応じてページ番号を調整します。

## ステップ7: 変更したPDFを保存する

最後に、新しく追加したテキストスタンプでドキュメントを保存しましょう。

```csharp
dataDir = dataDir + "AddTextStamp_out.pdf";

//出力ドキュメントを保存する
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);
```

説明: 出力ファイルの新しいパスを定義し、変更されたドキュメントを保存します。保存後、パスがコンソールに出力され、操作が成功したことが確認されます。

## 結論

おめでとうございます! Aspose.PDF for .NET を使用して、PDF ファイルにテキスト スタンプを正常に追加できました。この方法を使用すると、ドキュメントに効率的に注釈を付けることができ、ドキュメントの専門性と使いやすさの両方が向上します。透かし、署名、または簡単なメモを追加する場合でも、Aspose ライブラリは PDF を簡単に操作するための強力なツールを提供します。

## よくある質問

### PDF のテキストスタンプとは何ですか?
テキスト スタンプは、PDF ドキュメントに配置できるテキストを含むグラフィカル オーバーレイであり、注釈や透かしとしてよく使用されます。

### スタンプを画像でカスタマイズできますか?
はい、Aspose.PDF は画像スタンプの追加もサポートしており、より柔軟なデザインを実現します。

### Aspose.PDF ではどのようなプログラミング言語を使用できますか?
Aspose.PDF は主に .NET に重点を置いていますが、Java や Python などの他の言語用のバージョンも用意されています。

### Aspose.PDF の一時ライセンスを取得するにはどうすればよいですか?
一時ライセンスを申請するには、[購入リンク](https://purchase.aspose.com/temporary-license/)彼らのウェブサイトで。

### Aspose.PDF のサポートはどこで受けられますか?
 Aspose.PDFのサポートは、[サポートフォーラム](https://forum.aspose.com/c/pdf/10).