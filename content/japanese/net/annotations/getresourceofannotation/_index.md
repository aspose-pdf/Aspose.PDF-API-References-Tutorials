---
title: アノテーションのリソースを取得
linktitle: アノテーションのリソースを取得
second_title: Aspose.PDF for .NET API リファレンス
description: このステップバイステップ ガイドでは、Aspose.PDF for .NET を使用して注釈のリソースを取得する方法を学習します。
type: docs
weight: 90
url: /ja/net/annotations/getresourceofannotation/
---
この例では、Aspose.PDF for .NET を使用してアノテーションのリソースを取得する方法を示します。 Aspose.PDF for .NET を使用して注釈のリソースを取得するには、次の手順に従います。

## ステップ 1: ドキュメントが存在するディレクトリのパスを設定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: リソースを取得したい注釈を含む PDF ドキュメントを開きます。

```csharp
Document doc = new Document(dataDir + "AddAnnotation.pdf");
```

## ステップ 3: 注釈を作成します。

```csharp
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
```

## ステップ 4: ドキュメント内のページに注釈を追加します。

```csharp
doc.Pages[1].Annotations.Add(sa);
```

## ステップ 5: ドキュメントを保存します。

```csharp
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## ステップ 6: 変更したドキュメントを開きます。

```csharp
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## ステップ 7: アノテーションのアクションを取得します。

```csharp
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
```

## ステップ 7: アクションのレンディションを取得します。

```csharp
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
```

## ステップ 8: メディア クリップを取得します。

```csharp
MediaClip clip = (rendition as MediaRendition).MediaClip;
```

## ステップ 9: ファイル仕様を取得します。

```csharp
FileSpecification data = (clip as MediaClipData).Data;
```

## ステップ 10: メディアのデータを読み取ります。

```csharp
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
   ms.Write(buffer, 0, read);
}
```

## ステップ 11: レンディションの名前とレンディション操作を出力します。

```csharp
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

これらの手順に従うと、Aspose.PDF for .NET を使用して PDF ドキュメント内の注釈のリソースを簡単に取得できます。

### Aspose.PDF for .NET を使用した注釈のリソースの取得のソース コードの例:

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開いた文書
Document doc = new Document(dataDir + "AddAnnotation.pdf");
//注釈の作成
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
doc.Pages[1].Annotations.Add(sa);
//文書の保存
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
//開いた文書
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
//アノテーションのアクションを取得する
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
//レンディションアクションのレンディションを取得します
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
//メディアクリップ
MediaClip clip = (rendition as MediaRendition).MediaClip;
FileSpecification data = (clip as MediaClipData).Data;
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
//メディアのデータは FileSpecific.Contents でアクセスできます。
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
ms.Write(buffer, 0, read);
}
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントから特定の注釈のリソースを取得する方法を検討しました。ステップバイステップのガイドに従い、提供されている C# ソース コードを使用することで、開発者は PDF ドキュメント内のレンディション注釈を含む注釈に簡単にアクセスして管理できます。

### よくある質問

#### Q: PDF 注釈のコンテキストにおけるレンディションとは何ですか?

A: PDF 注釈のコンテキストでは、レンディションはマルチメディア コンテンツのプレゼンテーションです。 PDF ドキュメント内にオーディオやビデオなどのマルチメディアを埋め込むことができます。レンディションの注釈は、提示されるメディアとその再生方法を指定します。

#### Q: レンディションの注釈に関連付けられたメディア ファイルの名前を取得できますか?

A: はい、Aspose.PDF for .NET を使用して、レンディション アノテーションに関連付けられたメディア ファイルの名前を取得できます。メディア ファイル名には、`FileSpecification`の`MediaClip`物体。

#### Q: Aspose.PDF for .NET はレンディションの注釈からメディア ファイルを抽出できますか?

A: はい、Aspose.PDF for .NET は、オーディオまたはビデオ コンテンツを含むメディア データをレンディション アノテーションから抽出し、別のファイルとして保存できます。

#### Q: レンディションアノテーションのメディアデータにアクセスするにはどうすればよいですか?

 A: レンディション アノテーションのメディア データには、`FileSpecification.Contents`の財産`MediaClipData`物体。

#### Q: Aspose.PDF for .NET を使用して、レンディション アノテーションに関連付けられたメディアを変更できますか?

A: Aspose.PDF for .NET は、レンディション アノテーションに関連付けられたメディア データにアクセスして変更するためのメソッドを提供します。レンディションアノテーションで使用されるメディアファイルを更新または置換できます。