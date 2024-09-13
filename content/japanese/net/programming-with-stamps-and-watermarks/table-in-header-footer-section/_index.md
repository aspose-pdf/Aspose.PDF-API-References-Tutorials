---
title: ヘッダー フッター セクションの表
linktitle: ヘッダー フッター セクションの表
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ドキュメントのヘッダー/フッター セクションにテーブルを追加する方法を学習します。
type: docs
weight: 170
url: /ja/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
## 導入

プレーンな PDF ドキュメントを見つめながら、もう少しセンスがあればいいのにと思ったことはありませんか? 幸運です! Aspose.PDF for .NET を使用すると、プロのように PDF ファイルを作成および操作できます。今日は、PDF ドキュメントのヘッダーにテーブルを追加できる便利な機能について詳しく説明します。その方法を学ぶだけでなく、プロセス全体をバターのようにスムーズにするために、ステップ バイ ステップでガイドします。🎉

## 前提条件

実際のコーディング部分に進む前に、始めるのに必要なものがすべて揃っていることを確認しましょう。必要なものは次のとおりです。

1.  Visual Studio: お使いのコンピュータにVisual Studioがインストールされていることを確認してください。まだインストールされていない場合は、こちらからダウンロードできます。[Microsoftのサイト](https://visualstudio.microsoft.com/).
2. Aspose.PDFライブラリ: .NET用のAspose.PDFライブラリが必要です。次のリンクから入手できます。[Aspose.PDF for .NET パッケージ](https://releases.aspose.com/pdf/net/).
3. C# の基礎知識: 少なくとも C# の基本的な知識が必要です。まだ学習中であっても心配しないでください。できるだけ簡単に説明します。

## パッケージのインポート

さあ、袖をまくってコーディングに取り掛かりましょう! ただし、まずは必要なパッケージをインポートして環境を設定する必要があります。手順は次のとおりです。

###  プロジェクトを開く
PDF 作成作業を行う Visual Studio プロジェクトを開きます。 

###  Aspose.PDF への参照を追加する
1. NuGet パッケージ マネージャー: ソリューション エクスプローラーでプロジェクトを右クリックし、[NuGet パッケージの管理] を選択します。
2. Aspose.PDF を検索します。検索バーに「Aspose.PDF」と入力してパッケージをインストールします。

このステップの終わりまでに、すべてがセットアップされ、コーディングを開始する準備が整うはずです。

では、実際にコードに取り組んでみましょう。PDF のヘッダー セクションにテーブルを作成するには、次の手順に従ってください。

## ステップ1: ドキュメントディレクトリへのパスを設定する

PDF の作成を始める前に、ドキュメントを保存する場所を定義する必要があります。手順は次のとおりです。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY"; //これを実際のディレクトリに変更します
```

交換する`YOUR DOCUMENT DIRECTORY`PDF を保存するパスを入力します。システム上の任意の場所を指定できますが、アクセス可能であることを確認してください。

## ステップ2: ドキュメントをインスタンス化する

次に、新しい PDF ドキュメントを作成します。

```csharp
//空のコンストラクタを呼び出してDocumentインスタンスをインスタンス化する
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();
```

ここで行っているのは、すべての機能を追加する空の PDF ドキュメントを作成することです。

## ステップ3: 新しいページを作成する

ドキュメントに新しいページを追加しましょう。 

```csharp
// PDF文書にページを作成する
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

このページを、傑作を描くための空白のキャンバスと考えてください。

## ステップ4: ヘッダーセクションを作成する

ここで、PDF のヘッダーを設定します。

```csharp
// PDFファイルのヘッダーセクションを作成する
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
```

このヘッダーにテーブルが保持されます。 

## ステップ5: ページにヘッダーを割り当てる

次に、ヘッダーがページに表示されることを確認します。

```csharp
// PDFファイルの奇数ヘッダーを設定する
page.Header = header;
```

## ステップ6: 上余白を設定する

ヘッダーの上部に余裕を持たせるために、余白を調整しましょう。

```csharp
//ヘッダーセクションの上余白を設定する
header.Margin.Top = 20;
```

余白を設定することは、テキストに個人的なスペースを与えることと同じです。窮屈なのは誰も好みません。

## ステップ7: テーブルを作成する

ここで、ヘッダーに挿入するテーブルを作成します。

```csharp
//テーブルオブジェクトをインスタンス化する
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## ステップ8: ヘッダーにテーブルを追加する

新しく作成した表をヘッダーの段落コレクションに追加します。

```csharp
//希望するセクションの段落コレクションに表を追加します
header.Paragraphs.Add(tab1);
```

## ステップ9: セルの境界線を設定する

デフォルトのセルの境界線を定義して、テーブルに構造を与えてみましょう。

```csharp
// BorderInfo オブジェクトを使用してデフォルトのセル境界線を設定する
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## ステップ10: 列幅を定義する

表の各列の幅を指定できます。

```csharp
//テーブルの列幅を設定する
tab1.ColumnWidths = "60 300";
```

値は各列の幅をポイント単位で表します。必要に応じて自由に調整してください。

## ステップ11: 行を作成し、セルを追加する

行とセルをいくつか追加してみましょう。 

```csharp
//表に行を作成し、行にセルを作成します
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;
```

これにより、テキストを含むセルを含む最初の行が作成され、その背景色がグレーに設定されます。

## ステップ12: 行間隔とテキストスタイルを設定する

行を複数の列にまたがらせたいですか? 方法は次のとおりです。

```csharp
//最初の行の行スパン値を2に設定します
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
```

この手順では、行の範囲を設定するだけでなく、テキストの色とフォントも変更します。

## ステップ13: 2行目を追加する

テーブルにもう 1 行追加してみましょう。

```csharp
//テーブルに別の行を作成する
Aspose.Pdf.Row row2 = tab1.Rows.Add();

//行2の背景色を設定する
row2.BackgroundColor = Color.White;
```

## ステップ14: 2行目に画像を追加する

今度はロゴを入れてテーブルをおしゃれに見せましょう!

```csharp
//画像を保持するセルを追加します
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg"; //必ずディレクトリに画像を置いてください
```

交換を忘れないでください`"aspose-logo.jpg"`画像の実際の名前を入力してください。

## ステップ15: 画像の幅を調整する

セル内で画像が適切に表示されるように画像の幅を設定します。

```csharp
//画像の幅を60に設定します
img.FixWidth = 60;

//表のセルに画像を追加する
Aspose.Pdf.Cell cell2 = row2.Cells.Add();
cell2.Paragraphs.Add(img);
```

## ステップ16: 2番目のセルにテキストを追加する

ロゴの横にちょっとしたテキストを追加してみましょう。

```csharp
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
```

## ステップ17: テキストを垂直方向と水平方向に揃える

すべてが整然と見えるようにしてください。テキストを揃えてください。

```csharp
//テキストの垂直方向の配置を中央揃えに設定します
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## ステップ18: PDFドキュメントを保存する

最後に、私たちの作品を保存しましょう!

```csharp
// PDFファイルを保存する
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

すると、ヘッダー セクションにテーブルが追加されたすばらしい PDF が作成されました。

## 結論

これで完了です。Aspose.PDF for .NET を使用して、PDF ドキュメントのヘッダーにテーブルを正常に追加できました。わずか数行のコードで、シンプルな PDF をプロフェッショナルなドキュメントに変えることができるのは驚きです。レポート、請求書、プレゼンテーションを作成する場合でも、創造性を少し加えるだけで、大きな違いが生まれます。 

## よくある質問

### Aspose.PDF for .NET とは何ですか?
Aspose.PDF for .NET は、開発者がプログラムで PDF ドキュメントを作成および操作できるようにする強力なライブラリです。

### Aspose.PDF を使用するにはライセンスが必要ですか?
試用期間中は無料でライブラリを使用できますが、延長使用にはライセンスが必要です。[一時ライセンス](https://purchase.aspose.com/temporary-license/)評価のため。

### ドキュメントはどこにありますか?
包括的なドキュメントと例については、[Aspose.PDF ドキュメント ページ](https://reference.aspose.com/pdf/net/).

### 技術的な問題についてサポートに問い合わせるにはどうすればいいですか?
サポートを受けるには、[Aspose フォーラム](https://forum.aspose.com/c/pdf/10).

### PDF の他のセクションに表を作成できますか?
もちろんです! フッターや本文のセクションにもテーブルを作成できます。同様の手順に従ってください。