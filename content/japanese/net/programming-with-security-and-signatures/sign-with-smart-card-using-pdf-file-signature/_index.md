---
title: PDF ファイル署名を使用してスマート カードで署名する
linktitle: PDF ファイル署名を使用してスマート カードで署名する
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET でスマート カードを使用して PDF ファイルに署名する方法を学びます。安全なデジタル署名については、このステップ バイ ステップ ガイドに従ってください。
type: docs
weight: 110
url: /ja/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
## 導入

デジタル時代では、文書のセキュリティ保護がこれまで以上に重要になっています。契約書、合意書、機密情報など、文書が本物であり、改ざんされていないことを確認することが最も重要です。そこでデジタル署名の出番です。今日は、Aspose.PDF for .NET でスマート カードを使用して PDF ファイルに署名する方法について詳しく説明します。この強力なライブラリにより、開発者は PDF 文書を効率的に操作および作成でき、安全なデジタル署名を追加することもできます。スマート カードを用意して、始めましょう。

## 前提条件

PDF ファイルに署名する手順に入る前に、必要なものがすべて揃っていることを確認しましょう。準備に役立つチェックリストを以下に示します。

1.  Aspose.PDF for .NET: Aspose.PDFライブラリがインストールされていることを確認してください。[サイト](https://releases.aspose.com/pdf/net/).
2. Visual Studio: .NET コードを記述して実行できる開発環境。
3. スマート カード: 有効なデジタル証明書がインストールされたスマート カードが必要です。
4. C# の基本的な理解: この言語でコード スニペットを記述するため、C# プログラミングの知識があると役立ちます。
5. PDFドキュメント: サンプルPDFファイル（`blank.pdf`) を使用して署名プロセスをテストします。

これらの前提条件が整ったら、コードに取り組む準備が整いました。

## パッケージのインポート

まず最初に、必要なパッケージをインポートしましょう。プロジェクトに Aspose.PDF ライブラリへの参照を追加する必要があります。方法は次のとおりです。

1. Visual Studio を開きます。
2. 新しいプロジェクトを作成するか、既存のプロジェクトを開きます。
3. ソリューションエクスプローラーでプロジェクトを右クリックし、`Manage NuGet Packages`.
4. 検索する`Aspose.PDF`最新バージョンをインストールしてください。

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

必要なパッケージをインポートしたので、コードを段階的に分解してみましょう。

## ステップ1: ドキュメントを設定する

プロセスの最初のステップは、署名する PDF ドキュメントを設定することです。手順は次のとおりです。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
```
このスニペットでは、ドキュメントディレクトリへのパスを定義し、`Document`サンプルPDFファイルを使用したクラス`blank.pdf`必ず交換してください`"YOUR DOCUMENTS DIRECTORY"` PDF が配置されている実際のパスを入力します。

## ステップ2: PdfFileSignatureを初期化する

次に、`PdfFileSignature`署名プロセスの処理を担当するクラスです。

```csharp
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
    pdfSign.BindPdf(doc);
```
ここでは、`PdfFileSignature`これを PDF ドキュメントにバインドします。これで、ドキュメントに署名する準備が整います。

## ステップ3: スマートカード証明書にアクセスする

ここで重要な部分、つまりスマート カードに保存されているデジタル証明書にアクセスする部分が登場します。その方法は次のとおりです。

### 証明書ストアを開く

```csharp
System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
```
現在のユーザーのプロファイルにある証明書ストアを開きます。これにより、スマート カード上の証明書を含む、マシンにインストールされている証明書にアクセスできるようになります。

### 証明書を選択

```csharp
System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel =
    System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(
        store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
```
このコードは、ユーザーにコレクションから証明書を選択するよう求めます。ユーザー インターフェイスには利用可能なすべての証明書が表示され、スマート カードに関連付けられている証明書を選択できます。

## ステップ4: 外部署名を作成する

証明書を選択したら、次のステップは、選択した証明書を使用して外部署名を作成することです。

```csharp
Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
```
ここでは、`ExternalSignature`選択した証明書を使用します。このオブジェクトは PDF ドキュメントに署名するために使用されます。

## ステップ5: 署名の外観を設定する

次に、署名の外観を設定しましょう。ここで、文書上での署名の外観をカスタマイズできます。

```csharp
pdfSign.SignatureAppearance = dataDir + "demo.png";
```
このスニペットでは、画像ファイル（ロゴや署名グラフィックなど）へのパスを指定して署名の外観を指定します。`"demo.png"`実際に使用する画像を使用します。

## ステップ6: PDFに署名する

すべての設定が完了したら、PDF ドキュメントに署名します。

```csharp
pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
pdfSign.Save(dataDir + "externalSignature2.pdf");
```
このステップでは、`Sign`私たちの方法`pdfSign`オブジェクト。各パラメータの意味は次のとおりです。
- `1`: 署名が表示されるページ番号。
- `"Reason"`: 文書に署名する理由。
- `"Contact"`: 署名者の連絡先情報。
- `"Location"`: 署名者の所在地。
- `true`: 可視署名を作成するかどうかを示します。
- `new System.Drawing.Rectangle(100, 100, 200, 200)`: PDF 上の署名の位置とサイズ。
- `externalSignature`: 先ほど作成した署名オブジェクト。

最後に、署名された文書を次のように保存します。`externalSignature2.pdf`.

## ステップ7: 署名を確認する

文書に署名した後は、署名が有効であることを確認することが重要です。その方法は次のとおりです。

### 検証プロセスの初期化

```csharp
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
    IList<string> sigNames = pdfSign.GetSignNames();
```
新しいインスタンスを作成します`PdfFileSignature`署名された文書の場合、文書内に存在するすべての署名の名前を取得します。

### 署名の有効性を確認する

```csharp
for (int index = 0; index <= sigNames.Count - 1; index++)
{
    if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
    {
        throw new ApplicationException("Not verified");
    }
}
```
各署名名をループして、その有効性を検証します。いずれかの署名が検証に失敗した場合、署名が無効であることを示す例外がスローされます。

## 結論

これで完了です。Aspose.PDF for .NET でスマート カードを使用して PDF ドキュメントに署名できました。このプロセスはドキュメントのセキュリティを確保するだけでなく、今日のデジタル世界では極めて重要な信頼性のレイヤーを追加します。契約書、法的文書、または機密情報を扱う場合でも、デジタル署名の実装方法を知ることは貴重なスキルです。 

## よくある質問

### Aspose.PDF for .NET とは何ですか?
Aspose.PDF for .NET は、開発者が .NET アプリケーション内で PDF ドキュメントを作成、操作、変換できるようにする強力なライブラリです。

### PDF に署名するにはスマート カードが必要ですか?
スマート カードは必須ではありませんが、セキュリティがさらに強化されるため、安全なデジタル署名には強く推奨されます。

### 任意の PDF ファイルを使用して署名できますか?
はい、どの PDF ファイルでも使用できますが、パスワードで保護されていないことを確認してください。保護されている場合は、まずロックを解除する必要があります。

### デジタル証明書を持っていない場合はどうなりますか?
信頼できる証明機関 (CA) からデジタル証明書を取得するか、テスト目的で自己署名証明書を使用することができます。

### Aspose.PDF の試用版はありますか?
はい、無料試用版をこちらからダウンロードできます。[Aspose ウェブサイト](https://releases.aspose.com/).