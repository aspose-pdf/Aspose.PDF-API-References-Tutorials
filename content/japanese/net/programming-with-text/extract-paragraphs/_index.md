---
title: PDFファイル内の段落を抽出する
linktitle: PDFファイル内の段落を抽出する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内の段落を抽出する方法を学習します。
type: docs
weight: 160
url: /ja/net/programming-with-text/extract-paragraphs/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイル内の段落を抽出するプロセスについて説明します。提供されている C# ソース コードは、必要な手順を示しています。

## 要件
始める前に、次のものがあることを確認してください。

- マシンにインストールされている Visual Studio またはその他の C# コンパイラ。
- Aspose.PDF for .NET ライブラリ。公式 Aspose Web サイトからダウンロードするか、NuGet などのパッケージ マネージャーを使用してインストールできます。

## ステップ1: プロジェクトを設定する
1. 好みの開発環境で新しい C# プロジェクトを作成します。
2. Aspose.PDF for .NET ライブラリへの参照を追加します。

## ステップ2: 必要な名前空間をインポートする
段落を抽出するコード ファイルで、ファイルの先頭に次の using ディレクティブを追加します。

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## ステップ3: ドキュメントディレクトリを設定する
コード内で、次の行を見つけます。`string dataDir = "YOUR DOCUMENT DIRECTORY";`置き換えて`"YOUR DOCUMENT DIRECTORY"`ドキュメントが保存されているディレクトリへのパスを指定します。

## ステップ4: PDF文書を開く
既存のPDF文書を開くには、`Document`コンストラクターを呼び出して、入力 PDF ファイルへのパスを渡します。

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## ステップ5: 段落を抽出する
インスタンス化する`ParagraphAbsorber`クラスとその`Visit`文書から段落を抽出する方法。

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## ステップ6: 段落を繰り返す
抽出された段落をループしてテキストの内容にアクセスします。ネストされたループを使用して、各段落内のセクションと行を移動します。

```csharp
foreach(PageMarkup markup in absorber.PageMarkups)
{
     int i = 1;
     foreach(MarkupSection section in markup.Sections)
     {
         int j = 1;
         foreach(MarkupParagraph paragraph in section.Paragraphs)
         {
             StringBuilder paragraphText = new StringBuilder();
             foreach(List<TextFragment> line in paragraph.Lines)
             {
                 foreach(TextFragment fragment in line)
                 {
                     paragraphText.Append(fragment.Text);
                 }
                 paragraphText. Append("\r\n");
             }
             paragraphText. Append("\r\n");
             Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
             Console.WriteLine(paragraphText.ToString());
             j++;
         }
         i++;
     }
}
```

### Aspose.PDF for .NET を使用して段落を抽出するためのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//既存のPDFファイルを開く
Document doc = new Document(dataDir + "input.pdf");
//ParagraphAbsorber をインスタンス化する
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
foreach (PageMarkup markup in absorber.PageMarkups)
{
	int i = 1;
	foreach (MarkupSection section in markup.Sections)
	{
		int j = 1;
		foreach (MarkupParagraph paragraph in section.Paragraphs)
		{
			StringBuilder paragraphText = new StringBuilder();
			foreach (List<TextFragment> line in paragraph.Lines)
			{
				foreach (TextFragment fragment in line)
				{
					paragraphText.Append(fragment.Text);
				}
				paragraphText.Append("\r\n");
			}
			paragraphText.Append("\r\n");
			Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
			Console.WriteLine(paragraphText.ToString());
			j++;
		}
		i++;
	}
}
```

## 結論
Aspose.PDF for .NET を使用して PDF ドキュメントから段落を正常に抽出しました。抽出された段落はコンソール ウィンドウに表示されています。

### よくある質問

#### Q: このチュートリアルの目的は何ですか?

A: このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルから段落を抽出するプロセスについて説明します。付属の C# ソース コードには、このタスクを実行するための実用的な手順が示されています。

#### Q: どの名前空間をインポートすればよいですか?

A: 段落を抽出するコード ファイルでは、ファイルの先頭に次の using ディレクティブを含めます。

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### Q: ドキュメントディレクトリを指定するにはどうすればよいですか?

 A: 線を見つける`string dataDir = "YOUR DOCUMENT DIRECTORY";`コード内の`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

#### Q: 既存の PDF ドキュメントを開くにはどうすればよいですか?

 A: ステップ4では、既存のPDF文書を`Document`コンストラクターを呼び出して、入力 PDF ファイルへのパスを指定します。

#### Q: 文書から段落を抽出するにはどうすればよいですか?

 A: ステップ5では、`ParagraphAbsorber`クラスとその使用`Visit`PDF ドキュメントから段落を抽出する方法。

#### Q: 抽出された段落を反復処理するにはどうすればよいですか?

A: ステップ 6 では、抽出された段落をループする手順を説明します。ネストされたループは、各段落内のセクションと行を走査するために使用され、最終的にテキスト コンテンツにアクセスして表示します。

#### Q: このチュートリアルから得られる重要なポイントは何ですか?

A: このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントから段落を抽出する方法を学習しました。抽出された段落はコンソール ウィンドウに表示され、ドキュメントのコンテンツ構造に関する貴重な情報を提供します。