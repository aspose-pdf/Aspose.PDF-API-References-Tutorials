---
title: 向きを変更する
linktitle: 向きを変更する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF のページの向きを変更するためのステップバイステップ ガイド。フォローしてプロジェクトに実装するのが簡単です。
type: docs
weight: 10
url: /ja/net/programming-with-pdf-pages/change-orientation/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントのページの向きを変更するプロセスを段階的に説明します。バンドルされている C# ソース コードについて説明し、この機能を理解し、独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後には、Aspose.PDF for .NET を使用して PDF ドキュメントのページの向きを変更する方法がわかります。

## 前提条件
始める前に、以下のものがあることを確認してください。

- C# プログラミング言語の基本的な知識
- 開発環境にインストールされた Aspose.PDF for .NET

## ステップ 1: ドキュメント ディレクトリを定義する
まず、ドキュメント ディレクトリへのパスを設定する必要があります。これは、入力 PDF ファイルが存在する場所であり、変更した出力 PDF ファイルを保存する場所です。 「YOUR DOCUMENTS DIRECTORY」を適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: PDF ドキュメントをロードする
次に、次のコマンドを使用して、入力ファイルから PDF ドキュメントをロードできます。`Document` Aspose.PDF のクラス。 PDF ファイルへの正しいパスを指定してください。

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## ステップ 3: ページの向きを変更する
次に、ドキュメントの各ページを調べて、方向を変更します。ページごとに、メディア ボックスのサイズを変更します (`MediaBox`) 幅と高さを入れ替えてから、ページの位置を維持するためにメディア ボックスの座標を調整します。最後に、ページの回転を 90 度に設定します。

```csharp
foreach(Page page in doc.Pages)
{
Aspose.Pdf.Rectangle r = page.MediaBox;
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page. Rotate = Rotate. on90;
}
```

## ステップ 4: 変更した PDF ドキュメントを保存する
最後に、次のコマンドを使用して、変更した PDF ドキュメントを出力ファイルに保存できます。`Save()`の方法`Document`クラス。必ず正しいパスとファイル名を指定してください。

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
```

### Aspose.PDF for .NET を使用した方向変更のサンプル ソース コード 

```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Aspose.Pdf.Rectangle r = page.MediaBox;
	double newHeight = r.Width;
	double newWidth = r.Height;
	double newLLX = r.LLX;
	//ページサイズの変化を補うためにページを上部に移動する必要があります
	//(ページの下端は 0,0 で、情報は通常、ページの下端から配置されます)
	//ページの先頭。それが、私たちが恋人との違いを重視して恋人のエッジを上位に置く理由です。
	//古くて新しい高さ。
	double newLLY = r.LLY + (r.Height - newHeight);
	page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	//場合によっては、CropBox を設定する必要がある場合もあります (元のファイルに設定されている場合)
	page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	//ページの回転角度を設定する
	page.Rotate = Rotation.on90;
}
dataDir = dataDir + "ChangeOrientation_out.pdf";
//出力ファイルを保存する
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);

```

## 結論
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントのページの向きを変更する方法を学びました。上記の手順に従うことで、この機能を独自のプロジェクトに簡単に実装できます。 Aspose.PDF ドキュメントをさらに詳しく調べて、PDF ファイルを操作するためのその他の便利な機能を見つけてください。

### よくある質問

#### Q: PDF ドキュメントでページの向きを変更する目的は何ですか?

A: PDF ドキュメントでページの向きを変更すると、ページのコンテンツを 90 度回転できます。これは、縦モードから横モードへの切り替え、またはその逆の切り替えなど、元のコンテンツを別の方向で表示または印刷する必要があるシナリオで役立ちます。

#### Q: PDF ドキュメント内の特定のページの向きを変更できますか?

 A: はい、PDF ドキュメント内の特定のページの向きを変更できます。提供された C# ソース コードでは、`foreach`ループは、ドキュメントの各ページを調べて方向を変更するために使用されます。特定のページの方向のみを変更したい場合は、ページ番号またはその他の基準に基づいてそれらのページをターゲットにするようにループを変更できます。

#### Q: ページの向きを変更すると、ページ上のコンテンツのレイアウトに影響しますか?

A: はい、ページの向きを変更すると、ページ上のコンテンツのレイアウトに影響します。コンテンツが 90 度回転され、ページの幅と高さが入れ替わります。その結果、ページ上のコンテンツの配置と配置が変更される場合があります。

#### Q: ページを 90 度以外の角度で回転できますか?

 A: 提供されている C# ソース コードでは、ページの回転は次を使用して 90 度に設定されています。`page.Rotate = Rotate.on90;` 。ただし、必要に応じて回転角度を他の値に変更できます。たとえば、次のように使用できます`Rotate.on180`ページを 180 度回転するか、`Rotate.on270` 270度回転させます。

#### Q: 方向を変更した後にページ コンテンツがオーバーフローする場合は、どうすればよいですか?

A: ページの向きを変更すると、ページの寸法が変更され、コンテンツがオーバーフローする可能性があります。これに対処するには、ページ上のコンテンツのレイアウトと書式設定を調整する必要がある場合があります。 Aspose.PDF for .NET が提供する要素のサイズ変更、余白の調整、コンテンツの再編成などの機能を使用して、方向の変更後にページ コンテンツが適切に収まるようにすることができます。