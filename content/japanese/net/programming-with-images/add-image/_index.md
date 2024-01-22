---
title: PDF ファイルに画像を追加
linktitle: PDF ファイルに画像を追加
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、PDF ファイルに画像を簡単に追加できます。
type: docs
weight: 10
url: /ja/net/programming-with-images/add-image/
---
このガイドでは、Aspose.PDF for .NET を使用して PDF ファイルに画像を追加する方法を段階的に説明します。環境がすでにセットアップされていることを確認し、以下の手順に従ってください。

## ステップ 1: ドキュメント ディレクトリを定義する

開始する前に、ドキュメント用に正しいディレクトリを設定していることを確認してください。交換する`"YOUR DOCUMENT DIRECTORY"`コード内で、PDF ドキュメントが配置されているディレクトリへのパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ドキュメントを開く

このステップでは、`Document` Aspose.PDF のクラス。使用`Document`コンストラクターを開き、PDF ドキュメントへのパスを渡します。

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## ステップ 3: 画像座標を設定する

追加したい画像の座標を設定します。変数`lowerLeftX`, `lowerLeftY`, `upperRightX`そして`upperRightY`はそれぞれ画像の左下隅と右上隅の座標を表します。

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
```

## ステップ 4: 画像を追加するページを取得する

PDF ドキュメントの特定のページに画像を追加するには、まずそのページを取得する必要があります。この例では、ドキュメントの 2 ページ目 (インデックス 1) に画像を追加します。

```csharp
Page page = pdfDocument.Pages[1];
```

## ステップ 5: ストリームから画像をロードする

ここで、PDF ドキュメントに追加する画像をロードします。この例では、という名前の画像ファイルがあることを前提としています。`aspose-logo.jpg`ドキュメントと同じディレクトリにあります。必要に応じてファイル名を置き換えます。

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
```

## ステップ 6: 画像をページアセットに追加する

PDF ドキュメントで画像を使用するには、ページのリソース画像コレクションに画像を追加する必要があります。

```csharp
page.Resources.Images.Add(imageStream);
```

## ステップ 7: 現在のグラフィックス状態を保存する

画像を描画する前に、次のコマンドを使用して現在のグラフィックス状態を保存する必要があります。`GSave`オペレーター。これにより、グラフィックス状態への変更を後でロールバックできるようになります。

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
```

## ステップ 8: Rectangle オブジェクトと Matrix オブジェクトを作成する

これから作成します`Rectangle`オブジェクトと`Matrix`物体。長方形は画像の位置とサイズを表し、行列は画像をどのように配置するかを定義します。

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lower

LeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

## ステップ 9: 画像配置のために行列を連結する

画像を四角形内に配置する方法を指定するには、`ConcatenateMatrix`オペレーター。この演算子は、画像の座標空間をページの座標空間にマッピングする変換行列を定義します。

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
```

## ステップ 10: 画像を描画する

このステップでは、`Do`オペレーター。の`Do`オペレーターはリソースから画像名を取得し、それをページ上に描画します。

```csharp
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
```

## ステップ 11: グラフィックス状態を復元する

