---
title: PDFファイルの枠線を抽出
linktitle: PDFファイルの枠線を抽出
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ファイルの境界線を抽出する方法を学びます。
type: docs
weight: 80
url: /ja/net/programming-with-tables/extract-border/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ファイルの枠線を抽出する方法を学習します。 C#のソースコードをステップバイステップで解説していきます。このチュートリアルの最後には、PDF ドキュメントから枠線を抽出し、画像として保存する方法がわかります。はじめましょう！

## ステップ 1: 環境をセットアップする
まず、Aspose.PDF for .NET を使用して C# 開発環境をセットアップしていることを確認します。参照をライブラリに追加し、必要な名前空間をインポートします。

## ステップ 2: PDF ドキュメントをロードする
このステップでは、指定されたファイルから PDF ドキュメントを読み込みます。

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

必ず「YOUR DOCUMENT DIRECTORY」を PDF ファイルが存在する実際のディレクトリに置き換えてください。

## ステップ 3: エッジ抽出
ドキュメントに含まれる操作を反復して、PDF ドキュメントから境界線を抽出します。

```csharp
Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
     //すべてのコンテンツ操作を処理する
     foreach(Operator op in doc.Pages[1].Contents)
     {
         //操作の種類を確認する
         // ...
         //各操作を処理するコードを追加する
     }
}
```

私たちは`graphicsState`グラフィックス状態を保存するためのスタック、抽出された境界線をキャプチャするためのビットマップ イメージ、`GraphicsPath`オブジェクトを使用して描画パスを保存し、その他の変数で状態と色を追跡します。

## ステップ 4: トランザクション処理
このステップでは、ドキュメントの各操作を処理して境界線を抽出します。

```csharp
//操作の種類を確認する
if (opSaveState != null)
{
     //以前の状態を保存し、現在の状態をスタックの先頭にプッシュします
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opRestoreState != null)
{
     //現在の状態を削除し、以前の状態を復元します
     graphicsState. Pop();
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opCtm != null)
{
     //現在の変換行列を取得します。
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
         (float)opCtm.Matrix.A,
         (float)opCtm.Matrix.B,
         (float)opCtm.Matrix.C,
         (float)opCtm.Matrix.D,
         (float)opCtm.Matrix.E,
         (float)opCtm.Matrix.F);

     //現在の行列と状態行列を乗算します。
     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opMoveTo != null)
{
     //最後の描画点を更新します
     lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
     //線の描画を加工する
     // ...
     //線の描画を処理するコードを追加する
}
// ...
//他の操作のために else if ブロックを追加する
```

条件を使用して操作のタイプを確認し、各操作に適切なコードを実行します。

## ステップ 5: バックアップイメージ
最後に、抽出された境界線を含むビットマップ イメージを指定したファイルに保存します。

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

出力イメージを保存するには、必ず正しいディレクトリとファイル名を指定してください。

