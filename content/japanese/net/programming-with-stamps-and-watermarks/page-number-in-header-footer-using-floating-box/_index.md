---
title: フローティングボックスを使用したヘッダーフッターのページ番号
linktitle: フローティングボックスを使用したヘッダーフッターのページ番号
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ドキュメントのヘッダーとフッターにページ番号を追加する方法を学びます。
type: docs
weight: 150
url: /ja/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
このチュートリアルでは、Aspose.PDF for .NET で FloatingBox を使用して PDF ドキュメントのヘッダーとフッターにページ番号を追加する方法を段階的に説明します。提供された C# ソース コードを使用して PDF ドキュメントを作成し、ページを追加し、FloatingBox を作成し、その位置を設定してページ番号を追加し、変更した PDF ドキュメントを保存します。

## ステップ 1: 環境をセットアップする

始める前に、以下のものがあることを確認してください。

- インストールされた .NET 開発環境。
- .NET 用の Aspose.PDF ライブラリがダウンロードされ、プロジェクトで参照されます。

## ステップ 2: PDF ドキュメントの作成とページの追加

最初のステップは、PDF ドキュメントのインスタンスを作成し、それにページを追加することです。その方法は次のとおりです。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// PDFドキュメントをインスタンス化する
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

//PDF ドキュメントにページを追加する
Aspose.Pdf.Page page = pdf.Pages.Add();
```

「YOUR DOCUMENTS DIRECTORY」を、PDF ドキュメントを保存するディレクトリへの実際のパスに必ず置き換えてください。

## ステップ 3: FloatingBox の作成とページ番号の追加

ページが PDF ドキュメントに追加されたので、FloatingBox を作成し、その位置を設定し、ページ番号を追加できます。その方法は次のとおりです。

```csharp
//幅140、高さ80のFloatingBoxを作成します。
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

//段落の左位置を設定します
box1. Left = 2;

//段落の先頭位置を設定します
box1. Top = 10;

//FloatingBox にページ番号を追加します。
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// FloatingBox をページに追加する
page.Paragraphs.Add(box1);
```

上記のコードは、幅 140、高さ 80 の FloatingBox を作成します。次に、左と上の値を指定して位置を設定します。最後に、構文 "($p/ $P )" を含む TextFragment を使用してページ番号を FloatingBox に追加します。この構文は現在のページ番号と総ページ数に置き換えられます。

## ステップ 4: 変更した PDF ドキュメントを保存する

FloatingBox を使用してページ番号をヘッダーまたはフッターに追加したら、変更した PDF ドキュメントを保存できます。その方法は次のとおりです。

```csharp
//変更した PDF ドキュメントを保存する
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

上記のコードは、編集した PDF ドキュメントを指定されたディレクトリに保存します。

### Aspose.PDF for .NET を使用したフローティング ボックスを使用したヘッダー フッターのページ番号のサンプル ソース コード 
```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//ドキュメントインスタンスをインスタンス化する
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// PDF ドキュメントにページを追加する
Aspose.Pdf.Page page = pdf.Pages.Add();

//FloatingBox クラスの新しいインスタンスを初期化します。
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

//段落の左位置を示す浮動小数点値
box1.Left = 2;

//段落の先頭位置を示す浮動小数点値
box1.Top = 10;

//FloatingBox の段落コレクションにマクロを追加します。
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

//ページにフローティングボックスを追加する
page.Paragraphs.Add(box1);

//文書を保存する
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## 結論

おめでとうございます！ Aspose.PDF for .NET で FloatingBox を使用して、PDF ドキュメントのヘッダーとフッターにページ番号を追加する方法を学習しました。ページ番号などの動的な情報を追加して、ヘッダーとフッターをカスタマイズできるようになりました。

### よくある質問

#### Q: FloatingBox とは何ですか? PDF ドキュメントのヘッダーまたはフッターにページ番号を追加するためにどのように使用されますか?

A: FloatingBox は、テキストや画像などのさまざまなコンテンツを保持できる、Aspose.PDF の多用途のレイアウト要素です。このチュートリアルでは、これを使用してページ番号のコンテナを作成し、現在のページ番号と合計ページ数をヘッダーまたはフッターに動的に挿入できるようにします。

#### Q: 提供されている C# ソース コードでは、FloatingBox を使用してページ番号を追加する方法をどのように実現していますか?

A: コード スニペットは、PDF ドキュメントの作成、ページの追加、FloatingBox の作成、ページ内での位置の設定、TextFragment を使用したページ番号の挿入の方法を示しています。 TextFragment の構文 "($p/ $P )" は、現在のページ番号と総ページ数に置き換えられます。

#### Q: FloatingBox を使用して追加されたページ番号の外観と書式をカスタマイズできますか?

A: はい、FloatingBox 内の TextFragment のプロパティを変更することで、ページ番号の外観をカスタマイズできます。フォントのサイズ、色、スタイル、配置、その他の書式設定オプションを変更できます。

#### Q: 同様のアプローチを使用して、日付や時刻などのさまざまな動的要素をヘッダーまたはフッターに追加することはできますか?

A: もちろん、FloatingBox 内の TextFragment コンテンツを変更することで、日付、時刻、ドキュメントのメタデータ、カスタム テキストなどのさまざまな動的要素を追加できます。ページ番号には「($p/ $P )」、現在の日付には「($date)」などのマクロを使用できます。

#### Q: ヘッダーまたはフッター セクション内で FloatingBox の位置を指定するにはどうすればよいですか?
 A: 提供されたコードは、`Left`そして`Top`プロパティ。これらの値を調整して、ヘッダーまたはフッター セクション内で必要に応じて FloatingBox を配置できます。

#### Q: ヘッダーまたはフッターのページ番号に別のフォントまたはスタイルを使用できますか?

A: はい、FloatingBox 内の TextFragment プロパティを変更することで、ページ番号テキストのフォント、スタイル、その他の書式設定プロパティをカスタマイズできます。

#### Q: FloatingBox 内のコンテンツがその寸法を超えるとどうなりますか?

A: FloatingBox 内のコンテンツがそのサイズを超える場合、コンテンツが切り取られたり、レイアウトの問題が発生したりする可能性があります。 FloatingBox のサイズがコンテンツを収容するのに適切であることを確認し、必要に応じてページ レイアウトを調整することを検討してください。

#### Q: 同じページのヘッダーまたはフッターに、異なるコンテンツを持つ複数の FloatingBox を追加することはできますか?

A: はい、別々の FloatingBox インスタンスを作成し、ページの Paragraphs コレクションに追加することで、異なるコンテンツを持つ複数の FloatingBox を同じページのヘッダーまたはフッターに追加できます。

#### Q: FloatingBox アプローチを使用して、PDF ドキュメントの他のセクション (本文や余白など) にコンテンツを追加できますか?

A: FloatingBox は通常、ヘッダーとフッターに使用されますが、ページ内で適切に配置することで、PDF ドキュメントの他のセクション (本文や余白など) にコンテンツを追加するために使用することもできます。