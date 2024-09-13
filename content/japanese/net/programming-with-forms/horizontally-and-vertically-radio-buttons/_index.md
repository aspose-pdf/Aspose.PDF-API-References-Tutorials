---
title: 水平方向と垂直方向のラジオボタン
linktitle: 水平方向と垂直方向のラジオボタン
second_title: Aspose.PDF for .NET API リファレンス
description: このステップバイステップのチュートリアルでは、Aspose.PDF for .NET を使用して PDF に水平および垂直に揃えられたラジオ ボタンを作成する方法を学習します。
type: docs
weight: 180
url: /ja/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
## 導入

インタラクティブな PDF フォームを作成すると、特に情報収集の場合には、ユーザー エクスペリエンスを大幅に向上できます。最も一般的なフォーム要素の 1 つはラジオ ボタンで、ユーザーはこれを使用して、セットから 1 つのオプションを選択できます。このチュートリアルでは、Aspose.PDF for .NET を使用して、水平および垂直に整列したラジオ ボタンを作成する方法について説明します。熟練した開発者でも、初心者でも、このガイドでは、各部分を明確に理解できるように、プロセスを段階的に説明します。

## 前提条件

コードに進む前に、いくつかの前提条件を満たす必要があります。

1.  Aspose.PDF for .NET: Aspose.PDFライブラリがインストールされていることを確認してください。[サイト](https://releases.aspose.com/pdf/net/).
2. Visual Studio: コードを記述してテストできる開発環境。
3. C# の基礎知識: C# プログラミングに精通していると、コード スニペットをよりよく理解できるようになります。

## パッケージのインポート

まず、C# プロジェクトに必要なパッケージをインポートする必要があります。手順は次のとおりです。

### 新しいプロジェクトを作成する

Visual Studio を開き、新しい C# プロジェクトを作成します。簡単にするために、コンソール アプリケーションを選択できます。

### Aspose.PDF 参照の追加

1. ソリューション エクスプローラーでプロジェクトを右クリックします。
2. 「NuGet パッケージの管理」を選択します。
3. 「Aspose.PDF」を検索し、最新バージョンをインストールしてください。

```csharp
using System;
using System.IO;
using Aspose.Pdf.Facades;
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

これですべての設定が完了したので、コードを分解して水平および垂直に揃えられたラジオ ボタンを作成しましょう。

## ステップ1: ドキュメントディレクトリを設定する

このステップでは、PDF ドキュメントを保存するディレクトリへのパスを定義します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

交換する`"YOUR DOCUMENT DIRECTORY"` PDF ファイルを保存する実際のパスを入力します。これは、プログラムに入力ファイルの検索場所と出力の保存場所を指示するため、非常に重要です。

## ステップ2: 既存のPDF文書を読み込む

次に、作業するPDF文書を読み込む必要があります。これは、`FormEditor`クラス。

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

ここでは、`FormEditor`それを既存のPDFファイルにバインドします。`input.pdf`指定したディレクトリにこのファイルが存在することを確認してください。

## ステップ3: ラジオボタンのプロパティを構成する

ここで、ラジオ ボタンのプロパティをいくつか設定しましょう。これには、ボタン間の間隔、ボタンの向き、サイズなどが含まれます。

```csharp
formEditor.RadioGap = 4; //ラジオボタンオプション間の距離
formEditor.RadioHoriz = true; //水平方向の配置の場合はtrueに設定
formEditor.RadioButtonItemSize = 20; //ラジオボタンのサイズ
formEditor.Facade.BorderWidth = 1; //境界線の幅
formEditor.Facade.BorderColor = System.Drawing.Color.Black; //境界線の色
```

これらのプロパティは、ラジオボタンがPDFでどのように表示されるかを定義するのに役立ちます。`RadioGap`プロパティはボタン間のスペースを制御し、`RadioHoriz`レイアウトを決定します。

## ステップ4: 水平ラジオボタンを追加する

次に、PDF に水平ラジオ ボタンを追加しましょう。

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

このコードでは、ラジオボタンの項目を定義してPDFに追加します。`AddField`メソッドは、フィールド タイプ、フィールド名、配置の座標など、いくつかのパラメータを取ります。

## ステップ5: 垂直ラジオボタンを追加する

次に、垂直ラジオ ボタンを追加します。これを行うには、方向を垂直に戻す必要があります。

```csharp
formEditor.RadioHoriz = false; //垂直方向の配置の場合は false に設定
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

前と同じように項目を定義して PDF に追加しますが、今回は垂直に揃えます。

## ステップ6: PDFドキュメントを保存する

最後に、変更した PDF ドキュメントを保存する必要があります。

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
```

このコードは、新しく追加されたラジオ ボタンを含む PDF を保存します。出力ファイルの指定されたディレクトリを必ず確認してください。

## 結論

Aspose.PDF for .NET を使用して PDF にラジオ ボタンを作成するのは簡単なプロセスです。このチュートリアルで説明されている手順に従うと、水平方向と垂直方向に並んだラジオ ボタンを PDF フォームに簡単に追加できます。これにより、ドキュメントのインタラクティブ性が向上するだけでなく、全体的なユーザー エクスペリエンスも向上します。ぜひお試しください。

## よくある質問

### Aspose.PDF for .NET とは何ですか?
Aspose.PDF for .NET は、開発者がプログラムによって PDF ドキュメントを作成、操作、変換できるようにする強力なライブラリです。

### Aspose.PDF を無料で使用できますか?
はい、Asposeはライブラリを評価するために使用できる無料試用版を提供しています。ダウンロードできます。[ここ](https://releases.aspose.com/).

### Aspose.PDF のサポートを受けるにはどうすればよいですか?
サポートを受けるには、[Aspose フォーラム](https://forum.aspose.com/c/pdf/10).

### Aspose.PDF で他のフォーム要素を作成することは可能ですか?
もちろんです! Aspose.PDF は、テキスト フィールド、チェック ボックス、ドロップダウンなど、さまざまなフォーム要素をサポートしています。

### Aspose.PDF for .NET はどこで購入できますか?
 Aspose.PDF for .NETは以下から購入できます。[購入ページ](https://purchase.aspose.com/buy).