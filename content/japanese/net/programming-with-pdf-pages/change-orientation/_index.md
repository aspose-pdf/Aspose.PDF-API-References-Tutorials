---
title: 方向を変える
linktitle: 方向を変える
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF のページの向きを変更するためのステップバイステップ ガイド。簡単に実行でき、プロジェクトに実装できます。
type: docs
weight: 10
url: /ja/net/programming-with-pdf-pages/change-orientation/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントのページの向きを変更する手順を順を追って説明します。バンドルされている C# ソース コードについて説明し、この機能を理解して独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後には、Aspose.PDF for .NET を使用して PDF ドキュメントのページの向きを変更する方法がわかります。

## 前提条件
始める前に、次のものがあることを確認してください。

- C#プログラミング言語の基礎知識
- 開発環境に Aspose.PDF for .NET がインストールされている

## ステップ1: ドキュメントディレクトリを定義する
まず、ドキュメント ディレクトリへのパスを設定する必要があります。これは、入力 PDF ファイルがある場所であり、変更した出力 PDF ファイルを保存する場所です。「YOUR DOCUMENTS DIRECTORY」を適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: PDF文書を読み込む
次に、入力ファイルからPDF文書を読み込むには、`Document` Aspose.PDF のクラス。PDF ファイルへの正しいパスを必ず指定してください。

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## ステップ3: ページの向きを変更する
次に、ドキュメントの各ページを調べて、その向きを変更します。各ページで、メディアボックスのサイズを変更します（`MediaBox`) の幅と高さを入れ替えて、メディア ボックスの座標を調整し、ページの位置を維持します。最後に、ページの回転を 90 度に設定します。

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

## ステップ4: 変更したPDF文書を保存する
最後に、変更したPDF文書を出力ファイルに保存するには、`Save()`方法の`Document`クラス。正しいパスとファイル名を必ず指定してください。

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
```

### Aspose.PDF for .NET を使用した方向変更のサンプル ソース コード 

```csharp

//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Aspose.Pdf.Rectangle r = page.MediaBox;
	double newHeight = r.Width;
	double newWidth = r.Height;
	double newLLX = r.LLX;
	//ページサイズの変更を補正するためにページを上に移動する必要があります
	//（ページの下端は0,0で、情報は通常、
	//ページの上部。それが、恋人のエッジを上に移動します。
	//古くて新しい高さ。
	double newLLY = r.LLY + (r.Height - newHeight);
	page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	//場合によっては、CropBox も設定する必要があります (元のファイルで設定されている場合)
	page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	//ページの回転角度の設定
	page.Rotate = Rotation.on90;
}
dataDir = dataDir + "ChangeOrientation_out.pdf";
//出力ファイルを保存する
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);

```

## 結論
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントのページの向きを変更する方法を学習しました。上記の手順に従うことで、この機能を自分のプロジェクトに簡単に実装できます。Aspose.PDF のドキュメントをさらに詳しく調べて、PDF ファイルの操作に役立つその他の機能を見つけてください。

### よくある質問

#### Q: PDF ドキュメントのページの向きを変更する目的は何ですか?

A: PDF ドキュメントのページの向きを変更すると、ページのコンテンツを 90 度回転できます。これは、縦向きから横向きに、またはその逆に切り替えるなど、元のコンテンツを別の向きで表示または印刷する必要がある場合に役立ちます。

#### Q: PDF ドキュメント内の特定のページの向きを変更できますか?

 A: はい、PDF文書内の特定のページの向きを変更することができます。提供されているC#ソースコードでは、`foreach`ループは、ドキュメントの各ページを調べて向きを変更するために使用されます。特定のページの向きのみを変更したい場合は、ページ番号やその他の基準に基づいてそれらのページをターゲットにするようにループを変更できます。

#### Q: ページの向きを変更すると、ページ上のコンテンツのレイアウトに影響しますか?

A: はい、ページの向きを変更すると、ページ上のコンテンツのレイアウトに影響します。コンテンツは 90 度回転し、ページの幅と高さが入れ替わります。その結果、ページ上のコンテンツの配置と配置が変わる場合があります。

#### Q: ページを 90 度以外の角度で回転できますか?

 A: 提供されているC#ソースコードでは、ページの回転は90度に設定されています。`page.Rotate = Rotate.on90;`ただし、必要に応じて回転角度を他の値に変更することもできます。たとえば、`Rotate.on180`ページを180度回転させるには`Rotate.on270`270 度回転します。

#### Q: 向きを変更した後にオーバーフローするページ コンテンツを処理するにはどうすればよいですか?

A: ページの向きを変更すると、ページのサイズが変わる場合があり、コンテンツがオーバーフローする可能性があります。これに対処するには、ページ上のコンテンツのレイアウトと書式設定を調整する必要があります。Aspose.PDF for .NET が提供する機能 (要素のサイズ変更、余白の調整、コンテンツの再編成など) を使用すると、向きの変更後にページ コンテンツが適切に収まるようにすることができます。