---
title: PDF ファイルのズーム率を取得
linktitle: PDF ファイルのズーム率を取得
second_title: Aspose.PDF for .NET API リファレンス
description: このステップバイステップのガイドでは、Aspose.PDF for .NET を使用して PDF ファイルのズーム率を取得する方法を学びます。
type: docs
weight: 210
url: /ja/net/programming-with-document/getzoomfactor/
---
Aspose.PDF for .NET は、PDF ドキュメントに対してさまざまな操作を実行するための多くの機能を提供する PDF 操作ライブラリです。これらの機能の 1 つは、PDF ファイルのズーム率を取得する機能です。このチュートリアルでは、C# ソース コードを使用して、Aspose.PDF for .NET を使用して PDF ファイルのズーム率を取得する方法を説明します。


## ステップ 1: 新しい Document オブジェクトをインスタンス化する

Aspose.PDF for .NET を使用して PDF ファイルのズーム率を取得する最初のステップは、新しいファイルをインスタンス化することです。`Document`物体。の`Document`オブジェクトは、ファイルまたはストリームからロードできる PDF ドキュメントを表します。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//新しいDocumentオブジェクトをインスタンス化する
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

上記のコードでは、`Document` PDF ファイルのパスをコンストラクターに渡してオブジェクトを作成します。`Document`クラス。 「YOUR DOCUMENT DIRECTORY」を、PDF ファイルが置かれているディレクトリの実際のパスに置き換える必要があります。

## ステップ 2: GoToAction オブジェクトを作成する

次のステップは、`GoToAction`物体。あ`GoToAction`オブジェクトは、PDF ドキュメント内の特定の宛先に移動するアクションを表します。私たちの場合、PDF ファイルのズーム率を取得したいので、`OpenAction`の財産`Document`を取得するオブジェクト`GoToAction`物体。

```csharp
//GoToActionオブジェクトを作成する
GoToAction action = doc.OpenAction as GoToAction;
```

上記のコードでは、`GoToAction`をキャストしてオブジェクトを作成します`OpenAction`の財産`Document`に反対する`GoToAction`.

## ステップ 3: PDF ファイルのズーム率を取得する

 番目のステップは、PDF ファイルのズーム率を取得することです。 PDF ファイルのズーム率を取得するには、`Destination`の財産`GoToAction`オブジェクトを作成してからそれをキャストします`XYZExplicitDestination`。の`XYZExplicitDestination`クラスは、移動先の座標とズーム率を指定する PDF ドキュメント内の目的地を表します。

```csharp
// PDFファイルのズーム率を取得します
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); //ドキュメントのズーム値。
```

上記のコードでは、`Destination`の財産`GoToAction`オブジェクトを作成してからそれをキャストします`XYZExplicitDestination`。その後、アクセスしたのは、`Zoom`の財産`XYZExplicitDestination` PDF ファイルのズーム率を取得するオブジェクト。

## ステップ 4: ズーム率を出力する

最後のステップは、PDF ファイルのズーム率を出力することです。使用できます`System.Console.WriteLine`

```csharp
// PDFファイルのズーム率を取得します
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); //ドキュメントのズーム値。
```        

### Aspose.PDF for .NET を使用したズーム係数の取得のソース コード例

Aspose.PDF for .NET を使用してズーム係数を取得するための完全なソース コード例を次に示します。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//新しいDocumentオブジェクトをインスタンス化する
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");

//GoToActionオブジェクトを作成する
GoToAction action = doc.OpenAction as GoToAction;

// PDFファイルのズーム率を取得します
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); //ドキュメントのズーム値。
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルのズーム率を取得する方法を説明しました。ズーム率は、ビューアで開いたときの初期表示サイズを決定するため、PDF ドキュメントの重要な側面です。開発者は、ズーム倍率にアクセスして利用することで、エンドユーザーの表示エクスペリエンスをカスタマイズできます。 Aspose.PDF for .NET は、PDF ドキュメントからズーム倍率やその他のナビゲーション関連情報を取得するためのシンプルで効果的な API を提供し、開発者が機能豊富でインタラクティブな PDF アプリケーションを構築できるようにします。

### PDF ファイルのズーム率を取得するための FAQ

#### Q: PDF ファイルのズーム倍率は何ですか?

A: PDF ファイルのズーム率とは、ドキュメントを表示するときに適用される倍率のレベルを指します。画面上の PDF ファイルの初期表示サイズを決定します。ズーム率 1.0 は実際のサイズ (100% ズーム) を表し、1.0 を超えるズーム率は拡大を表し、1.0 未満のズーム率は縮小を表します。

#### Q: アプリケーションでズーム倍率情報を使用するにはどうすればよいですか?

A: ズーム率情報を使用して、PDF ドキュメントをビューアで開いたときの初期表示サイズをカスタマイズできます。たとえば、特定のズーム率を設定して、PDF を特定のサイズで表示したり、ページ全体をビューアのウィンドウに合わせたりすることができます。

#### Q: Aspose.PDF for .NET を使用して、PDF ドキュメントのズーム率をプログラムで変更できますか?

 A: はい、Aspose.PDF for .NET を使用してプログラムで PDF ドキュメントのズーム率を変更できます。特定のアクションのズーム率を設定できます。`GoToAction`または`GoToRemoteAction`、ユーザーがリンクまたはブックマークを操作するときにドキュメントがどのように表示されるかを制御します。

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメント内の特定の場所に移動する他の方法はありますか?

 A: はい、Aspose.PDF for .NET は、PDF ドキュメント内の特定の場所に移動するためのさまざまな機能を提供します。使用する以外に`GoToAction`、次のような他のアクションを使用できます。`GoToURIAction` URLを開くには、`GoToEmbeddedAction`埋め込みファイルに移動し、`GoToNamedAction` PDF ドキュメント内の指定された宛先に移動します。