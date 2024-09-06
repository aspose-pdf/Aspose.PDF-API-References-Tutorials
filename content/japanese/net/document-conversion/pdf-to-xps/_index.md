---
title: PDF から XPS へ
linktitle: PDF から XPS へ
second_title: Aspose.PDF for .NET API リファレンス
description: このステップバイステップ ガイドでは、Aspose.PDF for .NET を使用して PDF を XPS に変換する方法を説明します。開発者やドキュメント処理愛好家に最適です。
type: docs
weight: 220
url: /ja/net/document-conversion/pdf-to-xps/
---
## 導入

今日のデジタル世界では、ドキュメントをある形式から別の形式に変換する必要性がかつてないほど高まっています。アプリケーションにドキュメント処理を統合しようとしている開発者であっても、広く受け入れられている形式でファイルを共有する必要があるビジネス プロフェッショナルであっても、PDF ファイルを XPS (XML Paper Specific) に変換する方法を理解することは非常に役立ちます。このチュートリアルでは、.NET 用の強力な Aspose.PDF ライブラリを使用して PDF を XPS に変換するプロセスについて詳しく説明します。

## 前提条件

始める前に、いくつかの前提条件を満たす必要があります。

1. Visual Studio: マシンに Visual Studio がインストールされていることを確認してください。ここで .NET コードを記述して実行します。
2. .NET Framework: この例では C# を使用するため、.NET Framework に精通していることが必須です。
3.  Aspose.PDFライブラリ: Aspose.PDFライブラリがインストールされている必要があります。[Aspose PDF for .NET リリース ページ](https://releases.aspose.com/pdf/net/).
4. 基本的な C# の知識: C# プログラミングの基礎を理解しておくと、例を理解するのに役立ちます。

## パッケージのインポート

Aspose.PDF を使い始めるには、必要なパッケージをプロジェクトにインポートする必要があります。手順は次のとおりです。

1. Visual Studio を開く: Visual Studio を起動し、新しいプロジェクトを作成します。
2. 参照の追加: ソリューション エクスプローラーでプロジェクトを右クリックし、「NuGet パッケージの管理」を選択して、「Aspose.PDF」を検索します。パッケージをプロジェクトにインストールします。
3. using ディレクティブ: C# ファイルの先頭に、次の using ディレクティブを含めます。

```csharp
using System;
using System.IO;
using Aspose.Pdf;
```

すべての設定が完了したので、変換プロセスを管理しやすいステップに分解してみましょう。

## ステップ1: ドキュメントディレクトリを設定する

PDF を XPS に変換する前に、PDF ファイルが保存されているディレクトリを指定する必要があります。これは、プログラムが入力ファイルの場所を知る必要があるため、非常に重要です。

このステップでは、ドキュメント ディレクトリへのパスを保持する文字列変数を定義します。このパスは PDF ファイルの場所を指す必要があります。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

交換する`"YOUR DOCUMENT DIRECTORY"` PDF ファイルが保存されているマシン上の実際のパスを入力します。

## ステップ2: PDFドキュメントを読み込む

ドキュメント ディレクトリの設定が完了したら、次のステップは、変換する PDF ドキュメントを読み込むことです。

インスタンスを作成します`Document`Aspose.PDF ライブラリからクラスを作成し、PDF ファイルのパスをそのコンストラクターに渡します。これにより、PDF ドキュメントがメモリに読み込まれます。

```csharp
// PDF文書を読み込む
Document pdfDocument = new Document(dataDir + "input.pdf");
```

必ず交換してください`"input.pdf"`実際の PDF ファイルの名前を入力します。

## ステップ3: XPS保存オプションをインスタンス化する

ドキュメントをXPS形式で保存する前に、`XpsSaveOptions`クラス。このクラスを使用すると、ドキュメントを保存するためのさまざまなオプションを指定できます。

インスタンス化することで`XpsSaveOptions`、PDF を XPS に変換する方法をカスタマイズできます。この基本的な変換では、デフォルト設定を使用できます。

```csharp
// XPS保存オプションをインスタンス化する
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();
```

## ステップ4: ドキュメントをXPSとして保存する

最後に、読み込んだ PDF ドキュメントを XPS ファイルとして保存します。ここで魔法が起こります。

あなたは`Save`方法`pdfDocument`オブジェクトに、希望する出力ファイル名と`saveOptions`以前作成したもの。

```csharp
// XPSドキュメントを保存する
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

このコード行は、次の名前のXPSファイルを作成します。`PDFToXPS_out.xps`プロジェクト ディレクトリ内。

## 結論

おめでとうございます! Aspose.PDF for .NET を使用して PDF ドキュメントを XPS 形式に正常に変換できました。このシンプルでありながら強力なライブラリを使用すると、さまざまなドキュメント処理タスクを簡単に処理できます。互換性を高めるためにファイルを変換する場合でも、単にドキュメントを別の形式でアーカイブする場合でも、Aspose.PDF が役立ちます。

## よくある質問

### XPS 形式とは何ですか?
XPS (XML Paper Specific) は、ドキュメントのレイアウトと外観を保持する Microsoft によって開発されたドキュメント形式です。

### 複数の PDF ファイルを一度に XPS に変換できますか?
はい、ディレクトリ内の複数の PDF ファイルをループし、同じ方法を使用して各ファイルを XPS に変換できます。

### Aspose.PDF は無料で使用できますか?
 Aspose.PDFは無料トライアルを提供していますが、フル機能を使用するにはライセンスを購入する必要があります。詳細については、[購入ページ](https://purchase.aspose.com/buy).

### 変換中に問題が発生した場合はどうなりますか?
Asposeコミュニティからサポートを受けることができます。[サポートフォーラム](https://forum.aspose.com/c/pdf/10).

### Aspose.PDF の一時ライセンスを取得できますか?
はい、評価目的で一時ライセンスを申請することができます。[一時ライセンスページ](https://purchase.aspose.com/temporary-license/).