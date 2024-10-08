---
title: フローティングボックスを使用したヘッダー フッターのページ番号
linktitle: フローティングボックスを使用したヘッダー フッターのページ番号
second_title: Aspose.PDF for .NET API リファレンス
description: このステップバイステップのチュートリアルでは、Aspose.PDF for .NET のフローティング ボックスを使用して、PDF のヘッダーとフッターにページ番号を簡単に追加できます。
type: docs
weight: 150
url: /ja/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
## 導入

PDF ドキュメントをプログラムで管理する場合、Aspose.PDF for .NET は優れたツールとして際立っています。.NET アプリケーションで PDF ファイルを作成、編集、操作する方法が簡素化されます。請求書、レポート、その他のドキュメント タイプを作成する場合でも、ページ番号をエレガントに追加することで、PDF の専門性と構成が向上します。このチュートリアルでは、フローティング ボックスを使用して PDF のヘッダーとフッターにページ番号を追加する方法について説明します。準備はできましたか? さあ始めましょう!

## 前提条件

PDF 操作の世界へのこのエキサイティングな旅を始める前に、いくつか必要なものがあります。

### .NET 環境のセットアップ
.NET 開発環境があることを確認してください。.NET アプリケーションの開発者の間で人気のある選択肢である Visual Studio を使用できます。

### Aspose.PDF ライブラリ
Aspose.PDF ライブラリをインストールします。次の Web サイトから簡単にダウンロードできます。

- [Aspose.PDF for .NET をダウンロード](https://releases.aspose.com/pdf/net/)

### C#プログラミングの基礎知識
C# の基礎的な理解は、このチュートリアルで紹介されている概念とコーディング スニペットを理解するのに役立ちます。

### ドキュメントへのアクセス
常に有益である[Aspose.PDF ドキュメント](https://reference.aspose.com/pdf/net/)参照や追加機能の詳細な調査に便利です。

## パッケージのインポート

まず、プロジェクトに必要なパッケージをインポートする必要があります。これにより、コード内で Aspose.PDF アセンブリにアクセスして使用できるようになります。手順は次のとおりです。

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

それでは、フローティング ボックスを使用してページ番号を追加するプロセスを、管理しやすい手順に分解してみましょう。手順に沿って進めていきましょう。

## ステップ1: ドキュメント環境を設定する

まず、PDF ドキュメントを保存するディレクトリを指定します。これは、出力ファイルが保存される場所を決定するため、非常に重要です。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

交換する`YOUR DOCUMENT DIRECTORY`出力 PDF ファイルを保存するパスを指定します。

## ステップ2: ドキュメントをインスタンス化する

次のステップは、新しいPDF文書を作成することです。これには、`Document` Aspose.PDF ライブラリのクラス。

```csharp
//ドキュメントインスタンスをインスタンス化する
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
```
ここで、新しいインスタンスを作成します。`Document`クラスは操作のキャンバスとして機能します。

## ステップ3: 新しいページを追加する

それでは、PDF ドキュメントにページを追加しましょう。すべての PDF には少なくとも 1 ページが必要ですよね?

```csharp
// PDF文書にページを追加する
Aspose.Pdf.Page page = pdf.Pages.Add();
```
このコード スニペットは、ドキュメントに新しいページを追加し、ページ番号を含むフローティング ボックスを含むコンテンツを受け取る準備を整えます。

## ステップ4: フローティングボックスを作成する

次に、ページ番号を保持するフローティングボックスを作成します。`FloatingBox`クラスを使用すると、ページ上でコンテンツを自由に配置できます。

```csharp
// FloatingBoxクラスの新しいインスタンスを初期化します
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);
```
ここで、パラメータ`(140, 80)`フローティング ボックスの幅と高さを指定します。レイアウトの設定に応じてこれらの値を調整できます。

## ステップ5: フローティングボックスの配置

位置が重要です。ページ番号がページのどこに表示されるかを決定します。`Left`そして`Top`位置を指定するためのプロパティ。

```csharp
//段落の左位置を示す浮動小数点値
box1.Left = 2;
//段落の上の位置を示す浮動小数点値
box1.Top = 10;
```
これらの値は、ページ上のフローティング ボックスの配置を決定します。自由に試してみて、ドキュメントに最適なものを見つけてください。

## ステップ6: ページ番号マクロを使用してテキストを追加する

ここで、ページ番号を動的に表示する文字列を追加します。ここで魔法が起こります。

```csharp
// FloatingBoxの段落コレクションにマクロを追加します
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));
```
この場合、`($p/ $P)`現在のページ番号を表示するマクロです（`$p`）と総ページ数（`$P`）。その結果、テキストは「ページ: 1/5」のようにフォーマットされます。

## ステップ7: ページにフローティングボックスを追加する

新しく作成したページに、フローティング ボックスとページ番号テキストを追加します。

```csharp
//ページにフローティングボックスを追加する
page.Paragraphs.Add(box1);
```
この行は基本的に、フローティング ボックスをページに埋め込み、ドキュメントのレイアウトの一部にします。 

## ステップ8: ドキュメントを保存する

最後に、作業を保存することを忘れないでください。最後のステップは、適切なファイル名で PDF ドキュメントを保存することです。

```csharp
//文書を保存する
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```
指定したパスに目的のファイル名が含まれていることを確認してください。これで、ページ番号付きのすばらしい PDF が作成されます。 

## 結論

これで完了です。Aspose.PDF for .NET を使用して PDF のヘッダーとフッターにページ番号を追加するのは、とても簡単です。わずか数行のコードで、アプリケーションでのドキュメント処理をマスターする旅に出ることができます。さまざまなレイアウトや書式設定をためらわずに試してみてください。結局のところ、創造性には限界がありません。プロフェッショナルなドキュメントを作成する準備はできましたか? コーディングの帽子をかぶって、実験を始めましょう。

## よくある質問

### ページ番号テキストの外観をカスタマイズできますか?  
はい、フォントサイズ、色、スタイルなどのテキストプロパティをカスタマイズできます。`TextFragment`プロパティ。

### Aspose.PDF は無料で使用できますか?  
 Aspose.PDFは無料トライアルを提供していますが、実稼働環境での使用には有料製品となります。[ここで購入](https://purchase.aspose.com/buy).

### より詳細なドキュメントはどこで見つかりますか?  
包括的なドキュメントは、[Aspose.PDF ドキュメント サイト](https://reference.aspose.com/pdf/net/).

### 複数のページにヘッダーとフッターを適用するにはどうすればよいですか?  
ドキュメント内のすべてのページをループし、各ページに同様にフローティング ボックスを適用できます。

### 追加機能のサポートが必要な場合はどうすればよいですか?  
追加の質問やサポートについては、[Aspose フォーラム](https://forum.aspose.com/c/pdf/10).