画像を描画した後、次のコマンドを使用して以前のグラフィックス状態を復元する必要があります。`GRestore`オペレーター。

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
```

## ステップ 12: 更新されたドキュメントを保存する

最後に、更新されたドキュメントを新しいファイルに保存します。を更新します`dataDir`変数に目的の出力ディレクトリとファイル名を指定します。

```csharp
dataDir = dataDir + "AddImage_out.pdf";
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET を使用した画像の追加のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開いた文書
Document pdfDocument = new Document(dataDir+ "AddImage.pdf");
//座標を設定する
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
//画像を追加する必要があるページを取得する
Page page = pdfDocument.Pages[1];
//画像をストリームにロードする
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
//ページリソースの画像コレクションに画像を追加します
page.Resources.Images.Add(imageStream);
//GSave オペレーターの使用: このオペレーターは現在のグラフィックス状態を保存します。
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
// Rectangle オブジェクトと Matrix オブジェクトを作成する
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
//ConcatenateMatrix (連結行列) 演算子の使用: 画像をどのように配置するかを定義します
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
//Do 演算子の使用: この演算子は画像を描画します
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
//GRestore オペレーターの使用: このオペレーターはグラフィックス状態を復元します。
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
dataDir = dataDir + "AddImage_out.pdf";
//更新されたドキュメントを保存する
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage added successfully.\nFile saved at " + dataDir); 
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントに画像を追加する方法を学びました。ドキュメントを開くところから更新バージョンを保存するところまで、すべての手順を詳しく説明しました。このガイドに従うと、C# と Aspose.PDF を使用してプログラムで PDF ファイルに画像を埋め込むことができるようになります。

### PDF ファイルへの画像の追加に関する FAQ

#### Q: PDF ドキュメントに画像を追加する必要があるのはなぜですか?

A: PDF ドキュメントに画像を追加すると、視覚的なコンテンツが強化され、追加のコンテキストが提供されたり、PDF ファイルにロゴやグラフィックが組み込まれたりすることができます。

#### Q: PDF ドキュメント内の特定のページに画像を追加できますか?

A: はい、画像を追加するページを指定できます。提供されたコードでは、画像が PDF ドキュメントの 2 ページ目に追加されます。

#### Q: 追加した画像の位置やサイズを調整するにはどうすればよいですか?

 A: 変更できます。`lowerLeftX`, `lowerLeftY`, `upperRightX` 、 そして`upperRightY`コード内の変数を使用して画像の座標を設定し、ページ上のサイズと位置を制御します。

#### Q: この方法ではどのような種類の画像形式を追加できますか?

A: 提供されているコード例では、JPG 画像をロードしていることを前提としています (`aspose-logo.jpg`）。 Aspose.PDF for .NET は、PNG、BMP、GIF などのさまざまな画像形式をサポートしています。

#### Q: 追加した画像が指定された座標内に収まるようにするにはどうすればよいですか?

 A: 必ず座標とサイズを調整してください。`Rectangle`物体 （`rectangle`画像のサイズとページ上の目的の配置を一致させます。

#### Q: 1 つの PDF ページに複数の画像を追加できますか?

A: はい、各画像に対してこのプロセスを繰り返し、それに応じて座標やその他のパラメータを調整することで、複数の画像を 1 つの PDF ページに追加できます。

####  Q: どうやって`GSave` and `GRestore` operator work in the code?

 A:`GSave`オペレータは現在のグラフィックス状態を保存するため、グラフィックス コンテキスト全体に影響を与えることなく変更を加えることができます。の`GRestore`変更が加えられた後、オペレータは以前のグラフィックス状態を復元します。

#### Q: 指定されたパスにイメージ ファイルが見つからない場合はどうなりますか?

A: 指定されたパスにイメージ ファイルが見つからない場合、コードはイメージ ストリームをロードしようとすると例外をスローします。イメージ ファイルが正しいディレクトリに配置されていることを確認してください。

#### Q: 画像の配置と外観をさらにカスタマイズできますか?

 A: はい、画像の外観をカスタマイズするには、`Matrix`オブジェクトを調整し、コード内の他の演算子を調整します。高度なカスタマイズについては、Aspose.PDF ドキュメントを参照してください。

#### Q: 画像が PDF に正常に追加されたかどうかをテストするにはどうすればよいですか?

A: 提供されたコードを適用して画像を追加した後、変更した PDF ファイルを開き、指定したページに画像が正しい配置で表示されることを確認します。

#### Q: 画像を追加すると、PDF ドキュメントの元のコンテンツに影響しますか?

A: 画像を追加しても、PDF ドキュメントの元のコンテンツには影響しません。視覚的な要素を含めることで文書を強化します。