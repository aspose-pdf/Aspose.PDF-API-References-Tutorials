---
title: PDF ファイル内の段落を抽出する
linktitle: PDF ファイル内の段落を抽出する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内の段落を抽出する方法を学びます。
type: docs
weight: 160
url: /ja/net/programming-with-text/extract-paragraphs/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイル内の段落を抽出するプロセスについて説明します。提供されている C# ソース コードは、必要な手順を示しています。

## 要件
始める前に、以下のものがあることを確認してください。

- マシンにインストールされている Visual Studio またはその他の C# コンパイラー。
- .NET ライブラリ用の Aspose.PDF。 Aspose の公式 Web サイトからダウンロードするか、NuGet などのパッケージ マネージャーを使用してインストールできます。

## ステップ 1: プロジェクトをセットアップする
1. 好みの開発環境で新しい C# プロジェクトを作成します。
2. Aspose.PDF for .NET ライブラリへの参照を追加します。

## ステップ 2: 必要な名前空間をインポートする
段落を抽出するコード ファイルで、ファイルの先頭に次の using ディレクティブを追加します。

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## ステップ 3: ドキュメント ディレクトリを設定する
コード内で、次の行を見つけます。`string dataDir = "YOUR DOCUMENT DIRECTORY";`そして交換してください`"YOUR DOCUMENT DIRECTORY"`ドキュメントが保存されているディレクトリへのパスを置き換えます。

## ステップ 4: PDF ドキュメントを開く
既存の PDF ドキュメントを開くには、`Document`コンストラクターを呼び出して、入力 PDF ファイルへのパスを渡します。

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## ステップ 5: 段落を抽出する
インスタンス化します`ParagraphAbsorber`クラスを作成し、そのクラスを使用します`Visit`文書から段落を抽出するメソッド。

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## ステップ 6: 段落を反復処理する
抽出された段落をループしてテキストの内容にアクセスします。ネストされたループを使用して、各段落内のセクションと行をたどります。

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

### Aspose.PDF for .NET を使用した段落抽出のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//既存の PDF ファイルを開く
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
Aspose.PDF for .NET を使用して PDF ドキュメントから段落を正常に抽出しました。抽出された段落がコンソール ウィンドウに表示されます。

### よくある質問

#### Q: このチュートリアルの目的は何ですか?

A: このチュートリアルは、Aspose.PDF for .NET を使用して PDF ファイルから段落を抽出するプロセスをガイドすることを目的としています。付属の C# ソース コードには、このタスクを達成するための実践的な手順が記載されています。

#### Q: どの名前空間をインポートする必要がありますか?

A: 段落を抽出するコード ファイルでは、ファイルの先頭に次の using ディレクティブを含めます。

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### Q: ドキュメント ディレクトリを指定するにはどうすればよいですか?

 A: 行を見つけてください`string dataDir = "YOUR DOCUMENT DIRECTORY";`コードに追加して置き換えます`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを置き換えます。

#### Q: 既存の PDF ドキュメントを開くにはどうすればよいですか?

 A: ステップ 4 では、`Document`コンストラクターを作成し、入力 PDF ファイルへのパスを提供します。

#### Q: 文書から段落を抽出するにはどうすればよいですか?

 A: ステップ 5 では、`ParagraphAbsorber`クラスとその使用`Visit`PDF ドキュメントから段落を抽出するメソッド。

#### Q: 抽出した段落を繰り返すにはどうすればよいですか?

A: ステップ 6 では、抽出された段落をループする手順を説明します。ネストされたループは、各段落内のセクションや行を横断するために使用され、最終的にはテキストの内容にアクセスして表示します。

#### Q: このチュートリアルの重要なポイントは何ですか?

A: このチュートリアルに従うことで、Aspose.PDF for .NET を使用して PDF ドキュメントから段落を抽出する方法を学習しました。抽出された段落がコンソール ウィンドウに表示され、ドキュメントのコンテンツ構造についての貴重な洞察が得られます。