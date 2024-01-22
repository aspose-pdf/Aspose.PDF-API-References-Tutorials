---
title: PDFからSVGへ
linktitle: PDFからSVGへ
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF を SVG に変換するためのステップバイステップ ガイド。
type: docs
weight: 180
url: /ja/net/document-conversion/pdf-to-svg/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF を SVG 形式に変換するプロセスを説明します。 SVG (Scalable Vector Graphics) は、グラフィックスの品質とスケーリングを維持するのに役立つベクトル画像形式です。以下の手順でPDFファイルをSVG形式に変換することができます。

## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。

- C# プログラミング言語の基本的な知識。
- .NET 用の Aspose.PDF ライブラリがシステムにインストールされています。
- Visual Studio などの開発環境。

## ステップ 1: PDF ドキュメントをロードする
このステップでは、Aspose.PDF for .NET を使用してソース PDF ファイルをロードします。以下のコードに従ってください。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// PDF ドキュメントをロードする
Document doc = new Document(dataDir + "input.pdf");
```

必ず交換してください`"YOUR DOCUMENTS DIRECTORY"`PDF ファイルが置かれている実際のディレクトリに置き換えます。

## ステップ 2: SVG 保存オプションのインスタンス化
PDF ファイルをロードした後、SVG 保存オプションをインスタンス化します。次のコードを使用します。

```csharp
// SvgSaveOptions オブジェクトをインスタンス化する
SvgSaveOptions saveOptions = new SvgSaveOptions();
//SVG 画像を Zip アーカイブに圧縮しないでください
saveOptions.CompressOutputToZipArchive = false;
```

## ステップ 3: 結果の SVG ファイルを保存する
次に、変換された PDF ファイルを SVG 形式で保存します。次のコードを使用します。

```csharp
//出力をSVGファイルに保存する
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

上記のコードは、変換された PDF を SVG 形式でファイル名を付けて保存します。`"PDFToSVG_out.svg"`.

### Aspose.PDF for .NET を使用した PDF から SVG へのソース コードの例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//PDFドキュメントをロードする
Document doc = new Document(dataDir + "input.pdf");
//SvgSaveOptions のオブジェクトをインスタンス化する
SvgSaveOptions saveOptions = new SvgSaveOptions();
//SVG画像をZipアーカイブに圧縮しないでください
saveOptions.CompressOutputToZipArchive = false;
//出力を SVG ファイルに保存する
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

## 結論
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルを SVG 形式に変換する段階的なプロセスについて説明しました。上記の手順に従うことで、PDF ファイルを SVG 形式に変換できるようになります。この機能は、ベクター イメージに変換するときにグラフィックスの品質とスケーリングを維持したい場合に便利です。

### よくある質問

#### Q: PDF から SVG への変換中に、結果の SVG ファイルの解像度やサイズを制御できますか?

 A: はい、Aspose.PDF for .NET を使用して PDF から SVG への変換中に、結果の SVG ファイルの解像度やサイズを制御できます。の`SvgSaveOptions`クラスは次のようなプロパティを提供します`PageSavingCallback`そして`SaveFormat`解像度、ページ サイズ、または SVG 出力に関連するその他のパラメーターを設定できます。要件に応じてこれらのオプションをカスタマイズして、SVG ファイルの品質とサイズを制御できます。

#### Q: Aspose.PDF for .NET は、暗号化またはパスワードで保護された PDF から SVG への変換をサポートしていますか?

A: はい、Aspose.PDF for .NET は、暗号化またはパスワードで保護された PDF の SVG 形式への変換をサポートしています。パスワードで保護された PDF をロードするときは、`Document`クラス コンストラクター、または`Password`PDF をロードする前にプロパティを変更します。 Aspose.PDF for .NET は、PDF から SVG への変換プロセス中に復号化を処理します。

#### Q: ドキュメント全体ではなく、PDF の特定のページのみを SVG に変換できますか?

A: はい、Aspose.PDF for .NET を使用すると、ドキュメント全体ではなく、PDF の特定のページのみを SVG に変換できます。出力を SVG ファイルとして保存する前に、ページ番号または範囲を指定して、変換するページを選択できます。このようにして、PDF から必要なページのみを抽出して SVG 形式に変換できます。

#### Q: Aspose.PDF for .NET は SVG のすべてのバージョンと互換性がありますか?

A: Aspose.PDF for .NET は、SVG 1.1 (Scalable Vector Graphics) 仕様と互換性があるように設計されています。 SVG 1.1 標準に従って SVG ファイルの生成をサポートします。ただし、SVG 2.0 が SVG 仕様の最新バージョンとして導入されたことに注意してください。 Aspose.PDF for .NET は多くの場合、SVG 2.0 でも問題なく動作しますが、使用する予定の特定の SVG 機能との互換性と潜在的な制限を確認することをお勧めします。