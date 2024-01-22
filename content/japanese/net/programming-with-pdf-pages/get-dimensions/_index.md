---
title: PDF ページの寸法を取得する
linktitle: PDF ページの寸法を取得する
second_title: Aspose.PDF for .NET API リファレンス
description: このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ページの寸法を取得し、操作を実行する方法を説明します。プロセスをガイドする詳細な手順が提供されます。
type: docs
weight: 60
url: /ja/net/programming-with-pdf-pages/get-dimensions/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルのページ寸法を取得するプロセスを段階的に説明します。バンドルされている C# ソース コードについて説明し、この機能を理解し、独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後には、Aspose.PDF for .NET を使用して PDF ファイル内のページの寸法を取得する方法がわかります。

## 前提条件
始める前に、以下のものがあることを確認してください。

- C# プログラミング言語の基本的な知識
- 開発環境にインストールされた Aspose.PDF for .NET

## ステップ 1: ドキュメント ディレクトリを定義する
まず、ドキュメント ディレクトリへのパスを設定する必要があります。これは PDF ファイルがある場所です。 「YOUR DOCUMENTS DIRECTORY」を適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: PDF ドキュメントを開く
次に、次のコマンドを使用して PDF ファイルを開くことができます。`Document` Aspose.PDF のクラス。 PDF ファイルへの正しいパスを指定してください。

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## ステップ 3: 空白ページを追加する (必要な場合)
 PDF ドキュメントに既にページが含まれている場合は、インデックスを使用して既存のページにジャンプできます。`1` (最初のページのインデックスは 1 です)。それ以外の場合は、ドキュメントに新しいページを追加できます。

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## ステップ 4: ページのサイズを取得する
を使用してページの寸法を取得できるようになりました。`GetPageRect()`の方法`Page`物体。このメソッドは、`Rectangle`ページの寸法を含むオブジェクト。幅と高さにアクセスするには、`Width`そして`Height`プロパティ。

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## ステップ 5: ページを回転する
ページを回転したい場合は、`Rotate`の財産`Page`物体。この例では、ページが 90 度回転されます。

```csharp
page. Rotate = Rotate. on90;
```

## ステップ 6: ページのサイズを再度取得する
ページを回転した後、次のコマンドを使用してページの寸法を再度取得できます。`GetPageRect()`方法。

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### Aspose.PDF for .NET を使用したディメンションの取得のサンプル ソース コード 

```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開いた文書
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
//PDF ドキュメントに空白ページを追加します
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
//ページの高さと幅の情報を取得する
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
//ページを 90 度の角度で回転します
page.Rotate = Rotation.on90;
//ページの高さと幅の情報を取得する
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## 結論
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイル内のページの寸法を取得する方法を学びました。記載されている手順に従うことで、ページの寸法を抽出し、その他の PDF 操作操作を簡単に実行できます。 Aspose.PDF for .NET は、PDF ファイルの操作に優れた柔軟性を提供し、強力なカスタマイズされたソリューションを開発できます。

Aspose.PDF のドキュメントをさらに詳しく調べて、このライブラリが提供するすべての機能を確認してください。

### PDF ページのサイズを取得するための FAQ

#### Q: PDF ファイル内の特定のページの寸法を取得するにはどうすればよいですか?

A: PDF ファイル内の特定のページの寸法を取得するには、`GetPageRect()`の方法`Page` Aspose.PDF for .NET のオブジェクト。このメソッドは、`Rectangle`ページの寸法 (幅と高さ) を含むオブジェクト。

####  Q: とは何ですか?`GetPageRect(true)` method do in the provided C# source code?

 A:`GetPageRect(true)`提供された C# ソース コードのメソッドは、回転を適用した後のページの寸法を返します。ページが回転されている場合、メソッドは回転されたページの寸法を返しますが、元の寸法とは異なる場合があります。

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメント内のすべてのページの寸法を取得できますか?

 A: はい、PDF ドキュメント内のすべてのページの寸法を取得するには、`Pages`のコレクション`Document`オブジェクトを使用し、`GetPageRect(true)`各ページのメソッド。

#### Q: ページの寸法に基づいてページの向き (縦または横) を判断するにはどうすればよいですか?

A: ページの寸法に基づいてページの向きを判断するには、ページの幅と高さを比較します。幅が高さより大きい場合、ページは横向きになり、高さが幅より大きい場合、ページは縦向きになります。

#### Q: Aspose.PDF for .NET を使用してページの寸法を変更できますか?

 A: はい、Aspose.PDF for .NET でページの寸法を変更できます。を取得した後、`Rectangle`ページの寸法を表すオブジェクトを使用すると、要件に応じて幅と高さを調整し、変更をページに適用できます。