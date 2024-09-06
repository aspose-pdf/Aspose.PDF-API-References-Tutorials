---
title: PDFファイルの画像情報
linktitle: PDFファイルの画像情報
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内の画像情報を抽出します。
type: docs
weight: 160
url: /ja/net/programming-with-images/image-information/
---
このガイドでは、Aspose.PDF for .NET を使用して PDF ファイル内の画像に関する情報を抽出する方法を段階的に説明します。環境がすでに設定されていることを確認し、以下の手順に従ってください。

## ステップ1: ドキュメントディレクトリを定義する

正しいドキュメントディレクトリを設定してください。`"YOUR DOCUMENT DIRECTORY"`コード内に、PDF ドキュメントが保存されているディレクトリへのパスを含めます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: ソースPDFファイルを読み込む

このステップでは、ソースPDFファイルを読み込みます。`Document` Aspose.PDFのクラス。`Document`コンストラクターを呼び出して、PDF ドキュメントへのパスを渡します。

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## ステップ3: デフォルトの解像度を設定する

この手順では、画像のデフォルトの解像度を設定します。例では、デフォルトの解像度は 72 に設定されています。

```csharp
int defaultResolution = 72;
```

## ステップ4: オブジェクトとカウンターを初期化する

このステップでは、画像情報を取得するために必要なオブジェクトとカウンターを初期化します。

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## ステップ5: ドキュメントの最初のページで演算子を循環する

このステップでは、ドキュメントの最初のページにある演算子を順に見ていき、画像関連の操作を識別します。

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## ステップ6: オペレータを管理し、画像情報を抽出する

このステップでは、さまざまな種類の演算子を管理し、画像に関する情報を抽出します。

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

//変換のためのGSaveおよびGRestore操作を処理する
if (opSaveState != null)
{
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
}
else if (opRestoreState != null)
{
     graphicsState. Pop();
}
//変換のためのConcatenateMatrix操作を処理する
else if (opCtm != null)
{
     //変換行列を適用する
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);


     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     keep on going;
}
//画像のDo操作を処理する
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         //画像を取得する
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         //画像の寸法を取得する
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         //上記の情報に基づいて解像度を計算します
         double resHorizontal = originalWidth * defaultResolution / scaledWidth;
         double resVertical = originalHeight * defaultResolution / scaledHeight;
         //画像情報を表示する
         Console.Out.WriteLine(
                 string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
     }
}
```

### Aspose.PDF for .NET を使用した画像情報のサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ソースPDFファイルを読み込む
Document doc = new Document(dataDir+ "ImageInformation.pdf");
//画像のデフォルトの解像度を定義する
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
//画像名を保持する配列リストオブジェクトを定義する
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
//スタックするオブジェクトを挿入する
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
//ドキュメントの最初のページにあるすべての演算子を取得します
foreach (Operator op in doc.Pages[1].Contents)
{
	//GSave/GRestore演算子を使用して、変換を以前の設定に戻します。
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	//現在の変換行列を定義する ConcatenateMatrix オブジェクトをインスタンス化します。
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	//リソースからオブジェクトを描画するDo演算子を作成します。フォームオブジェクトとイメージオブジェクトを描画します。
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//以前の状態を保存し、現在の状態をスタックの一番上にプッシュします
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		//現在の状態を破棄し、以前の状態を復元します
		graphicsState.Pop();
	}
	else if (opCtm != null)
	{
		System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
		   (float)opCtm.Matrix.A,
		   (float)opCtm.Matrix.B,
		   (float)opCtm.Matrix.C,
		   (float)opCtm.Matrix.D,
		   (float)opCtm.Matrix.E,
		   (float)opCtm.Matrix.F);
		//現在の行列と状態行列を掛け合わせる
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		//これが画像描画演算子の場合
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			//最初の PDF ページの画像を保持する XImage オブジェクトを作成する
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			//画像のサイズを取得する
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			//画像の高さと幅の情報を取得する
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			//上記の情報に基づいて解像度を計算する
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			//各画像のサイズと解像度情報を表示します
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## 結論

おめでとうございます! Aspose.PDF for .NET を使用して PDF ファイル内の画像情報を抽出する方法を学習しました。この情報は、アプリケーション内のさまざまな画像処理タスクに使用できます。

### PDF ファイル内の画像情報に関する FAQ

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメントから画像情報を抽出する目的は何ですか?

A: PDF ドキュメントから画像情報を抽出すると、ドキュメント内の画像のサイズ、解像度、その他の属性に関する情報が得られます。この情報は、画像処理、分析、または最適化タスクに使用できます。

#### Q: Aspose.PDF for .NET はどのようにして PDF ドキュメントから画像情報を抽出するのですか?

A: Aspose.PDF for .NET には、画像を含む PDF ドキュメントのコンテンツにアクセスして分析するためのツールが用意されています。提供されているコードは、さまざまな演算子を使用して画像情報を抽出して表示する方法を示しています。

#### Q: この方法ではどのような画像情報を抽出できますか?

A: この方法を使用すると、PDF ドキュメント内の画像の拡大縮小された寸法、解像度、画像名などの情報を抽出して表示できます。

#### Q: コードは PDF ドキュメント内の画像関連の演算子をどのように識別して処理しますか?

A: コードは、PDF ドキュメントの指定されたページの演算子を反復処理します。画像操作、変換、レンダリングに関連する演算子を識別して処理します。

#### Q: デフォルトの解像度の意味は何ですか? また、コード内でどのように使用されますか?

A: デフォルトの解像度は、画像の実際の解像度を計算するための基準として使用されます。コードは、各画像の寸法とデフォルトの解像度設定に基づいて、各画像の解像度を計算します。

#### Q: 抽出された画像情報は実際のシナリオでどのように活用できますか?

A: 抽出された画像情報は、画像品質の評価、画像の最適化、画像のサムネイルの生成、画像関連の意思決定プロセスの促進などのタスクに使用できます。

#### Q: コードを変更して、追加の画像関連属性を抽出することはできますか?

A: はい、コードをカスタマイズして、色空間、ピクセル深度、画像タイプなどの画像の追加属性を抽出することができます。

#### Q: 画像情報抽出プロセスは、多くのリソースや時間がかかりますか?

A: 画像情報抽出プロセスは効率的でパフォーマンスが最適化されており、リソース使用量と処理時間への影響を最小限に抑えます。

#### Q: PDF ドキュメントから画像情報を識別して抽出することで、開発者はどのようなメリットを得ることができますか?

A: 開発者は PDF ドキュメント内の画像の特性に関する洞察を得ることができ、画像の操作、処理、最適化に関して情報に基づいた決定を下すことができます。

#### Q: この方法は、画像を含む PDF ドキュメントのバッチ処理に使用できますか?

A: はい、この方法は、複数のページまたはドキュメントを反復処理し、画像情報を抽出し、画像関連のタスクを実行することで、バッチ処理用に拡張できます。