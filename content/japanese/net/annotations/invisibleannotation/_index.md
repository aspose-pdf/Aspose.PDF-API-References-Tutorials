---
title: PDF ファイル内の非表示の注釈
linktitle: PDF ファイル内の非表示の注釈
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET で C# ソース コードを使用して PDF ファイルに非表示の注釈を付ける方法を学びます。ステップバイステップのガイド。
type: docs
weight: 100
url: /ja/net/annotations/invisibleannotation/
---
PDF ファイルの注釈は、実際の内容を変更せずに文書に追加情報やメモを追加できる強力な機能です。テキストを強調表示したり、文書の特定の領域に注意を引いたり、コメントやフィードバックを追加したりするために使用できます。

PDF ドキュメントで使用できる注釈には、次のようなさまざまな種類があります。

- テキスト注釈
- リンクの注釈
- スタンプの注釈
- 音声注釈
- 添付ファイルの注釈
- などなど

## ステップ 1: Aspose.PDF for .NET を使用して PDF ドキュメントに非表示の注釈を作成する

Aspose.PDF for .NET を使用して PDF ドキュメントに非表示の注釈を作成するには、まず、`FreeTextAnnotation`オブジェクトを選択し、注釈の位置とサイズを指定します。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開いた文書
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
```

上記のコードでは、`FreeTextAnnotation`オブジェクトを選択し、PDF ドキュメントの 2 ページ目にある注釈の場所を指定します。注釈に表示されるテキストのフォントの種類、サイズ、色も指定します。

## ステップ 2: 非表示の注釈に特性を追加する

次に、境界線の色、背景色、不透明度などのいくつかの特性を注釈に追加できます。

```csharp
annotation.Characteristics.Border = System.Drawing.Color.Red;
```

上記のコードでは、注釈の境界線の色を赤に設定しています。

## ステップ 3: 注釈フラグを設定する

注釈を作成し、その特性を設定した後、注釈フラグを指定できます。このチュートリアルでは、注釈を印刷可能であるが表示できないようにします。

```csharp
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);
```

## ステップ 4: 変更した PDF ドキュメントを保存する

最後に、変更した PDF ドキュメントを新しい非表示の注釈とともに保存できます。

```csharp
dataDir = dataDir + "InvisibleAnnotation_out.pdf";
doc.Save(dataDir);
```

## Aspose.PDF for .NET を使用して非表示の注釈を付ける方法のソース コード例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開いた文書
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
annotation.Contents = "ABCDEFG";
annotation.Characteristics.Border = System.Drawing.Color.Red;
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);

dataDir = dataDir + "InvisibleAnnotation_out.pdf";
//出力ファイルを保存する
doc.Save(dataDir);
//ExEnd:InvisibleAnnotation
Console.WriteLine("\nAnnotation nvisible successfully.\nFile saved at " + dataDir);
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントに非表示の注釈を作成する方法を学びました。非表示の注釈は、読者に表示せずに文書に追加情報やメモを追加したい場合に便利な機能です。ステップバイステップのガイドに従い、提供されている C# ソース コードを使用することで、開発者は PDF ドキュメント内に非表示の注釈を簡単に作成およびカスタマイズできます。 Aspose.PDF for .NET は、注釈を操作するための包括的なツール セットを提供し、PDF ファイルの対話性と使いやすさを向上させることができます。

### よくある質問

#### Q: PDF ドキュメント内の非表示の注釈とは何ですか?

A: PDF ドキュメント内の非表示の注釈とは、ページ上には表示されませんが、追加の情報やメモが含まれている注釈です。コメントやフィードバックを、読者に表示せずに追加できます。

#### Q: 非表示の注釈にはどのようなタイプの特性を追加できますか?

A: 非表示の注釈には、表示されるテキストの境界線の色、背景色、不透明度、フォントの種類、サイズ、色など、さまざまな特性を追加できます。

#### Q: 非表示の注釈に異なる注釈フラグを設定できますか?

A: はい、要件に応じて、非表示の注釈にさまざまな注釈フラグを設定できます。たとえば、注釈を印刷可能だが表示できないようにすることができます。

#### Q: PDF ドキュメントの特定のページに非表示の注釈を追加するにはどうすればよいですか?

 A: PDF ドキュメントの特定のページに非表示の注釈を追加するには、`FreeTextAnnotation`オブジェクトを選択し、そのページ上の注釈の位置とサイズを指定します。

#### Q: PDF ファイル内の既存の非表示の注釈の特性を変更できますか?

A: はい、Aspose.PDF for .NET を使用して、PDF ファイル内の既存の非表示の注釈の特性を変更できます。注釈のフォントの種類、サイズ、色、境界線の色、背景色、不透明度、およびその他のプロパティを変更できます。