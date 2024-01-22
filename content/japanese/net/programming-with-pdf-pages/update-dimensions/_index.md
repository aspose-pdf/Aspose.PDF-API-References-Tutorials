---
title: PDF ページの寸法を更新する
linktitle: PDF ページの寸法を更新する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ページの寸法を更新するためのステップバイステップ ガイド。必要に応じて寸法を確認してください。
type: docs
weight: 150
url: /ja/net/programming-with-pdf-pages/update-dimensions/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントのページ寸法を更新するプロセスを段階的に説明します。バンドルされている C# ソース コードについて説明し、この機能を理解し、独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後には、Aspose.PDF for .NET を使用して PDF ドキュメントのページ寸法を変更する方法がわかります。

## 前提条件
始める前に、以下のものがあることを確認してください。

- C# プログラミング言語の基本的な知識
- 開発環境にインストールされた Aspose.PDF for .NET

## ステップ 1: ドキュメント ディレクトリを定義する
まず、ドキュメント ディレクトリへのパスを設定する必要があります。これは、編集した PDF ドキュメントを保存する場所です。 「YOUR DOCUMENTS DIRECTORY」を適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: PDF ドキュメントを開く
その後、次のコマンドを使用して既存の PDF ドキュメントを開くことができます。`Document` Aspose.PDF のクラス。必ず正しいドキュメント パスを指定してください。

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## ステップ 3: ページ コレクションを取得する
これで、`Pages`の財産`Document`クラス。

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## ステップ 4: 特定のページを取得する
次に、コレクション内のページのインデックスを使用して、ドキュメントの特定のページを選択できます。この例では、2 ページ目 (インデックス 1) を使用しています。

```csharp
Page pdfPage = pageCollection[1];
```

## ステップ 5: 新しいページのサイズを定義する
これで、`SetPageSize()`の方法`Page`物体。この例では、ページ寸法を A4 (11.7 x 8.3 インチ) に設定し、ポイントに変換します (1 インチ = 72 ポイント)。

```csharp
pdfPage.SetPageSize(597.6, 842.4);
```

## ステップ 6: 更新されたドキュメントを保存する
最後に、更新された PDF ドキュメントをファイルに保存するには、`Save()`の方法`Document`クラス。必ず正しいパスとファイル名を指定してください。

```csharp
dataDir = dataDir + "UpdateDimensions_out.pdf";
pdfDocument.Save(dataDir);
```

### Aspose.PDF for .NET を使用したディメンションの更新のサンプル ソース コード 

```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開いた文書
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
//ページコレクションを取得する
PageCollection pageCollection = pdfDocument.Pages;
//特定のページを取得する
Page pdfPage = pageCollection[1];
//ページ サイズを A4 (11.7 x 8.3 インチ) に設定し、Aspose.Pdf では 1 インチ = 72 ポイントに設定します。
//したがって、A4 のポイント単位の寸法は (842.4, 597.6) になります。
pdfPage.SetPageSize(597.6, 842.4);
dataDir = dataDir + "UpdateDimensions_out.pdf";
//更新されたドキュメントを保存する
pdfDocument.Save(dataDir);
System.Console.WriteLine("\nPage dimensions updated successfully.\nFile saved at " + dataDir);

```

## 結論
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内のページの寸法を更新する方法を学びました。このステップバイステップのガイドに従うことで、必要に応じて PDF ドキュメント内のページのサイズを簡単に変更できます。 Aspose.PDF は、PDF ファイルを操作し、ページ寸法の変更などのさまざまな操作を実行するための強力で柔軟な API を提供します。この知識があれば、特定のニーズに合わせて PDF ページのサイズを制御およびカスタマイズできます。

### PDF ページのサイズの更新に関する FAQ

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメント内の特定のページの寸法を更新するにはどうすればよいですか?

A: Aspose.PDF for .NET を使用して PDF ドキュメント内の特定のページのサイズを更新するには、次の手順に従います。

1. 元の PDF ファイルが存在するパスと、更新された PDF ファイルを保存する場所を指定して、ドキュメント ディレクトリを設定します。 「YOUR DOCUMENTS DIRECTORY」を適切なパスに置き換えます。
2. 既存の PDF ドキュメントを開いて、`Document` Aspose.PDF のクラス。必ず元の PDF ドキュメントへの正しいパスを指定してください。
3.  PDF ドキュメントのページ コレクションにアクセスするには、`Pages`の財産`Document`クラス。
4. ページのインデックスを使用して、ページ コレクションから更新する特定のページを選択します。提供されている C# ソース コードでは、2 ページ目 (インデックス 1) を使用しています。
5. 新しいページ サイズを定義するには、`SetPageSize()`の方法`Page`物体。この例では、ページの寸法を A4 サイズ (11.7 x 8.3 インチ) に設定し、ポイントに変換します (1 インチ = 72 ポイント)。
6. 更新された PDF ドキュメントをファイルに保存するには、`Save()`の方法`Document`クラス。必ず正しいパスとファイル名を指定してください。

#### Q: PDF ドキュメント内の複数のページの寸法を同時に更新できますか?

A: はい、提供されたソース コードを変更して、PDF ドキュメント内の複数のページの寸法を同時に更新できます。特定のページを選択する代わりに (手順 4 を参照)、ページ コレクション内のすべてのページをループして、各ページに必要なページ サイズを設定できます。

#### Q: Aspose.PDF for .NET を使用する場合、ページの寸法をインチからポイントに変換するにはどうすればよいですか?

 A: Aspose.PDF for .NET では、ページの寸法に使用される測定単位はポイントであり、1 インチは 72 ポイントに相当します。インチをポイントに変換するには、次の式を使用できます。`points = inches * 72`。たとえば、ページ サイズを 11.7 x 8.3 インチに設定するには、対応する寸法をポイント単位で (11.7 * 72) および (8.3 * 72) として計算できます。

#### Q: ページのサイズを更新すると、PDF ドキュメントのコンテンツ レイアウトに影響しますか?

A: はい、ページの寸法を更新すると、その特定のページ上の PDF ドキュメントのコンテンツ レイアウトに影響します。ページのサイズを変更すると、ページ上のコンテンツは新しいサイズに収まるように調整されます。

#### Q: 更新後に変更を元に戻し、元のページサイズに戻すことは可能ですか?

A: はい、変更を元に戻して元のページ寸法に戻したい場合は、変更を加える前に元の PDF ドキュメントのコピーを保存するか、変更を保存せずに元の PDF ドキュメントを再度開くことができます。こうすることで、元の寸法が維持されます。