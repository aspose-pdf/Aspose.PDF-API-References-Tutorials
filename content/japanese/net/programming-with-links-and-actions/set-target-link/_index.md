---
title: PDF ファイルにターゲットリンクを設定する
linktitle: PDF ファイルにターゲットリンクを設定する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルにターゲット リンクを設定する方法を学びます。
type: docs
weight: 100
url: /ja/net/programming-with-links-and-actions/set-target-link/
---
このステップバイステップ ガイドでは、Aspose.PDF for .NET を使用して PDF ファイルにターゲット リンクを設定する方法を学びます。

## ステップ 1: 環境をセットアップする

C# プロジェクトと適切な Aspose.PDF 参照を使用して開発環境がセットアップされていることを確認してください。

## ステップ 2: PDF ファイルをロードする

次のコードを使用して、ドキュメントのディレクトリ パスを設定し、PDF ファイルをアップロードします。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// PDFファイルをロードする
Document document = new Document(dataDir + "UpdateLinks.pdf");
```

## ステップ 3: ターゲット リンクの編集

次のコードを使用して、変更するリンク アノテーションを取得します。

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
```

調整できます`[1]`インデックスを使用して、特定のページまたは注釈を選択します。

次に、ファイルを更新せずに宛先を更新します。

```csharp
goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
```

ファイルも更新したい場合は、次のようにします。

```csharp
goToR.File = new FileSpecification(dataDir + "input.pdf");
```

## ステップ 4: 更新されたリンクを含むドキュメントを保存する

次のコマンドを使用して、更新されたリンクを含むドキュメントを保存します。`Save`方法：

```csharp
dataDir = dataDir + "SetTargetLink_out.pdf";
document. Save(dataDir);
```

## ステップ 5: 結果の表示

ターゲット リンクが正常に構成されたことを示すメッセージを表示し、保存されたファイルの場所を指定します。

```csharp
Console.WriteLine("\nConfiguration of target link successful.\nFile saved at location: " + dataDir);
```

### Aspose.PDF for .NET を使用した Set Target Link のサンプル ソース コード 
```csharp
try
{
	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// PDFファイルをロードする
	Document document = new Document(dataDir + "UpdateLinks.pdf");
	LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
	GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
	//次の行は更新先、ファイルは更新しません
	goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
	//次の行の更新ファイル
	goToR.File = new FileSpecification(dataDir +  "input.pdf");
	dataDir = dataDir + "SetTargetLink_out.pdf";
	//更新されたリンクを含むドキュメントを保存します
	document.Save(dataDir);
	Console.WriteLine("\nTarget link setup successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 結論

おめでとうございます！ Aspose.PDF for .NET を使用して PDF ファイルにターゲット リンクを設定する方法がわかりました。この知識を活用して、PDF ドキュメント内のリンクをカスタマイズし、ユーザー向けのインタラクティブなエクスペリエンスを作成します。

このガイドを完了したので、これらの概念を独自のプロジェクトに適用し、Aspose.PDF for .NET が提供する機能をさらに詳しく調べることができます。

### PDF ファイル内のターゲット リンクの設定に関する FAQ

#### Q: PDF ファイル内のターゲット リンクとは何ですか?

A: PDF ファイル内のターゲット リンクは、同じ文書内の特定のリンク先または別の PDF ファイルに読者を移動するクリック可能なリンクです。

#### Q: PDF ファイルにターゲット リンクを設定する必要があるのはなぜですか?

A: ターゲット リンクを設定すると、PDF ドキュメント内でシームレスなナビゲーション エクスペリエンスを作成したり、他の PDF ファイル内の特定のセクションやページにリンクしたりできます。

#### Q: Aspose.PDF for .NET はターゲット リンクの設定にどのように役立ちますか?

A: Aspose.PDF for .NET は、リンクの作成や変更など、PDF ファイルのさまざまな側面を操作するための API を提供します。このチュートリアルでは、C# コードを使用してターゲット リンクを設定する方法を示します。

#### Q: 同じドキュメント内の特定のページに移動するようにターゲット リンクを設定できますか?

A: はい、Aspose.PDF for .NET を使用すると、同じドキュメント内の特定のページに移動するようにターゲット リンクを設定できます。

#### Q: 別の PDF ファイルの特定のページに移動するようにターゲット リンクを設定できますか?

A: はい、Aspose.PDF for .NET を使用して、別の PDF ファイル内の特定のページに移動するようにターゲット リンクを設定できます。

#### Q: ターゲットリンクの設定に制限はありますか?

A: ターゲット リンクは、同じドキュメント内、または他の PDF ファイル内の特定のページにのみ移動できます。他のドキュメント内の特定のコンテンツに直接リンクすることはできません。

#### Q: ターゲット リンクの外観をカスタマイズするにはどうすればよいですか?

A: ターゲット リンクの色やスタイルなどの外観は、Aspose.PDF for .NET が提供するプロパティを使用してカスタマイズできます。

#### Q: 同じ PDF ドキュメント内に複数のターゲット リンクを設定できますか?

A: はい、同じ PDF ドキュメント内に複数のターゲット リンクを設定できます。作成するリンクごとにこのプロセスを繰り返すだけです。

#### Q: 特定の図形やテキストを使用してターゲット リンクを設定できますか?

A: はい、Aspose.PDF for .NET が提供する適切なプロパティとメソッドを使用して、PDF ドキュメント内の特定の図形またはテキストにターゲット リンクを添付できます。

#### Q: ターゲット リンクが意図したとおりに動作しているかどうかをテストするにはどうすればよいですか?

A: 提供されたコードを使用してターゲット リンクを設定した後、変更した PDF を開いてリンクをクリックし、目的のリンク先に移動することを確認します。

#### Q: パスワードで保護された PDF にターゲット リンクを設定できますか?

A: はい、ドキュメントにアクセスして変更するための適切な資格情報を提供している限り、パスワードで保護された PDF にターゲット リンクを設定できます。