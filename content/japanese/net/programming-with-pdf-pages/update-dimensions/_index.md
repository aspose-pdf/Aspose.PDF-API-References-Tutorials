---
title: PDF ページサイズの更新
linktitle: PDF ページサイズの更新
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ページのサイズを更新するためのステップバイステップ ガイド。ニーズに応じてサイズを確認してください。
type: docs
weight: 150
url: /ja/net/programming-with-pdf-pages/update-dimensions/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントのページ サイズを更新する手順を順を追って説明します。バンドルされている C# ソース コードについて説明し、この機能を理解して独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後には、Aspose.PDF for .NET を使用して PDF ドキュメントのページ サイズを変更する方法がわかります。

## 前提条件
始める前に、次のものがあることを確認してください。

- C#プログラミング言語の基礎知識
- 開発環境に Aspose.PDF for .NET がインストールされている

## ステップ1: ドキュメントディレクトリを定義する
まず、ドキュメント ディレクトリへのパスを設定する必要があります。これは、編集した PDF ドキュメントを保存する場所です。「YOUR DOCUMENTS DIRECTORY」を適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: PDF文書を開く
次に、既存のPDF文書を`Document`Aspose.PDF のクラス。正しいドキュメント パスを必ず指定してください。

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## ステップ3: ページコレクションを取得する
これで、PDF文書のページコレクションにアクセスできます。`Pages`の財産`Document`クラス。

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## ステップ4: 特定のページを取得する
次に、コレクション内のページのインデックスを使用して、ドキュメントの特定のページを選択できます。この例では、2 番目のページ (インデックス 1) を使用しています。

```csharp
Page pdfPage = pageCollection[1];
```

## ステップ5: 新しいページのサイズを定義する
これで、新しいページサイズを設定できます。`SetPageSize()`方法の`Page`オブジェクト。この例では、ページのサイズを A4 (11.7 x 8.3 インチ) に設定し、ポイント (1 インチ = 72 ポイント) に変換しています。

```csharp
pdfPage.SetPageSize(597.6, 842.4);
```

## ステップ6: 更新したドキュメントを保存する
最後に、更新されたPDF文書をファイルに保存するには、`Save()`方法の`Document`クラス。正しいパスとファイル名を必ず指定してください。

```csharp
dataDir = dataDir + "UpdateDimensions_out.pdf";
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET を使用してディメンションを更新するためのサンプル ソース コード 

```csharp

//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントを開く
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
//ページコレクションを取得
PageCollection pageCollection = pdfDocument.Pages;
//特定のページを取得する
Page pdfPage = pageCollection[1];
//ページサイズをA4（11.7 x 8.3インチ）に設定し、Aspose.Pdfでは1インチ = 72ポイントです。
//したがって、A4の寸法はポイントで（842.4、597.6）になります。
pdfPage.SetPageSize(597.6, 842.4);
dataDir = dataDir + "UpdateDimensions_out.pdf";
//更新されたドキュメントを保存する
pdfDocument.Save(dataDir);
System.Console.WriteLine("\nPage dimensions updated successfully.\nFile saved at " + dataDir);

```

## 結論
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントのページのサイズを更新する方法を学習しました。このステップ バイ ステップ ガイドに従うことで、必要に応じて PDF ドキュメントのページのサイズを簡単に変更できます。Aspose.PDF は、PDF ファイルを操作し、ページ サイズの変更など、さまざまな操作を実行するための強力で柔軟な API を提供します。この知識があれば、特定のニーズに合わせて PDF ページのサイズを制御およびカスタマイズできます。

### PDF ページ サイズの更新に関する FAQ

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメント内の特定のページのサイズを更新するにはどうすればよいですか?

A: Aspose.PDF for .NET を使用して PDF ドキュメント内の特定のページのサイズを更新するには、次の手順に従います。

1. 元の PDF ファイルがあるパスと更新された PDF ファイルを保存するパスを指定して、ドキュメント ディレクトリを設定します。「YOUR DOCUMENTS DIRECTORY」を適切なパスに置き換えます。
2. 更新する既存のPDF文書を開き、`Document`Aspose.PDF のクラス。元の PDF ドキュメントへの正しいパスを必ず指定してください。
3.  PDF文書のページコレクションにアクセスするには、`Pages`の財産`Document`クラス。
4. ページのインデックスを使用して、ページ コレクションから更新する特定のページを選択します。提供されている C# ソース コードでは、2 番目のページ (インデックス 1) を使用しています。
5. 新しいページサイズを定義するには、`SetPageSize()`方法の`Page`オブジェクト。例では、ページのサイズを A4 サイズ (11.7 x 8.3 インチ) に設定し、ポイント (1 インチ = 72 ポイント) に変換しています。
6. 更新されたPDF文書をファイルに保存するには、`Save()`方法の`Document`クラス。正しいパスとファイル名を必ず指定してください。

#### Q: PDF ドキュメント内の複数のページのサイズを同時に更新できますか?

A: はい、提供されているソース コードを変更して、PDF ドキュメント内の複数のページのサイズを同時に更新できます。特定のページを選択する代わりに (手順 4 を参照)、ページ コレクション内のすべてのページをループし、各ページに希望のページ サイズを設定できます。

#### Q: Aspose.PDF for .NET を使用する場合、ページ寸法をインチからポイントに変換するにはどうすればよいですか?

 A: Aspose.PDF for .NET では、ページ寸法の測定単位はポイントです。1 インチは 72 ポイントに相当します。インチをポイントに変換するには、次の数式を使用します。`points = inches * 72`たとえば、ページ サイズを 11.7 x 8.3 インチに設定するには、対応するポイント単位の寸法を (11.7 * 72) および (8.3 * 72) として計算できます。

#### Q: ページのサイズを更新すると、PDF ドキュメントのコンテンツ レイアウトに影響しますか?

A: はい、ページのサイズを更新すると、その特定のページの PDF ドキュメントのコンテンツ レイアウトに影響します。ページのサイズを変更すると、ページ上のコンテンツは新しいサイズに合わせて調整されます。

#### Q: 更新後に変更を元に戻し、元のページ寸法に戻すことは可能ですか?

A: はい、変更を元に戻して元のページ寸法を復元したい場合は、変更を加える前に元の PDF ドキュメントのコピーを保存するか、変更を保存せずに元の PDF ドキュメントを再度開きます。この方法では、元の寸法が保持されます。