### Aspose.PDF for .NET を使用した境界線の抽出のソース コード例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "input.pdf");

Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
//デフォルトの ctm マトリックス値は 1,0,0,1,0,0 です。
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
//System.Drawing 座標系は左上ベースですが、PDF 座標系は左下ベースなので、反転行列を適用する必要があります。
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
	gr.SmoothingMode = SmoothingMode.HighQuality;
	graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));

	//すべてのコンテンツコマンドを処理します
	foreach (Operator op in doc.Pages[1].Contents)
	{
		Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
		Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
		Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
		Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
		Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
		Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;
		Aspose.Pdf.Operators.EndPath opEndPath = op as Aspose.Pdf.Operators.EndPath;
		Aspose.Pdf.Operators.Stroke opStroke = op as Aspose.Pdf.Operators.Stroke;
		Aspose.Pdf.Operators.Fill opFill = op as Aspose.Pdf.Operators.Fill;
		Aspose.Pdf.Operators.EOFill opEOFill = op as Aspose.Pdf.Operators.EOFill;
		Aspose.Pdf.Operators.SetRGBColor opRGBFillColor = op as Aspose.Pdf.Operators.SetRGBColor;
		Aspose.Pdf.Operators.SetRGBColorStroke opRGBStrokeColor = op as Aspose.Pdf.Operators.SetRGBColorStroke;

		if (opSaveState != null)
		{
			//以前の状態を保存し、現在の状態をスタックの先頭にプッシュします
			graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opRestoreState != null)
		{
			//現在の状態を破棄して以前の状態に戻す
			graphicsState.Pop();
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
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
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opMoveTo != null)
		{
			lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
		}
		else if (opLineTo != null)
		{
			System.Drawing.PointF linePoint = new System.Drawing.PointF((float)opLineTo.X, (float)opLineTo.Y);
			graphicsPath.AddLine(lastPoint, linePoint);

			lastPoint = linePoint;
		}
		else if (opRe != null)
		{
			System.Drawing.RectangleF re = new System.Drawing.RectangleF((float)opRe.X, (float)opRe.Y, (float)opRe.Width, (float)opRe.Height);
			graphicsPath.AddRectangle(re);
		}
		else if (opEndPath != null)
		{
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opRGBFillColor != null)
		{
			fillColor = opRGBFillColor.getColor();
		}
		else if (opRGBStrokeColor != null)
		{
			strokeColor = opRGBStrokeColor.getColor();
		}
		else if (opStroke != null)
		{
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opFill != null)
		{
			graphicsPath.FillMode = FillMode.Winding;
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.FillPath(new System.Drawing.SolidBrush(fillColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opEOFill != null)
		{
			graphicsPath.FillMode = FillMode.Alternate;
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.FillPath(new System.Drawing.SolidBrush(fillColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
	}
}
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);

Console.WriteLine("\nBorder extracted successfully as image.\nFile saved at " + dataDir);
```

## 結論
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントから枠線を抽出する方法を学びました。このステップバイステップのガイドを使用して、他の PDF ドキュメントから枠線を抽出できます。

### PDFファイルの枠線抽出に関するFAQ

#### Q: PDF ファイルから枠線を抽出する目的は何ですか?

A: PDF ファイルから枠線を抽出すると、さまざまな目的に役立ちます。これにより、表、図、グラフィック要素などのドキュメントの構造要素を分離して分析できます。抽出された境界線を使用して、PDF ドキュメント内のコンテンツのレイアウト、寸法、位置を識別できます。

#### Q: PDF ドキュメント内の特定のページまたは領域から境界線を抽出できますか?

A: はい、提供されている C# ソース コードを変更して、PDF ドキュメント内の特定のページまたは領域から境界線を抽出できます。を操作することで、`doc.Pages`コレクションを作成し、カスタム基準を指定すると、特定のページまたは関心のある領域から境界線を抽出することを選択できます。

#### Q: 出力画像の形式と品質をカスタマイズするにはどうすればよいですか?

 A: 提供されている C# コードでは、抽出された境界線が PNG 画像として保存されます。出力画像形式を変更したい場合は、`ImageFormat.Png`のパラメータ`bitmap.Save`メソッドを JPEG、BMP、GIF などの他のサポートされている画像形式に変換します。さらに、要件に基づいて画質や圧縮設定を調整できます。

#### Q: 抽出された境界線に対して他にどのような操作を実行できますか?

A: 境界線を画像として抽出したら、画像処理ライブラリまたはアルゴリズムを使用してさらに処理できます。必要に応じて、画像を分析したり、画像フィルターを適用したり、パターンを検出したり、OCR (光学式文字認識) を実行して画像からテキストを抽出したりできます。

#### Q: 複雑な PDF ドキュメントから境界線を抽出する際に制限や考慮事項はありますか?

A: 抽出プロセスは、PDF ドキュメントの複雑さによって異なる場合があります。複数のレイヤー、透明度、または高度なグラフィックスを含む複雑な PDF では、境界線を正確に抽出するために追加の処理や調整が必要になる場合があります。信頼性の高い結果を確保するには、さまざまな PDF ドキュメントで抽出プロセスを徹底的にテストすることが重要です。