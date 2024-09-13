---
title: PDF ファイルのページ番号スタンプ
linktitle: PDF ファイルのページ番号スタンプ
second_title: Aspose.PDF for .NET API リファレンス
description: コード例付きのわかりやすいガイドを通じて、Aspose.PDF for .NET を使用して PDF ファイルにページ番号スタンプを追加する方法を学習します。
type: docs
weight: 160
url: /ja/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
## 導入

PDF ドキュメントにページ番号を付けて、簡単にナビゲートできるようにしたいと思ったことはありませんか? ノートを共有する学生、レポートを発表する専門家、または複数ページのドキュメントを管理する人など、ページ番号を追加すると PDF ファイルの明瞭性が大幅に向上します。幸いなことに、強力な Aspose.PDF for .NET ライブラリを使用すると、PDF ドキュメントにページ番号スタンプを簡単に追加できます。このガイドでは、必要な知識がすべて身に付くように、プロセス全体をステップごとに説明します。さあ、始めましょう!

## 前提条件

PDF ドキュメントにページ番号スタンプを追加する前に、次の前提条件が満たされていることを確認してください。

1. Visual Studio: システムに Visual Studio がインストールされていることを確認してください。ここでコードを記述して実行します。
2. .NET Framework: Aspose.PDF は .NET アプリケーション用に設計されているため、C# プログラミングと .NET Framework の知識が必須です。
3.  Aspose.PDFライブラリ: Aspose.PDFライブラリは、[Aspose PDF リリース](https://releases.aspose.com/pdf/net/). 
4. PDF の基本的な理解: 専門家である必要はありませんが、PDF ファイルの仕組みに関する基本的な理解があれば、チュートリアルをよりよく理解できるようになります。

これらの前提条件を設定したら、ページ番号のスタンプを開始する準備が整います。

## パッケージのインポート

コーディングを始める前に、必要な Aspose.PDF パッケージがプロジェクトにインポートされていることを確認する必要があります。これは、ライブラリ関数をシームレスに活用するために重要です。手順は次のとおりです。

### 新しいプロジェクトを作成する

1. Visual Studio を開きます。
2. クリック`File` >`New` >`Project`.
3. C#に適したテンプレート（例：コンソールアプリケーション）を選択し、名前を付けてクリックします。`Create`.

### Aspose.PDF 参照の追加

1. ソリューション エクスプローラーでプロジェクト名を右クリックします。
2. クリック`Manage NuGet Packages`.
3. 検索する`Aspose.PDF`最新バージョンをインストールしてください。

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

ライブラリの準備ができたので、コーディングに取り掛かりましょう。

環境がセットアップされたので、次は PDF ファイルにページ番号スタンプを追加します。理解しやすいように、このプロセスを明確な手順に分解します。

## ステップ1: ドキュメントディレクトリを指定する

まず、PDF ファイルが保存されているディレクトリを指定する必要があります。これがプロジェクトの開始点となります。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; //このパスを更新
```

説明: 置き換え`"YOUR DOCUMENT DIRECTORY"`PDF ファイルを含むディレクトリへのパスを指定します。これは、操作するファイルの場所をコードに指示するため、非常に重要です。

## ステップ2: ドキュメントを開く

次に、ページ番号スタンプを追加する既存の PDF ドキュメントを開きます。

```csharp
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

説明: ここでは、`Document`特定の PDF ファイルを開くために Aspose.PDF によって提供されるクラス。ファイル名がディレクトリにある実際のファイルと一致していることを確認してください。

## ステップ3: ページ番号スタンプを作成する

次は楽しい部分です。PDF に追加するページ番号スタンプを作成しましょう。

```csharp
PageNumberStamp pageNumberStamp = new PageNumberStamp();
```

説明:`PageNumberStamp`クラスを使用すると、ドキュメントの総ページ数に対する現在のページ番号を表示するスタンプを作成できます。

## ステップ4: スタンプを設定する

次に、スタンプの設定を構成する必要があります。ここで、スタンプの外観と動作を設計します。

```csharp
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;
```

説明：
- `Background = false`: スタンプが最前面に表示されることを意味します。
- `Format`: ここでは、「ページ X / Y」を表示するようにフォーマットを設定し、ドキュメントの合計ページ数を動的に取得します。
- `BottomMargin`: ページの下部からの距離を調整します。
- `HorizontalAlignment`: スタンプを水平方向に中央揃えします。
- `StartingNumber`: 開始ページ番号を設定します。通常は 1 から始まります。

## ステップ5: テキストプロパティを設定する

次に、スタンプ内のテキストの外観をカスタマイズできます。

```csharp
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

説明: これらの属性は、スタンプ内のテキストのフォントの種類、フォント サイズ、スタイル (太字と斜体)、色を構成して、見た目を魅力的にします。

## ステップ6: 特定のページにスタンプを追加する

スタンプを設定したら、それをドキュメント内の特定のページに追加します。

```csharp
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

説明: この行はPDFの最初のページにスタンプを追加します。`Pages[1]`必要に応じて他のページのインデックスを作成します。

## ステップ7: 出力ドキュメントを保存する

最後に、変更した PDF ドキュメントを保存して、変更内容を永続的に保存します。

```csharp
dataDir = dataDir + "PageNumberStamp_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);
```

説明: 出力ファイルのパスを定義し、ドキュメントを保存しています。コンソールに、スタンプが正常に追加されたことと、ファイルが保存された場所が表示されます。

## 結論

Aspose.PDF for .NET を使用して PDF ファイルにページ番号スタンプを追加するのは簡単なだけでなく、高度にカスタマイズ可能です。ページ番号スタンプの作成をステップごとに説明し、その過程で明確なガイダンスが得られるようにしました。これで、PDF ドキュメントを強化して、よりユーザーフレンドリーでプロフェッショナルなものにするための知識が身につきました。 

## よくある質問

### ページ番号の外観をカスタマイズできますか?  
はい。ガイドに示されているように、ページ番号のフォント、サイズ、色、書式を変更できます。

### Aspose.PDF は無料で使用できますか?  
 Aspose.PDFは無料トライアルを提供していますが、広範囲に使用するにはライセンスが必要です。[購入ページ](https://purchase.aspose.com/buy)詳細については。

### 実装中に問題が発生した場合はどうなりますか?  
訪問することができます[Aspose サポート フォーラム](https://forum.aspose.com/c/pdf/10)援助をお願いします。

### 複数のページのページ番号を自動的に生成するにはどうすればよいですか?  
ガイドのコードはページの合計数を自動的に計算するため、複数のページのカスタマイズが簡単になります。

### Aspose.PDF を他のプログラミング言語で使用できますか?  
このガイドは .NET に重点を置いていますが、Aspose には Java、Python などのライブラリもあります。