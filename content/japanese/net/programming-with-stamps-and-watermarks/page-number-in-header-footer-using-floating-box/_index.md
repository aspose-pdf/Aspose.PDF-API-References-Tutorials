---
title: フローティングボックスを使用したヘッダー フッターのページ番号
linktitle: フローティングボックスを使用したヘッダー フッターのページ番号
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ドキュメントのヘッダーとフッターにページ番号を追加する方法を学習します。
type: docs
weight: 150
url: /ja/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
このチュートリアルでは、Aspose.PDF for .NET で FloatingBox を使用して PDF ドキュメントのヘッダーとフッターにページ番号を追加する方法を段階的に説明します。提供されている C# ソース コードを使用して PDF ドキュメントを作成し、ページを追加し、FloatingBox を作成し、その位置を設定してページ番号を追加し、変更した PDF ドキュメントを保存します。

## ステップ1: 環境の設定

始める前に、次のものがあることを確認してください。

- インストールされた .NET 開発環境。
- .NET 用の Aspose.PDF ライブラリがダウンロードされ、プロジェクトで参照されます。

## ステップ2: PDF文書を作成し、ページを追加する

最初のステップは、PDF ドキュメントのインスタンスを作成し、それにページを追加することです。手順は次のとおりです。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// PDFドキュメントをインスタンス化する
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

//PDF文書にページを追加する
Aspose.Pdf.Page page = pdf.Pages.Add();
```

「YOUR DOCUMENTS DIRECTORY」を、PDF ドキュメントを保存するディレクトリへの実際のパスに置き換えてください。

## ステップ3: FloatingBoxを作成し、ページ番号を追加する

PDF ドキュメントにページが追加されたので、FloatingBox を作成し、その位置を設定し、ページ番号を追加できます。手順は次のとおりです。

```csharp
//幅140、高さ80のFloatingBoxを作成します。
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

//段落の左位置を設定する
box1. Left = 2;

//段落の上の位置を設定する
box1. Top = 10;

//FloatingBoxにページ番号を追加する
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

//ページにFloatingBoxを追加する
page.Paragraphs.Add(box1);
```

上記のコードは、幅 140、高さ 80 の FloatingBox を作成します。次に、左と上の値を指定して位置を設定します。最後に、現在のページ番号と合計ページ数に置き換えられる構文 "($p/ $P )" を含む TextFragment を使用して、FloatingBox にページ番号を追加します。

## ステップ4: 変更したPDF文書を保存する

FloatingBox を使用してヘッダーまたはフッターにページ番号を追加したら、変更した PDF ドキュメントを保存できます。手順は次のとおりです。

```csharp
//変更したPDF文書を保存する
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

上記のコードは、編集された PDF ドキュメントを指定されたディレクトリに保存します。

### Aspose.PDF for .NET を使用したフローティング ボックスを使用したヘッダー フッターのページ番号のサンプル ソース コード 
```csharp

//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//ドキュメントインスタンスをインスタンス化する
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

//PDF文書にページを追加する
Aspose.Pdf.Page page = pdf.Pages.Add();

//FloatingBoxクラスの新しいインスタンスを初期化します
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

//段落の左位置を示す浮動小数点値
box1.Left = 2;

//段落の上の位置を示す浮動小数点値
box1.Top = 10;

//FloatingBoxの段落コレクションにマクロを追加します
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

//ページにフローティングボックスを追加する
page.Paragraphs.Add(box1);

//文書を保存する
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## 結論

おめでとうございます！ Aspose.PDF for .NET で FloatingBox を使用して PDF ドキュメントのヘッダーとフッターにページ番号を追加する方法を学習しました。 ページ番号などの動的な情報を追加して、ヘッダーとフッターをカスタマイズできるようになりました。

### よくある質問

#### Q: FloatingBox とは何ですか? また、PDF ドキュメントのヘッダーまたはフッターにページ番号を追加するにはどのように使用しますか?

A: FloatingBox は、テキストや画像など、さまざまなコンテンツを保持できる Aspose.PDF の多目的レイアウト要素です。このチュートリアルでは、ページ番号のコンテナーを作成するために使用し、現在のページ番号と合計ページ数をヘッダーまたはフッターに動的に挿入できるようにします。

#### Q: 提供されている C# ソース コードでは、FloatingBox を使用してページ番号をどのように追加するのでしょうか?

A: コード スニペットは、PDF ドキュメントを作成し、ページを追加し、FloatingBox を作成し、ページ内での位置を設定し、TextFragment を使用してページ番号を挿入する方法を示しています。TextFragment 内の構文 "($p/ $P )" は、現在のページ番号と合計ページ数に置き換えられます。

#### Q: FloatingBox を使用して追加されたページ番号の外観と書式をカスタマイズできますか?

A: はい、FloatingBox 内の TextFragment のプロパティを変更することで、ページ番号の外観をカスタマイズできます。フォント サイズ、色、スタイル、配置、その他の書式設定オプションを変更できます。

#### Q: 同様のアプローチを使用して、日付や時刻などのさまざまな動的要素をヘッダーやフッターに追加することは可能ですか?

A: もちろんです。FloatingBox 内の TextFragment コンテンツを変更することで、日付、時刻、ドキュメント メタデータ、カスタム テキストなどのさまざまな動的要素を追加できます。ページ番号には「($p/ $P )」、現在の日付には「($date)」などのマクロを使用できます。

#### Q: ヘッダーまたはフッター セクション内で FloatingBox の位置を指定するにはどうすればよいですか?
 A: 提供されたコードは、FloatingBoxの位置を次のように設定します。`Left`そして`Top`プロパティ。これらの値を調整して、ヘッダーまたはフッター セクション内で FloatingBox を必要に応じて配置できます。

#### Q: ヘッダーまたはフッターのページ番号に別のフォントやスタイルを使用できますか?

A: はい、FloatingBox 内の TextFragment プロパティを変更することで、ページ番号テキストのフォント、スタイル、その他の書式設定プロパティをカスタマイズできます。

#### Q: FloatingBox 内のコンテンツがその寸法を超えた場合はどうなりますか?

A: FloatingBox 内のコンテンツがサイズを超えると、コンテンツが切り取られたり、レイアウトの問題が発生する可能性があります。FloatingBox のサイズがコンテンツを収容するのに適していることを確認し、必要に応じてページ レイアウトを調整することを検討してください。

#### Q: 同じページのヘッダーまたはフッターに、異なるコンテンツを持つ複数の FloatingBox を追加することは可能ですか?

A: はい、個別の FloatingBox インスタンスを作成し、それをページの Paragraphs コレクションに追加することで、同じページのヘッダーまたはフッターに異なるコンテンツを持つ複数の FloatingBox を追加できます。

#### Q: FloatingBox アプローチを使用して、PDF ドキュメントの本文や余白などの他のセクションにコンテンツを追加できますか?

A: FloatingBox は一般的にヘッダーとフッターに使用されますが、ページ内で適切に配置することで、本文や余白など PDF ドキュメントの他のセクションにコンテンツを追加するためにも使用できます。