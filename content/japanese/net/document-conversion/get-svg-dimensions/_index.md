---
title: SVG 寸法の取得
linktitle: SVG 寸法の取得
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して SVG 寸法を取得するためのステップバイステップ ガイド。
type: docs
weight: 40
url: /ja/net/document-conversion/get-svg-dimensions/
---
## 導入
このチュートリアルでは、Aspose.PDF for .NET を使用して SVG ファイルの寸法を取得するプロセスを説明します。 SVG (Scalable Vector Graphics) は、ベクター グラフィックを表現するために使用される XML ベースの画像形式です。以下の手順を使用すると、SVG ファイルの寸法を取得し、PDF として保存できます。

## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。

- C# プログラミング言語の基本的な知識。
- .NET 用の Aspose.PDF ライブラリがシステムにインストールされています。
- Visual Studio などの開発環境。

## ステップ 1: SVG ファイルをロードする
このステップでは、Aspose.PDF for .NET を使用して SVG ファイルを読み込みます。以下のコードに従ってください。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
```

必ず交換してください`"YOUR DOCUMENTS DIRECTORY"` SVG ファイルが置かれている実際のディレクトリに置き換えます。

## ステップ2: ページサイズの調整
SVG ファイルをロードしたので、SVG コンテンツに合わせてページ サイズを調整できます。次のコードを使用します。

```csharp
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
```

上記のコードはページ余白をゼロに設定し、SVG コンテンツに基づいてページ サイズを調整できるようにします。

## ステップ 3: 結果の PDF を保存する
ページ サイズを調整したら、結果の PDF ドキュメントを保存できるようになります。最後のステップは次のとおりです。

```csharp
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

交換する`"YOUR DOCUMENTS DIRECTORY"`出力 PDF ファイルを保存したいディレクトリに置き換えます。
  
### Aspose.PDF for .NET を使用した SVG ディメンションの取得のソース コード例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

## 結論
このチュートリアルでは、Aspose.PDF for .NET を使用して SVG ファイルのサイズを取得する段階的なプロセスについて説明しました。上記の手順に従うことで、SVG ファイルの寸法を取得し、PDF 形式で保存できるようになります。この機能は、ベクター グラフィックの寸法を測定する必要がある場合に役立ちます。

### よくある質問

#### Q: SVG とは何ですか?

A: SVG (Scalable Vector Graphics) は、ベクター グラフィックを表現するために使用される XML ベースの画像形式です。ラスター イメージとは異なり、SVG ファイルは解像度に依存せず、品質を損なうことなく拡大縮小できます。 SVG は Web 上でグラフィックを表示するために広く使用されており、簡単に編集および操作できます。

#### Q: SVG から PDF への変換に .NET 用の Aspose.PDF を使用するのはなぜですか?

A: Aspose.PDF for .NET は、SVG ファイルを処理して PDF 形式に変換するための信頼性が高く効率的な方法を提供します。 PDF で正確に表現できるようにページ サイズ、余白、その他のプロパティを調整するなど、変換プロセスをカスタマイズするためのさまざまなオプションと設定が提供されます。

#### Q: 複雑なグラフィックやテキストを含む SVG ファイルを変換できますか?

A: はい、Aspose.PDF for .NET は、複雑なグラフィックス、テキスト、ベクター要素を含む SVG ファイルを処理できます。変換プロセス中に SVG コンテンツの詳細と品質を正確に保持し、高品質の PDF ドキュメントを生成します。

#### Q: Aspose.PDF for .NET を使用して SVG ファイルからテキストを抽出することはできますか?

A: はい、Aspose.PDF for .NET を使用すると、SVG ファイルからテキストを抽出できます。ライブラリのテキスト抽出機能を使用して、SVG からテキスト要素を抽出し、その後の処理のために個別に保存できます。