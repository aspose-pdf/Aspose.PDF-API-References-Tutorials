---
title: PDF ファイルにストロークテキストを記入する
linktitle: PDF ファイルにストロークテキストを記入する
second_title: Aspose.PDF for .NET API リファレンス
description: 実用的な例が満載のこのステップバイステップ ガイドで、Aspose.PDF for .NET を使用して PDF ファイルにストローク テキストを簡単に入力する方法を学びます。
type: docs
weight: 90
url: /ja/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
## 導入

PDF ファイルを目立たせるために変更したいと思ったことはありませんか? 重要なドキュメントを紛れもなく自分のものにするために、印象的な透かしや太字のスタンプを追加する必要があるかもしれません。Aspose.PDF for .NET を使用すると、PDF ファイルにストローク テキストを簡単に入力して、目を引く芸術的なセンスを加えることができます。今日のチュートリアルでは、C# を使用して PDF にストローク テキストを入力するプロセスを順を追って説明します。最後には、PDF ファイルをプロのように操作する方法をしっかりと理解できるようになります。

## 前提条件

コーディングに入る前に、このチュートリアルをスムーズに進めるために準備しておく必要があるものがいくつかあります。

1. Visual Studio: C# コードを記述するため、マシンに Visual Studio がインストールされていることを確認してください。
2.  Aspose.PDFライブラリ: Aspose.PDF for .NETライブラリをダウンロードしたことを確認してください。[ここ](https://releases.aspose.com/pdf/net/).
3. C# の基礎知識: C# プログラミングに精通していると、チュートリアルをより簡単に理解できるようになります。
4. サンプルPDFファイル: サンプルPDFファイル(`input.pdf`をテスト目的で使用できます。シンプルなものを作成することも、既存の PDF を使用することもできます。

これで準備はすべて整いましたので、PDF ファイルにストローク テキストを入力する具体的な手順について説明しましょう。

## パッケージのインポート

まず、必要なパッケージをインポートする必要があります。以下は、プロジェクトに必須のインポートの概要です。

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

これらのパッケージを使用すると、Aspose.PDF ライブラリの強力な機能を使用できるようになります。

主なタスクを明確なステップに分解してみましょう。これらの手順に従うことで、ストローク テキストを PDF ファイルに簡単に入力できます。 

## ステップ1: 環境を設定する

まず、Visual Studio プロジェクトですべてが正しく設定されていることを確認します。新しいプロジェクトを作成するか、既存のプロジェクトを選択します。サポートが必要な場合は、次の手順に従ってください。

1. Visual Studio を開きます。
2. 新しい C# プロジェクト (例: コンソール アプリケーション) を作成します。
3. ソリューション エクスプローラーでプロジェクトを右クリックし、「NuGet パッケージの管理」を選択します。
4. 検索する`Aspose.PDF`インストールしてください。

## ステップ2: ドキュメントディレクトリを定義する

すべての旅には出発点が必要です。この場合、それは入力ファイルと出力ファイルが存在するドキュメント ディレクトリです。 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

交換する`"YOUR DOCUMENT DIRECTORY"`入力 PDF ファイルが配置されている実際のパスを入力します。 

## ステップ3: TextStateオブジェクトを作成する

このステップでは、追加するテキストのプロパティの定義を開始します。 

```csharp
TextState ts = new TextState();
```

の`TextState`オブジェクトには、ストローク テキストのスタイル オプションが保持されます。

## ステップ4: ストロークの色を設定する

次に、テキストのストロークの色を定義します。 

```csharp
ts.StrokingColor = Color.Gray;
```

このコードでは、ストロークにグレー色を使用しています。必要に応じて色を自由に変更してください。

## ステップ5: レンダリングモードを構成する

テキストが意図したとおりに表示されるようにするには、レンダリング モードを設定します。

```csharp
ts.RenderingMode = TextRenderingMode.StrokeText;
```

これは、ストローク テキストを操作していることを Aspose ライブラリに指示します。

## ステップ6: 入力PDFドキュメントを読み込む

次に、変更する PDF ファイルを読み込みます。 

```csharp
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

入力PDF（`input.pdf`は、前の手順で定義したドキュメント ディレクトリにあります。

## ステップ7: スタンプオブジェクトを作成する

次に、ストロークテキストを保持するスタンプを作成します。 

```csharp
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
```

このスタンプは、PDF にテキストを重ねるために使用されます。

## ステップ8: スタンプするテキストを定義する

PDF に追加するテキストを指定する必要があります。

```csharp
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));
```

ここで追加するテキストは「PAID IN FULL」で、そのスタイル属性も一緒に追加します。必要に応じてカスタマイズしてください。

## ステップ9: テキスト状態をバインドする

さて、`TextState`スタンプに以前定義した内容。 

```csharp
stamp.BindTextState(ts);
```

この手順では、色やレンダリング モードなどのすべてのスタイルをテキストに適用します。

## ステップ10: スタンプの位置を設定する

PDF 内でスタンプが表示される場所を決定します。

```csharp
stamp.SetOrigin(100, 100);
```

議論`(100, 100)`テキストの原点の X 座標と Y 座標 (ポイント単位) を示します。これらの値を調整して、テキストを最適な位置に配置してください。

## ステップ11: 不透明度と回転を設定する

ここでは、テキストの外観をいろいろ試すことができます。

```csharp
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
```

この場合、不透明度の値と 45 度の回転角度により、テキストに独特の雰囲気が加わります。さまざまな効果を得るために、これらの設定を自由に変更してください。

## ステップ12: PDFにスタンプを追加する

これは、ストローク テキストを含むスタンプを最終的に PDF に追加する重要なステップです。

```csharp
fileStamp.AddStamp(stamp);
```

これで、テキストでメッセージを発信する準備が整いました。

## ステップ13: ドキュメントを保存して閉じる

最後に、変更内容を保存し、すべてが適切にクリーンアップされていることを確認します。 

```csharp
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

ストロークテキストを含む新しく変更されたPDFファイルは次のように保存されます。`output_out.pdf`ドキュメントディレクトリ内。 

## 結論

これで完了です。これらの簡単な手順に従うだけで、Aspose.PDF for .NET を使用して PDF ファイルにストローク テキストを簡単に入力できます。ビジネス ドキュメントでも個人プロジェクトでも、このテクニックを使用すると PDF に独自のタッチを追加でき、書類の山の中でも目立つようになります。

## よくある質問

### Aspose.PDF for .NET とは何ですか?
Aspose.PDF for .NET は、開発者がプログラムによって PDF ファイルを作成、操作、変換できるようにするライブラリです。

### Aspose.PDF を無料で使用できますか?
はい、Asposeは無料トライアルを提供しています。[ここ](https://releases.aspose.com/).

### ライセンス料を支払う必要がありますか?
ライブラリは無料で試用できますが、一時ライセンスを購入することもできます。[このリンク](https://purchase.aspose.com/temporary-license/).

### ドキュメントはどこにありますか?
完全なドキュメントにアクセスできます[ここ](https://reference.aspose.com/pdf/net/).

### 問題が発生した場合、サポートを受けることはできますか?
もちろんです！Asposeフォーラムでサポートを受けることができます[ここ](https://forum.aspose.com/c/pdf/10).