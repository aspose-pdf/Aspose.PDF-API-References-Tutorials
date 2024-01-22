---
title: 権利の保持
linktitle: 権利の保持
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ドキュメント内のフォーム権限を保持します。
type: docs
weight: 210
url: /ja/net/programming-with-forms/preserve-rights/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内のフォーム権限を保持する方法を説明します。このプロセスをガイドするために、C# ソース コードをステップごとに説明します。

## ステップ 1: 準備

必要なライブラリをインポートし、ドキュメント ディレクトリへのパスを設定していることを確認してください。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: ドキュメントを開く

を使用してソース PDF ドキュメントを開きます。`FileStream`読み取りおよび書き込み権限がある場合:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## ステップ 3: フォームフィールドを編集する

文書内のすべてのフォームフィールドを調べて、必要な変更を加えます。この例では、名前に「A1」を含むフォーム フィールドの値を変更しています。

```csharp
foreach(Field formField in pdfDocument.Form)
{
if (formField.FullName.Contains("A1"))
{
TextBoxField textBoxField = formField as TextBoxField;
textBoxField.Value = "Testing";
}
}
```

## ステップ 4: 更新されたドキュメントを保存する

変更した PDF ドキュメントを保存します。

```csharp
pdfDocument.Save();
```

## ステップ 5:`FileStream`

を閉じることを忘れないでください`FileStream`完了したらオブジェクトを作成します。

```csharp
fs. Close();
```

### Aspose.PDF for .NET を使用した権利保持のサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//読み取りおよび書き込みの FileAccess を使用してソース PDF フォームを読み取ります。
//変更後は、ReadWrite 権限が必要です。
//更新された内容を同じドキュメント/ファイルに保存する必要があります。
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
//ドキュメントインスタンスをインスタンス化する
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
//すべてのフィールドから値を取得する
foreach (Field formField in pdfDocument.Form)
{
	//フィールドのフルネームに A1 が含まれている場合は、次の操作を実行します。
	if (formField.FullName.Contains("A1"))
	{
		//フォームフィールドをTextBoxとしてキャスト
		TextBoxField textBoxField = formField as TextBoxField;
		//フィールド値を変更する
		textBoxField.Value = "Testing";
	}
}
//更新されたドキュメントを保存 FileStream に保存します
pdfDocument.Save();
//ファイルストリームオブジェクトを閉じます。
fs.Close();
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内のフォームの権利を保持する方法を学びました。これらの手順に従うことで、アクセス権と書き込み権限を維持したまま、フォーム フィールドに簡単にアクセスし、特定の変更を加えることができます。


### よくある質問

#### Q: PDF ドキュメント内の他のフォームフィールドに影響を与えずに、特定のフォームフィールドの権利を保持できますか?

 A: はい、`FullName`フォーム フィールドのプロパティを使用すると、他のフォーム フィールドには影響を与えずに、特定のフォーム フィールドを保存対象にすることができます。

#### Q: パスワードで保護された PDF ドキュメント内のフォームの権利を保持できますか?

A: はい、Aspose.PDF for .NET を使用すると、ファイルにアクセスして変更するための正しいパスワードを指定する限り、パスワードで保護された PDF ドキュメントであってもフォームの権限を保持できます。

#### Q: 適切なアクセス権を持たずにフォームフィールドを変更しようとするとどうなりますか?

A: 適切なアクセス権を持たずにフォーム フィールドを変更しようとすると、変更内容は PDF ドキュメントに保存されず、例外またはエラー メッセージが表示される場合があります。

#### Q: Aspose.PDF for .NET は、.NET Framework のすべてのバージョンと互換性がありますか?

A: はい、Aspose.PDF for .NET は、.NET Core や .NET Standard を含む .NET Framework のすべてのバージョンと互換性があります。

#### Q: C# 以外のプログラミング言語でプログラム的に PDF ドキュメントのフォーム権限を保持できますか?

A: はい、Aspose.PDF for .NET は、C# に加えて、VB.NET や ASP.NET などのさまざまなプログラミング言語をサポートしています。