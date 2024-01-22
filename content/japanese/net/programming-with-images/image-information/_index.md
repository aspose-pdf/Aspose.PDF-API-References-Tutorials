---
title: PDFファイル内の画像情報
linktitle: PDFファイル内の画像情報
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイル内の画像情報を抽出します。
type: docs
weight: 160
url: /ja/net/programming-with-images/image-information/
---
このガイドでは、Aspose.PDF for .NET を使用して PDF ファイル内の画像に関する情報を抽出する方法を段階的に説明します。環境がすでにセットアップされていることを確認し、以下の手順に従ってください。

## ステップ 1: ドキュメント ディレクトリを定義する

必ず正しいドキュメント ディレクトリを設定してください。交換する`"YOUR DOCUMENT DIRECTORY"`コード内で、PDF ドキュメントが配置されているディレクトリへのパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ソース PDF ファイルをロードする

このステップでは、`Document` Aspose.PDF のクラス。使用`Document`コンストラクターを開き、PDF ドキュメントへのパスを渡します。

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## ステップ 3: デフォルトの解像度を設定する

このステップでは、画像のデフォルトの解像度を設定します。この例では、デフォルトの解像度は 72 に設定されています。

```csharp
int defaultResolution = 72;
```

## ステップ 4: オブジェクトとカウンターを初期化する

このステップでは、画像情報を取得するために必要なオブジェクトとカウンターを初期化します。

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## ステップ 5: 文書の最初のページで演算子を順番に選択します。

このステップでは、ドキュメントの最初のページにある演算子を順に見ていき、画像関連の演算を特定します。

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## ステップ 6: オペレーターを管理し、画像情報を抽出する

このステップでは、さまざまなタイプのオペレーターを管理し、画像に関する情報を抽出します。

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

//変換のための GSave および GRestore 操作を処理する
if (opSaveState != null)
{
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
}
else if (opRestoreState != null)
{
     graphicsState. Pop();
}
//変換のための ConcatenateMatrix 操作を処理します。
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
//画像の Do 操作を処理する
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
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ソース PDF ファイルをロードします
Document doc = new Document(dataDir+ "ImageInformation.pdf");
//画像のデフォルトの解像度を定義する
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
//画像名を保持する配列リストオブジェクトを定義します。
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
//オブジェクトをスタックに挿入します
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
//ドキュメントの最初のページにあるすべての演算子を取得します
foreach (Operator op in doc.Pages[1].Contents)
{
	//GSave/GRestore 演算子を使用して、変換を以前に設定した状態に戻します
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	//現在の変換行列を定義するときに ConcatenateMatrix オブジェクトをインスタンス化します。
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	//リソースからオブジェクトを描画する Do 演算子を作成します。 Form オブジェクトと Image オブジェクトを描画します
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//以前の状態を保存し、現在の状態をスタックの先頭にプッシュします
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		//現在の状態を破棄して以前の状態に戻す
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
		//現在の行列と状態行列を乗算します。
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		//画像描画オペレータの場合
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			//最初の PDF ページの画像を保持する XImage オブジェクトを作成する
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			//画像の寸法を取得する
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			//画像の高さと幅の情報を取得する
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			//上記の情報に基づいて解像度を計算する
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			//各画像の寸法と解像度の情報を表示します
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## 結論

おめでとうございます！ Aspose.PDF for .NET を使用して PDF ファイル内の画像情報を抽出する方法を学習しました。この情報は、アプリケーションのさまざまな画像処理タスクに使用できます。

### PDFファイルの画像情報に関するFAQ

#### Q: Aspose.PDF for .NET を使用して PDF ドキュメントから画像情報を抽出する目的は何ですか?

A: PDF ドキュメントから画像情報を抽出すると、ドキュメント内の画像の寸法、解像度、その他の属性についての洞察が得られます。この情報は、画像処理、分析、または最適化タスクに使用できます。

#### Q: Aspose.PDF for .NET は、PDF ドキュメントからの画像情報の抽出をどのように支援しますか?

A: Aspose.PDF for .NET は、画像を含む PDF ドキュメントのコンテンツにアクセスして分析するためのツールを提供します。提供されたコードは、さまざまな演算子を使用して画像情報を抽出して表示する方法を示しています。

#### Q：この手法ではどのような画像情報が抽出できるのでしょうか？

A: この方法を使用すると、PDF ドキュメント内の画像の拡大縮小された寸法、解像度、画像名などの情報を抽出して表示できます。

#### Q: コードは PDF ドキュメント内の画像関連の演算子をどのように識別して処理しますか?

A: コードは、PDF ドキュメントの指定されたページで演算子を反復処理します。画像の操作、変換、レンダリングに関連する演算子を識別して処理します。

#### Q: デフォルトの解像度の重要性は何ですか?また、コード内でどのように使用されますか?

A: デフォルトの解像度は、画像の実際の解像度を計算するための基準点として使用されます。このコードは、画像の寸法とデフォルトの解像度設定に基づいて各画像の解像度を計算します。

#### Q: 抽出された画像情報は、現実のシナリオでどのように活用できますか?

A: 抽出された画像情報は、画質評価、画像の最適化、画像サムネイルの生成、画像関連の意思決定プロセスの促進などのタスクに使用できます。

#### Q: 追加の画像関連属性を抽出するようにコードを変更できますか?

A: はい、コードをカスタマイズして、色空間、ピクセル深度、画像タイプなどの画像の追加属性を抽出できます。

#### Q: 画像情報抽出プロセスにはリソースや時間がかかりますか?

A: 画像情報抽出プロセスは効率的でパフォーマンスが最適化されており、リソース使用量と処理時間への影響を最小限に抑えます。

#### Q: 開発者は、PDF ドキュメントから画像情報を識別して抽出することでどのようなメリットを得られますか?

A: 開発者は、PDF ドキュメント内の画像の特性について洞察を得ることができ、画像の操作、処理、最適化に関して情報に基づいた意思決定を行うことができます。

#### Q: この方法は、画像を含む PDF ドキュメントのバッチ処理に使用できますか?

A: はい。このメソッドは、複数のページまたはドキュメントを反復処理し、画像情報を抽出し、画像関連のタスクを実行することにより、バッチ処理用に拡張できます。