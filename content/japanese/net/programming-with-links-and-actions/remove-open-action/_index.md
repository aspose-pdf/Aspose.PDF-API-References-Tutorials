---
title: 開いているアクションを削除する
linktitle: 開いているアクションを削除する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF から開くアクションを削除する方法を学習します。
type: docs
weight: 80
url: /ja/net/programming-with-links-and-actions/remove-open-action/
---
このステップバイステップ ガイドでは、Aspose.PDF for .NET を使用して PDF ファイルから開くアクションを削除する方法を学習します。

## ステップ1: 環境の設定

C# プロジェクトと適切な Aspose.PDF 参照を使用して開発環境が設定されていることを確認してください。

## ステップ2: PDFファイルの読み込み

次のコードを使用して、ドキュメントのディレクトリ パスを設定し、PDF ファイルをアップロードします。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//文書を開く
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
```

## ステップ3: 開いているアクションを削除する

ドキュメントから開くアクションを削除するには、`OpenAction`プロパティを null にする:

```csharp
document. OpenAction = null;
```

## ステップ4: 更新したドキュメントを保存する

更新された文書を保存するには、`Save`方法：

```csharp
dataDir = dataDir + "RemoveOpenAction_out.pdf";
document. Save(dataDir);
```

## ステップ5: 結果を表示する

オープンアクションが正常に削除されたことを示すメッセージを表示し、保存されたファイルの場所を指定します。

```csharp
Console.WriteLine("\nOpen action deleted successfully.\nFile saved to location: " + dataDir);
```

### Aspose.PDF for .NET を使用した開いているファイルの削除アクションのサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメントを開く
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
//ドキュメントを開くアクションを削除する
document.OpenAction = null;
dataDir = dataDir + "RemoveOpenAction_out.pdf";
//更新されたドキュメントを保存する
document.Save(dataDir);
Console.WriteLine("\nOpen action removed successfully.\nFile saved at " + dataDir); 
```

## 結論

おめでとうございます! Aspose.PDF for .NET を使用して PDF から開くアクションを削除する方法がわかりました。この知識を使用して、プロジェクト内の PDF ファイルのプロパティと動作をカスタマイズします。

このガイドを完了したら、これらの概念を独自のプロジェクトに適用し、Aspose.PDF for .NET が提供する機能をさらに詳しく調べることができます。

### よくある質問 

#### Q: PDF ファイルの「オープンアクション」とは何ですか?

A: PDF ファイルの「開くアクション」は、PDF を開いたときに何が起こるかを指定する命令です。ドキュメント内の特定のページまたは場所への移動、外部アプリケーションの起動、特定のビューの表示などのアクションを含めることができます。

#### Q: PDF ファイルから開くアクションを削除する必要があるのはなぜですか?

A: 開くアクションを削除すると、セキュリティ、ユーザー エクスペリエンス、および PDF を開いたときの表示方法の制御が向上します。たとえば、自動ナビゲーションを防止したり、ドキュメントを開いたときに特定のアクションを無効にしたりすることができます。

#### Q: Aspose.PDF for .NET は、開くアクションを削除するのにどのように役立ちますか?

A: Aspose.PDF for .NET は、PDF ファイルのさまざまな側面を操作するための API を提供します。このチュートリアルでは、C# コードを使用して開くアクションを削除する方法を説明します。

#### Q: オープンアクションを削除するときに潜在的なリスクや考慮事項はありますか?

A: 開くアクションを削除すると、PDF のデフォルトの動作が変わる可能性があります。そのため、意図したユーザー エクスペリエンスに合致していることを確認してください。変更した PDF を徹底的にテストして、削除によって他の機能に影響がないことを確認してください。

#### Q: 開くアクションをカスタマイズして他のアクションを実行できますか?

A: はい、Aspose.PDF for .NET では、特定のページへの移動や JavaScript の実行など、さまざまな種類のアクションに設定して、開くアクションをカスタマイズできます。

#### Q: パスワードで保護された PDF から開いているアクションを削除できますか?
A: はい、ドキュメントにアクセスして変更するための適切な資格情報を提供している限り、パスワードで保護された PDF から開いているアクションを削除できます。

#### Q: オープンアクションの削除は元に戻せますか?

A: いいえ、開くアクションを削除して PDF を保存すると、変更された PDF から元の開くアクションを復元することはできません。

#### Q: オープンアクションが正常に削除されたことを確認するにはどうすればよいですか?

A: 提供されたコードを使用して開くアクションを削除した後、変更された PDF を開き、開いたときに特定のアクションが発生しないことを確認します。

#### Q: 複数の PDF ファイルから同時に開いているアクションを削除できますか?

A: はい、同じ方法を使用して、バッチ処理シナリオで複数の PDF ファイルから開いているアクションを削除できます。