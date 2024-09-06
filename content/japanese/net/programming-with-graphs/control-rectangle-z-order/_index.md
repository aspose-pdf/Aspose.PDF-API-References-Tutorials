---
title: PDF ファイル内の四角形の Z 順序を制御する
linktitle: PDF ファイル内の四角形の Z 順序を制御する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内の四角形の Z 順序を制御する方法を学習します。
type: docs
weight: 40
url: /ja/net/programming-with-graphs/control-rectangle-z-order/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して四角形の Z 順序を制御するための次の C# ソース コードを段階的に説明します。

始める前に、Aspose.PDF ライブラリがインストールされ、開発環境が設定されていることを確認してください。また、C# プログラミングの基本的な知識も必要です。

## ステップ1: ドキュメントディレクトリの設定

提供されているソース コードでは、結果の PDF ファイルを保存するディレクトリを指定する必要があります。「dataDir」変数を目的のディレクトリに変更します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: ドキュメント オブジェクトのインスタンス化とページの追加

Document クラスのインスタンスを作成し、このドキュメントにページを追加します。

```csharp
Document doc1 = new Document();
Aspose.Pdf.Page page1 = doc1.Pages.Add();
```

## ステップ3: ページサイズの設定

SetPageSize メソッドを使用して PDF ページ サイズを設定します。

```csharp
page1.SetPageSize(375, 300);
```

## ステップ4: ページ余白の設定

PageInfo オブジェクトのプロパティを使用して、ページの余白を設定できます。

```csharp
page1.PageInfo.Margin.Left = 0;
page1.PageInfo.Margin.Top = 0;
```

## ステップ5: Zオーダーを指定して四角形を追加する

さまざまな色と指定された Z オーダーを持つ長方形を作成し、ページに追加します。

```csharp
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
```

## ステップ6: 結果のPDFファイルを保存する

最後に、結果の PDF ファイルを「ControlRectangleZOrder_out.pdf」という名前で指定したディレクトリに保存します。

```csharp
doc1.Save(dataDir);
```
### Aspose.PDF for .NET を使用して四角形の Z オーダーを制御するサンプル ソース コード 

```csharp

//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Documentクラスオブジェクトをインスタンス化する
Document doc1 = new Document();
//PDFファイルのページコレクションにページを追加する
Aspose.Pdf.Page page1 = doc1.Pages.Add();
//PDFページのサイズを設定する
page1.SetPageSize(375, 300);
//ページオブジェクトの左余白を0に設定する
page1.PageInfo.Margin.Left = 0;
//ページオブジェクトの上余白を0に設定する
page1.PageInfo.Margin.Top = 0;
//色を赤、Zオーダーを0、寸法を指定した新しい四角形を作成します。
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
//色を青、Zオーダーを0、寸法を指定した新しい四角形を作成します。
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
//色を緑、Zオーダーを0、寸法を指定した新しい四角形を作成します。
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
dataDir = dataDir + "ControlRectangleZOrder_out.pdf";
//結果のPDFファイルを保存する
doc1.Save(dataDir);

```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して四角形の Z オーダーを制御する方法について説明しました。この知識を使用して、PDF ファイル内の四角形を正確に配置およびレイヤー化できるようになりました。

### FAQ の PDF ファイル内の四角形の Z 順序の制御

#### Q: このチュートリアルの目的は何ですか?

A: このチュートリアルでは、Aspose.PDF for .NET を使用して四角形の Z 順序を制御し、PDF ファイル内で四角形を配置およびレイヤー化するプロセスを案内します。

#### Q: 始める前に必要な前提条件は何ですか?

A: 始める前に、Aspose.PDF ライブラリがインストールされ、開発環境が設定されていることを確認してください。また、C# プログラミングの基礎を理解しておくことをお勧めします。

#### Q: PDF ファイルを保存するディレクトリを指定するにはどうすればよいですか?

A: 提供されているソース コードで、「dataDir」変数を変更して、結果の PDF ファイルを保存するディレクトリを指定できます。

#### Q: ページサイズと余白を設定する目的は何ですか?

A: ページ サイズと余白を設定すると、PDF ページのレイアウトを構成し、四角形を配置できるキャンバスが提供されます。

#### Q: Z 順序を指定して四角形を追加するにはどうすればよいですか?

A: 長方形を作成してページに追加することができます。`AddRectangle`メソッドでは、各四角形の位置、寸法、色、Z 順序を指定します。

#### Q: Z オーダーとは何ですか? また、なぜ重要ですか?

A: Z オーダーは、ページ上のオブジェクトの重ね順を決定します。Z オーダー値が高いオブジェクトは、Z オーダー値が低いオブジェクトよりも上に配置され、可視性とレイヤーに影響します。

#### Q: 長方形の色と寸法をカスタマイズできますか?

 A: はい、四角形の色、位置、寸法は、渡されるパラメータを変更することでカスタマイズできます。`AddRectangle`方法。

#### Q: 長方形を配置した後、結果の PDF ファイルをどのように保存すればよいですか?

 A: 長方形を配置した後、結果のPDFファイルを`doc1.Save(dataDir);`提供されたソースコード内の行。