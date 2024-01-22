---
title: HTML からの変換後にハイパーリンクを削除する
linktitle: HTML からの変換後にハイパーリンクを削除する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して HTML を PDF に変換した後にハイパーリンクを削除するためのステップバイステップ ガイド。
type: docs
weight: 250
url: /ja/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して、HTML ファイルから生成された PDF ファイルからハイパーリンクを削除するプロセスを説明します。ハイパーリンクは、他のページまたは Web サイトにリダイレクトできるクリック可能なリンクです。以下の手順に従って、作成された PDF ファイルからハイパーリンクを削除できます。

## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。

- C# プログラミング言語の基本的な知識。
- .NET 用の Aspose.PDF ライブラリがシステムにインストールされています。
- Visual Studio などの開発環境。

## ステップ 1: HTML ファイルのロードとハイパーリンクの削除
このステップでは、HTML ファイルをロードし、結果の PDF ドキュメントからハイパーリンクを削除します。次のコードを使用します。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// HTML読み込みオプションを使用してHTMLファイルを読み込みます。
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());

//ドキュメントの最初のページの注釈を参照する
foreach(Annotation a in doc.Pages[1].Annotations)
{
     //注釈がリンクかどうかを確認する
     if (a.AnnotationType == AnnotationType.Link)
     {
         LinkAnnotation the = (LinkAnnotation)a;
        
         //アクションのタイプが GoToURIAction であるかどうかを確認する
         if (the.Action is GoToURIAction)
         {
             GoToURIAction gta = (GoToURIAction)the.Action;
             gta.URI = "";
            
             //テキスト フラグメント アブソーバーを使用して一致するテキスト フラグメントを検索する
             TextFragmentAbsorber tfa = new TextFragmentAbsorber();
             tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
             doc.Pages[a.PageIndex].Accept(tfa);
            
             //一致するテキストの断片をループし、ハイパーリンクから属性を削除します
             foreach(TextFragment tf in tfa.TextFragments)
             {
                 tf.TextState.Underline = false;
                 tf.TextState.ForegroundColor = Color.Black;
             }
         }
        
         //ページから注釈を削除する
         doc.Pages[a.PageIndex].Annotations.Delete(a);
     }
}
```

必ず交換してください`"YOUR DOCUMENTS DIRECTORY"` HTML ファイルが置かれている実際のディレクトリに置き換えます。

## ステップ 2: 結果の PDF ファイルを保存する
最後に、結果の PDF ファイルをハイパーリンクなしで保存します。次のコードを使用します。

```csharp
//結果の PDF ファイルを保存する
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

上記のコードは、結果の PDF ファイルを次のファイル名で保存します。`"RemoveHyperlinksFromText_out.pdf"`.

### Aspose.PDF for .NET を使用して Html から変換した後にハイパーリンクを削除するソース コードの例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
doc.Save(new MemoryStream());
foreach (Annotation a in doc.Pages[1].Annotations)
{
	if (a.AnnotationType == AnnotationType.Link)
	{
		LinkAnnotation la = (LinkAnnotation)a;
		if (la.Action is GoToURIAction)
		{
			GoToURIAction gta = (GoToURIAction)la.Action;
			gta.URI = "";
			TextFragmentAbsorber tfa = new TextFragmentAbsorber();
			tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
			doc.Pages[a.PageIndex].Accept(tfa);
			foreach (TextFragment tf in tfa.TextFragments)
			{
				tf.TextState.Underline = false;
				tf.TextState.ForegroundColor = Color.Black;
			}
		}
		doc.Pages[a.PageIndex].Annotations.Delete(a);
	}
}
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

## 結論
このチュートリアルでは、Aspose.PDF for .NET を使用して、HTML ファイルから生成された PDF ファイルからハイパーリンクを削除する手順を段階的に説明しました。上記の手順に従うことで、作成された PDF ファイルからハイパーリンクを正常に削除できます。

### よくある質問

#### Q: Aspose.PDF for .NET とは何ですか?

A: Aspose.PDF for .NET は、開発者が C# アプリケーションで PDF ドキュメントを操作できるようにする強力なライブラリです。 HTML ファイルを PDF に変換したり、PDF コンテンツを操作したりする機能など、幅広い機能を提供します。

#### Q: PDF ファイルからハイパーリンクを削除する必要があるのはなぜですか?

A: PDF ファイルからハイパーリンクを削除する理由はさまざまです。たとえば、印刷やアーカイブの目的で外部リンクを削除したり、ハイパーリンク経由で PDF コンテンツに移動できないようにしたりすることができます。

#### Q: Aspose.PDF for .NET を使用して HTML ファイルをロードし、ハイパーリンクを削除するにはどうすればよいですか?

 A: HTML ファイルをロードしてハイパーリンクを削除するには、.NET の Aspose.PDF を使用できます。`HtmlLoadOptions`クラス。 PDF ページの注釈を繰り返し処理して、リンク注釈を検索し、その属性を変更します。

#### Q: 生成される PDF の出力ファイル名をカスタマイズできますか?

A: はい、PDF ドキュメントを保存するコードを変更することで、結果の PDF ファイルの出力ファイル名をカスタマイズできます。必要なファイル名を変更するだけです。`doc.Save()`方法。

#### Q: 特定の基準に基づいてハイパーリンクを選択的に削除することは可能ですか?

A: はい、特定の基準に基づいてハイパーリンクを選択的に削除できます。たとえば、外部リンクまたは特定の URL を指すリンクのみを削除することを選択できます。