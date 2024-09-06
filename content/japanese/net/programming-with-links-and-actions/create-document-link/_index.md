---
title: ドキュメントリンクを作成
linktitle: ドキュメントリンクを作成
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用すると、他の PDF ドキュメントへのリンクを簡単に作成できます。
type: docs
weight: 30
url: /ja/net/programming-with-links-and-actions/create-document-link/
---
PDF ファイル内の別のドキュメントにリンクすると、ユーザーを他の PDF ドキュメントにリダイレクトするクリック可能なリンクを作成できます。Aspose.PDF for .NET を使用すると、次のソース コードに従って、このようなリンクを簡単に作成できます。

## ステップ1: 必要なライブラリをインポートする

始める前に、C# プロジェクトに必要なライブラリをインポートする必要があります。必要なインポート ディレクティブは次のとおりです。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## ステップ2: ドキュメントフォルダへのパスを設定する

この手順では、別のドキュメントへのリンクを追加するPDFファイルを含むフォルダーへのパスを指定する必要があります。`"YOUR DOCUMENT DIRECTORY"`次のコードでは、ドキュメント フォルダーへの実際のパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ3: PDF文書を開く

ここで、次のコードを使用して、別のドキュメントへのリンクを追加する PDF ドキュメントを開きます。

```csharp
Document document = new Document(dataDir + "CreateDocumentLink.pdf");
```

## ステップ4: 別のドキュメントへのリンクを作成する

このステップでは、`LinkAnnotation`注釈。リンクの座標と領域、および外部ドキュメントへのナビゲーション アクションを指定します。対応するコードは次のとおりです。

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
```

## ステップ5: 更新したファイルを保存する

更新したPDFファイルを保存してみましょう。`Save`方法の`document`オブジェクト。対応するコードは次のとおりです。

```csharp
dataDir = dataDir + "CreateDocumentLink_out.pdf";
document. Save(dataDir);
```

### Aspose.PDF for .NET を使用してドキュメント リンクを作成するためのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントを開く
Document document = new Document(dataDir+ "CreateDocumentLink.pdf");
//リンクを作成
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

おめでとうございます! Aspose.PDF for .NET を使用して他のドキュメントにリンクするためのステップバイステップ ガイドが完成しました。このコードを使用して PDF ファイルにクリック可能なリンクを作成し、ユーザーを他のドキュメントにリダイレクトできます。

インタラクティブ リンクの高度な機能の詳細については、公式の Aspose.PDF ドキュメントを必ず確認してください。

### ドキュメントリンクの作成に関するFAQ

#### Q: PDF ファイル内のドキュメント リンクとは何ですか?

A: PDF ファイル内のドキュメント リンクはクリック可能なリンクであり、ユーザーを他の PDF ドキュメントに誘導します。これらのリンクは、関連コンテンツを効率的に接続してシームレスな読み取りエクスペリエンスを実現することで、ナビゲーションを強化します。

#### Q: ドキュメント リンクを作成するとどのようなメリットがありますか?

A: ドキュメント リンクを作成すると、PDF ドキュメント内のさまざまなセクションまたはトピック間の接続を確立できます。この機能により、ユーザーは補足情報や関連資料に簡単にアクセスできるようになります。

#### Q: Aspose.PDF for .NET はドキュメント リンクの作成をどのようにサポートしますか?

A: Aspose.PDF for .NET は包括的な API セットを提供することで、ドキュメント リンクの作成プロセスを簡素化します。このガイドで説明するステップバイステップのチュートリアルでは、PDF ファイルにドキュメント リンクを追加する方法を説明します。

#### Q: ドキュメント リンクの外観をカスタマイズできますか?

A: もちろんです! Aspose.PDF for .NET には、色、スタイル、ホバー効果など、ドキュメント リンクの外観をカスタマイズするオプションが用意されています。ドキュメントのデザインに合わせて外観を調整できます。

#### Q: 別のドキュメント内の特定のセクションまたはページにリンクすることは可能ですか?

A: はい、別の PDF ドキュメント内の特定のページまたはセクションにユーザーを移動するためのリンクを作成できます。Aspose.PDF for .NET では、リンクされたドキュメント内のターゲットの場所を柔軟に定義できます。

#### Q: ドキュメント リンクが機能していることを確認するにはどうすればよいですか?

A: 提供されているチュートリアルとサンプル コードに従うことで、機能的なドキュメント リンクを自信を持って作成できます。生成された PDF ドキュメントを開いてリンクをクリックすると、リンクをテストできます。

#### Q: 1 つの PDF ファイル内に複数のドキュメント リンクを作成できますか?

 A: もちろんです！1つのPDF文書内に複数の文書リンクを作成するには、`LinkAnnotation`注釈。これにより、ユーザーはさまざまなセクションのさまざまな関連ドキュメントにアクセスできるようになります。

#### Q: 外部ドキュメントへのリンクには制限がありますか?

A: 外部ドキュメントにリンクする場合は、リンクされたドキュメントがアクセス可能であり、指定されたパスに配置されていることを確認してください。また、ユーザー権限とリンクされたドキュメントの互換性を考慮することも重要です。

#### Q: Web またはオンライン リポジトリに保存されているドキュメントにリンクできますか?

A: このチュートリアルではローカル ドキュメントへのリンクに重点を置いていますが、Aspose.PDF for .NET は Web URL またはオンライン リポジトリへのリンクもサポートしています。提供されているコードを調整して、Web ベースのドキュメント リンクを作成できます。