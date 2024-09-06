---
title: PDF ファイルでズーム係数を取得する
linktitle: PDF ファイルでズーム係数を取得する
second_title: Aspose.PDF for .NET API リファレンス
description: このステップバイステップ ガイドでは、Aspose.PDF for .NET を使用して PDF ファイルのズーム係数を取得する方法を学習します。
type: docs
weight: 210
url: /ja/net/programming-with-document/getzoomfactor/
---
Aspose.PDF for .NET は、PDF ドキュメントに対してさまざまな操作を実行するための多くの機能を提供する PDF 操作ライブラリです。これらの機能の 1 つは、PDF ファイルのズーム係数を取得する機能です。このチュートリアルでは、C# ソース コードを使用して、Aspose.PDF for .NET で PDF ファイルのズーム係数を取得する方法について説明します。


## ステップ1: 新しいDocumentオブジェクトをインスタンス化する

Aspose.PDF for .NETを使用してPDFファイルのズーム率を取得する最初のステップは、新しい`Document`オブジェクト。`Document`オブジェクトは、ファイルまたはストリームから読み込むことができる PDF ドキュメントを表します。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//新しいDocumentオブジェクトをインスタンス化する
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

上記のコードでは、`Document` PDFファイルのパスをオブジェクトのコンストラクタに渡すことで、`Document`クラス。「YOUR DOCUMENT DIRECTORY」を、PDF ファイルが配置されているディレクトリの実際のパスに置き換える必要があります。

## ステップ2: GoToActionオブジェクトを作成する

次のステップは、`GoToAction`オブジェクト。`GoToAction`オブジェクトはPDF文書内の特定の目的地に移動するアクションを表します。この例では、PDFファイルのズーム率を取得したいので、`OpenAction`の財産`Document`オブジェクトを取得する`GoToAction`物体。

```csharp
//GoToAction オブジェクトを作成する
GoToAction action = doc.OpenAction as GoToAction;
```

上記のコードでは、`GoToAction`オブジェクトをキャストして`OpenAction`の財産`Document`反対する`GoToAction`.

## ステップ3: PDFファイルのズーム率を取得する

3番目のステップは、PDFファイルのズーム率を取得することです。PDFファイルのズーム率を取得するには、`Destination`の財産`GoToAction`オブジェクトをキャストして`XYZExplicitDestination` 。`XYZExplicitDestination`クラスは、PDF ドキュメント内の移動先の座標とズーム係数を指定する移動先を表します。

```csharp
// PDFファイルのズーム率を取得する
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); //ドキュメントのズーム値。
```

上記のコードでは、`Destination`の財産`GoToAction`オブジェクトにしてキャストする`XYZExplicitDestination`その後、私たちは`Zoom`の財産`XYZExplicitDestination`PDF ファイルのズーム係数を取得するオブジェクト。

## ステップ4: ズーム係数を出力する

最後のステップは、PDFファイルのズーム率を出力することです。`System.Console.WriteLine`

```csharp
// PDFファイルのズーム率を取得する
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); //ドキュメントのズーム値。
```        

### Aspose.PDF for .NET を使用してズーム係数を取得するためのサンプル ソース コード

Aspose.PDF for .NET を使用してズーム係数を取得するための完全なサンプル ソース コードは次のとおりです。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//新しいDocumentオブジェクトをインスタンス化する
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");

//GoToAction オブジェクトを作成する
GoToAction action = doc.OpenAction as GoToAction;

// PDFファイルのズーム率を取得する
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); //ドキュメントのズーム値。
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルのズーム係数を取得する方法について説明しました。ズーム係数は PDF ドキュメントの重要な要素であり、ビューアで開いたときの初期表示サイズを決定します。ズーム係数にアクセスして使用することで、開発者はエンドユーザーの表示エクスペリエンスをカスタマイズできます。Aspose.PDF for .NET は、PDF ドキュメントからズーム係数やその他のナビゲーション関連情報を取得するためのシンプルで効果的な API を提供し、開発者が機能豊富でインタラクティブな PDF アプリケーションを構築できるようにします。

### PDF ファイルのズーム率を取得する方法に関する FAQ

#### Q: PDF ファイルのズーム係数はどれくらいですか?

A: PDF ファイルのズーム係数は、ドキュメントを表示するときに適用される拡大レベルを指します。これにより、画面上の PDF ファイルの初期表示サイズが決まります。ズーム係数 1.0 は実際のサイズ (100% ズーム) を表し、ズーム係数が 1.0 より大きい場合は拡大、1.0 より小さい場合は縮小を表します。

#### Q: アプリケーションでズーム係数情報を使用するにはどうすればよいですか?

A: ズーム係数情報を使用すると、ビューアで PDF ドキュメントを開いたときの初期表示サイズをカスタマイズできます。たとえば、特定のズーム係数を設定して、PDF を特定のサイズで表示したり、ページ全体をビューアのウィンドウに合わせることができます。

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメントのズーム係数をプログラムで変更できますか?

 A: はい、Aspose.PDF for .NETを使用してプログラム的にPDFドキュメントのズーム率を変更できます。次のような特定のアクションのズーム率を設定できます。`GoToAction`または`GoToRemoteAction`ユーザーがリンクやブックマークを操作したときにドキュメントがどのように表示されるかを制御します。

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメント内の特定の場所に移動する他の方法はありますか?

 A: はい、Aspose.PDF for .NETにはPDF文書内の特定の場所に移動するためのさまざまな機能があります。`GoToAction` 、他のアクションも使用できます`GoToURIAction`URLを開くには、`GoToEmbeddedAction`埋め込まれたファイルに移動し、`GoToNamedAction` PDF ドキュメント内の指定された宛先に移動します。