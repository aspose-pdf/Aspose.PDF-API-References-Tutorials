---
title: ドキュメントリンクの作成
linktitle: ドキュメントリンクの作成
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、他の PDF ドキュメントへのリンクを簡単に作成できます。
type: docs
weight: 30
url: /ja/net/programming-with-links-and-actions/create-document-link/
---
PDF ファイル内の別のドキュメントにリンクすると、ユーザーを他の PDF ドキュメントにリダイレクトするクリック可能なリンクを作成できます。 Aspose.PDF for .NET を使用すると、次のソース コードに従ってそのようなリンクを簡単に作成できます。

## ステップ 1: 必要なライブラリをインポートする

始める前に、C# プロジェクトに必要なライブラリをインポートする必要があります。必要なインポートディレクティブは次のとおりです。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## ステップ 2: ドキュメントフォルダーへのパスを設定する

この手順では、別のドキュメントへのリンクを追加する PDF ファイルが含まれるフォルダーへのパスを指定する必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`次のコードでは、ドキュメント フォルダーへの実際のパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 3: PDF ドキュメントを開く

次に、次のコードを使用して、別のドキュメントへのリンクを追加する PDF ドキュメントを開きます。

```csharp
Document document = new Document(dataDir + "CreateDocumentLink.pdf");
```

## ステップ 4: 別のドキュメントへのリンクを作成する

このステップでは、`LinkAnnotation`注釈。リンクの座標と領域、および外部ドキュメントへのナビゲーション アクションを指定します。対応するコードは次のとおりです。

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
```

## ステップ 5: 更新されたファイルを保存する

次に、更新された PDF ファイルを保存しましょう。`Save`の方法`document`物体。対応するコードは次のとおりです。

```csharp
dataDir = dataDir + "CreateDocumentLink_out.pdf";
document. Save(dataDir);
```

### Aspose.PDF for .NET を使用したドキュメント リンクの作成のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開いた文書
Document document = new Document(dataDir+ "CreateDocumentLink.pdf");
//リンクの作成
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
dataDir = dataDir + "CreateDocumentLink_out.pdf";
//更新されたドキュメントを保存する
document.Save(dataDir);
Console.WriteLine("\nDocument link created successfully.\nFile saved at " + dataDir);            
```

## 結論

おめでとうございます！これで、Aspose.PDF for .NET を使用して他のドキュメントにリンクするためのステップバイステップ ガイドが完成しました。このコードを使用すると、PDF ファイル内にクリック可能なリンクを作成し、ユーザーを他のドキュメントにリダイレクトできます。

インタラクティブ リンクの高度な機能の詳細については、公式の Aspose.PDF ドキュメントを必ずご確認ください。

### ドキュメント作成リンクに関する FAQ

#### Q: PDF ファイル内のドキュメント リンクとは何ですか?

A: PDF ファイル内のドキュメント リンクは、ユーザーを他の PDF ドキュメントに誘導するクリック可能なリンクです。これらのリンクは、関連コンテンツに接続する効率的な方法を提供することでナビゲーションを強化し、シームレスな読書体験を促進します。

#### Q: ドキュメントリンクを作成するとどのようなメリットがありますか?

A: ドキュメント リンクを作成すると、PDF ドキュメント内の異なるセクションまたはトピック間の接続を確立できます。この機能により、ユーザーは補足情報や関連資料に簡単にアクセスできるようになります。

#### Q: Aspose.PDF for .NET はドキュメント リンクの作成をどのようにサポートしますか?

A: Aspose.PDF for .NET は、包括的な API セットを提供することにより、ドキュメント リンクの作成プロセスを簡素化します。このガイドで概説されているステップバイステップのチュートリアルでは、PDF ファイルにドキュメントのリンクを追加する方法を示します。

#### Q: ドキュメントのリンクの外観をカスタマイズできますか?

A: もちろんです！ Aspose.PDF for .NET は、色、スタイル、ホバー効果など、ドキュメント リンクの外観のカスタマイズ オプションを提供します。ドキュメントのデザインに合わせて外観を調整できます。

#### Q: 別のドキュメント内の特定のセクションまたはページにリンクすることはできますか?

A: はい、別の PDF ドキュメント内の特定のページまたはセクションにユーザーを移動するリンクを作成できます。 Aspose.PDF for .NET は、リンクされたドキュメント内のターゲットの場所を定義する柔軟性を提供します。

#### Q: ドキュメントのリンクが機能していることを確認するにはどうすればよいですか?

A: 提供されているチュートリアルとサンプル コードに従うことで、機能的なドキュメント リンクを自信を持って作成できます。生成された PDF ドキュメントを開いてリンクをクリックすると、リンクをテストできます。

#### Q: 1 つの PDF ファイル内に複数のドキュメント リンクを作成できますか?

 A：確かに！を使用して、単一の PDF ドキュメント内に複数のドキュメント リンクを作成できます。`LinkAnnotation`注釈。これにより、ユーザーがさまざまなセクションからさまざまな関連ドキュメントにアクセスできるようになります。

#### Q: 外部ドキュメントにリンクする場合、制限はありますか?

A: 外部ドキュメントにリンクする場合は、リンクされたドキュメントがアクセス可能であり、指定されたパスに配置されていることを確認してください。ユーザーの権限とリンクされたドキュメントの互換性を考慮することも重要です。

#### Q: Web またはオンライン リポジトリに保存されているドキュメントにリンクできますか?

A: このチュートリアルではローカル ドキュメントへのリンクに焦点を当てていますが、Aspose.PDF for .NET は Web URL またはオンライン リポジトリへのリンクもサポートしています。提供されたコードを調整して、Web ベースのドキュメント リンクを作成できます。