---
title: 方向を変える
linktitle: 方向を変える
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF のページの向きを変更するためのステップバイステップ ガイド。簡単に実行でき、プロジェクトに実装できます。
type: docs
weight: 10
url: /ja/net/programming-with-pdf-pages/change-orientation/
---
## 導入

ページの向きがまったくずれている PDF ファイルで苦労したことはありませんか? おそらく、スキャンまたは作成が不適切だったドキュメントを扱っていて、ページを回転しないと意味が通じないのでしょう。幸いなことに、Aspose.PDF for .NET は、ページの向きの変更を含め、考えられるほぼあらゆる方法で PDF ファイルを操作する簡単で強力な方法を提供します。縦向きから横向きに、またはその逆に切り替えたい場合、このガイドでは手順を追って手順を説明します。

では、PDF ページを簡単に回転させる準備ができたら、始めましょう。

## 前提条件

PDF のページの向きを変更する詳細に入る前に、必要な準備について簡単に説明しましょう。

-  Aspose.PDF for .NET: Aspose.PDFライブラリが.NET用にインストールされていることを確認してください。まだインストールされていない場合は、[ここからダウンロード](https://releases.aspose.com/pdf/net/).
- .NET 開発環境: .NET での作業には、Visual Studio、JetBrains Rider、または任意の IDE を使用できます。
- C# の基本知識: このガイドはわかりやすいですが、C# の基本を理解しておくと、さらに理解しやすくなります。
- PDF ファイル: 以下の例では、複数ページの PDF ファイルがあることを前提としています。手元に PDF ファイルがない場合は、サンプル PDF を作成またはダウンロードして作業してください。

また、まだ始めたばかりの場合は、Aspose.PDFを[無料の一時ライセンス](https://purchase.aspose.com/temporary-license/)決める前に[フルバージョンを購入する](https://purchase.aspose.com/buy).

## 名前空間のインポート

PDF のページの向きを操作する前に、C# プロジェクトに必要な名前空間をインポートする必要があります。次のものがあることを確認してください。

```csharp
using System.IO;
using Aspose.Pdf;
```

これをインポートしたら、チュートリアルのメイン部分に進みましょう。

## ステップ1: PDFドキュメントを読み込む

まず最初に、変更したいPDFファイルを読み込みます。`Document` PDF を開くには、Aspose.PDF 名前空間のクラスを使用します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

この行は、指定したディレクトリからPDFを読み込みます。`"YOUR DOCUMENT DIRECTORY"`ファイルの実際のパスを入力します。`"input.pdf"`向きを変更する PDF です。

## ステップ2: 各ページをループする

ドキュメントが読み込まれたので、PDFの各ページをループしてみましょう。`foreach`ループしてすべてのページを巡回し、すべてのページに向きの変更を適用できるようにします。

```csharp
foreach (Page page in doc.Pages)
{
    //各ページを操作する
}
```

このループはドキュメント内のすべてのページを反復処理します。

## ステップ3: ページのMediaBoxを取得する

PDFの各ページには`MediaBox`ページの境界を定義します。現在の方向を決定し、変更するには、これにアクセスする必要があります。

```csharp
Aspose.Pdf.Rectangle r = page.MediaBox;
```

の`MediaBox`ページの幅、高さ、位置などの寸法がわかります。

## ステップ4: 幅と高さを入れ替える

ページの向きを縦向きから横向きへ、または横向きから縦向きへ変更するには、幅と高さの値を入れ替えるだけです。この手順でページのサイズが調整されます。

```csharp
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
```

このコードは高さと幅を入れ替え、左下隅の位置を変更します（`LLY`）を使用すると、回転後にコンテンツがきれいに収まるようになります。

## ステップ5: MediaBoxとCropBoxを更新する

新しい高さと幅ができたので、ページに変更を適用してみましょう。`MediaBox`そして`CropBox` 。`CropBox`元のドキュメントに 1 セットある場合は、ページ全体が正しく表示されるようにするために不可欠です。

```csharp
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
```

この手順では、計算した新しい寸法に基づいてページのサイズを変更します。

## ステップ6: ページを回転する

最後に、ページの回転角度を設定します。Aspose.PDF を使用すると、これが非常に簡単になります。ページを 90 度回転して、縦向きから横向きに、またはその逆に変更できます。

```csharp
page.Rotate = Rotation.on90;
```

このコードはページを 90 度回転し、目的の方向に反転します。

## ステップ7: 出力PDFを保存する

すべてのページに向きの変更を適用した後、変更されたドキュメントを新しいファイルに保存します。 

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);
```

新しいファイル名を必ず指定してください（この場合は、`ChangeOrientation_out.pdf`) をクリックして出力を保存します。この方法では、元のファイルが上書きされることはありません。

### 結論

これで完了です。Aspose.PDF for .NET を使用して PDF ファイルのページの向きを変更するのは、ドキュメントを読み込み、ページをループし、MediaBox を調整し、更新されたファイルを保存するだけです。スキャンが不十分なドキュメントを扱う場合でも、書式設定のニーズに合わせてページを回転する必要がある場合でも、このステップ バイ ステップ ガイドが役立ちます。

## よくある質問

### PDF 内のすべてのページではなく、特定のページを回転できますか?  
はい、すべてのページをループするのではなく、インデックスを使用して特定のページをターゲットにするようにループを変更できます。

### 何ですか`MediaBox`?  
の`MediaBox`PDF ファイルのページのサイズと形状を定義します。ページのコンテンツが配置される場所です。

### Aspose.PDF for .NET は他のファイル形式でも動作しますか?  
はい、Aspose.PDF は HTML、XML、XPS などのさまざまなファイル形式を処理できます。

### Aspose.PDF for .NET の無料バージョンはありますか?  
はい、まずは[無料トライアル](https://releases.aspose.com/)またはリクエスト[一時ライセンス](https://purchase.aspose.com/temporary-license/).

### 一度保存した変更を元に戻すことはできますか?  
ドキュメントを保存すると、変更は永続的になります。必ずコピーで作業するか、元のファイルのバックアップを保存してください。