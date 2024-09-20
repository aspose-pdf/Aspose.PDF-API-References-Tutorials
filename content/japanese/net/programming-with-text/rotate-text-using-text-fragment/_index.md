---
title: PDF ファイル内のテキストフラグメントを使用してテキストを回転する
linktitle: PDF ファイル内のテキストフラグメントを使用してテキストを回転する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内のテキストを回転する方法をステップバイステップ ガイドで学習します。配置から回転までのテキスト操作テクニックを学びます。
type: docs
weight: 390
url: /ja/net/programming-with-text/rotate-text-using-text-fragment/
---
## 導入

PDF を作成するのは簡単ですが、特定の要件に合わせて PDF を操作するのは大変です。そこで、本当の魔法が起こります。PDF 内のテキストを回転する方法を考えたことはありませんか。レポートを生成する場合でも、カスタム デザインでドキュメントを作成する場合でも、テキスト フラグメントを回転すると、PDF の見た目がより魅力的になります。このチュートリアルでは、PDF ドキュメントをシームレスに操作できる強力なライブラリである Aspose.PDF for .NET を使用してテキストを回転する方法を説明します。

## 前提条件

コードに進む前に、必要なツールと設定について簡単に説明しましょう。すべて準備しておけば、簡単に理解できるようになります。

### Aspose.PDF for .NET ライブラリ
まず、プロジェクトに Aspose.PDF for .NET をインストールする必要があります。このライブラリには、プログラムで PDF ファイルを作成、変更、管理するのに役立つ機能が満載されています。まだダウンロードしていない場合は、次の場所から入手してください。
- [Aspose.PDF for .NET をダウンロード](https://releases.aspose.com/pdf/net/)

このチュートリアルでは、ライブラリの最新バージョンを使用していることを確認してください。

### 開発環境
Visual Studio のような .NET 開発環境も必要です。これは C# 開発の定番 IDE であり、コーディング作業をスムーズかつ効率的にします。

### 一時ライセンスまたはフルライセンス
Aspose.PDF の無料トライアルから始めることもできますが、制限を回避したい場合は、一時ライセンスまたは完全ライセンスを使用することをお勧めします。取得方法は次のとおりです。
- [無料トライアル](https://releases.aspose.com/)
- [一時ライセンス](https://purchase.aspose.com/temporary-license/)
- [フルライセンスを購入](https://purchase.aspose.com/buy)

これらの基本事項をすべて準備したら、次に進みましょう。

## パッケージのインポート

コーディングを始める前に、Aspose.PDF に付属する必要な名前空間をインポートする必要があります。これは、ドキュメント、ページ、テキスト フラグメントなどを操作する上で重要です。C# ファイルの先頭に次のコードを追加します。

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
```

それでは、プロのようにテキストを回転できるように、サンプル コードを段階的に分解してみましょう。

## ステップ1: ドキュメントオブジェクトを初期化する

すべての PDF 操作は、PDF ドキュメントの作成または読み込みから始まります。ここでは、Aspose.PDF を使用して、新しい PDF ドキュメントを最初から初期化します。

私たちは新しい`Document`PDF ファイルを表すオブジェクト。最初はこのドキュメントは空です。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントオブジェクトを初期化する
Document pdfDocument = new Document();
```

説明：  
- `dataDir`: これは最終的な PDF が保存されるディレクトリです。
- `Document pdfDocument = new Document();`: 新しい空の PDF ドキュメントを初期化します。 

## ステップ2: ドキュメントにページを追加する

次に、ドキュメントにページを追加する必要があります。PDF は基本的にページの集合体であり、コンテンツを追加するには少なくとも 1 ページが必要です。

```csharp
//特定のページを取得する
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

ページを追加しないと、描画したりテキストを配置したりするためのキャンバスがありません。

## ステップ3: 最初のテキストフラグメントを作成する

次は面白い部分です。PDF にテキスト フラグメントを追加しましょう。テキスト フラグメントとは、フォント、サイズ、位置などの特定のプロパティを持つテキストの一部です。

```csharp
//テキストフラグメントを作成
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
```

- TextFragment("main text"): これは、コンテンツが「main text」の新しいテキスト フラグメントを作成します。
- 位置 (100, 600): ページ上のテキストの位置を定義します。最初の数字は x 座標、2 番目の数字は y 座標です。
- TextState.FontSize: テキストのフォント サイズを設定します。
- FontRepository.FindFont: テキストに適用する指定されたフォントを検索します。

## ステップ4: 回転したテキストフラグメントを作成する

さらにテキストフラグメントを追加してみましょう。ただし、今回は異なる角度に回転させます。

### テキストフラグメントを45度回転する

```csharp
//回転したテキストフラグメントを作成する
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
```

ここで重要な変更点は次のとおりです。
- TextState.Rotation: このプロパティはテキスト フラグメントの回転角度を設定します。この場合は 45 度です。

### テキストフラグメントを90度回転する

```csharp
//回転したテキストフラグメントを作成する
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
```

この例では、回転は 90 度です。

## ステップ5: PDFページにテキストフラグメントを追加する

すべてのテキスト フラグメントが準備できたので、TextBuilder クラスを使用してそれらを PDF ページに追加します。

```csharp
// TextBuilder オブジェクトを作成する
TextBuilder textBuilder = new TextBuilder(pdfPage);
//テキストフラグメントをPDFページに追加します
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

TextBuilder クラスは、複数のテキスト フラグメントを 1 つのページに追加するのに役立ち、それらを個別に操作する柔軟性を提供します。

## ステップ6: PDFドキュメントを保存する

最後に、ドキュメントを指定されたディレクトリに保存します。この手順を実行しないと、これまでの努力がすべて無駄になってしまいます。

```csharp
//ドキュメントを保存
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

Aspose.PDF for .NET を使用して PDF ファイル内のテキストを正常に回転できました。これで、PDF を開いて回転したテキスト フラグメントを表示できます。

## 結論

PDF 内のテキストを回転すると、ドキュメントにプロフェッショナルなタッチが加わり、見た目が魅力的でユニークなものになります。Aspose.PDF for .NET を使用すると、テキスト フラグメントの操作が非常に簡単になり、コンテンツの表示方法を完全に制御できます。テキストの回転方法を学習したので、プロジェクトのニーズに合わせてさまざまな角度やレイアウトを試すことができます。

## よくある質問

### テキストフラグメントを任意の角度に回転できますか?
はい！設定できます`TextState.Rotation`プロパティを任意の角度（負の角度も含む）に設定して、必要に応じてテキストを回転します。

### テキストフラグメントごとに異なるフォントを使用できますか?
もちろんです。各テキストのフォントをカスタマイズするには、`FontRepository.FindFont`適用したいフォントを渡します。

### Aspose.PDF は複数ページの PDF をサポートしていますか?
はい、PDF ドキュメントに複数のページを追加し、各ページを個別に操作できます。

### 追加できるテキストフラグメントの数に制限はありますか?
いいえ、必要な数だけテキストフラグメントを追加できます。ページ上で適切に配置されていることを確認してください。

### テキストフラグメントを追加した後に変更できますか?
はい、テキスト フラグメントを追加した後でも、そのプロパティを更新したり、ページから削除したりすることができます。