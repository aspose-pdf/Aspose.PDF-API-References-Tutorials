---
title: 権利を守る
linktitle: 権利を守る
second_title: Aspose.PDF for .NET API リファレンス
description: Aspose.PDF for .NET を使用して PDF ドキュメント内のフォーム権限を保持します。
type: docs
weight: 210
url: /ja/net/programming-with-forms/preserve-rights/
---
このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメントのフォーム権限を保持する方法を説明します。このプロセスをガイドするために、C# ソース コードを段階的に説明します。

## ステップ1: 準備

必要なライブラリがインポートされ、ドキュメント ディレクトリへのパスが設定されていることを確認してください。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: ドキュメントを開く

ソースPDF文書を`FileStream`読み取りおよび書き込み権限付き:

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## ステップ3: フォームフィールドを編集する

ドキュメント内のすべてのフォーム フィールドを調べて、必要な変更を加えます。この例では、名前に「A1」が含まれるフォーム フィールドの値を変更します。

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

## ステップ4: 更新したドキュメントを保存する

変更した PDF ドキュメントを保存します。

```csharp
pdfDocument.Save();
```

## ステップ5:`FileStream`

忘れずに閉じてください`FileStream`完了したらオブジェクトを作成します。

```csharp
fs. Close();
```

### Aspose.PDF for .NET を使用した Preserve Rights のサンプル ソース コード 
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//読み取りと書き込みの FileAccess を使用してソース PDF フォームを読み取ります。
//変更後には読み取り書き込み権限が必要になるため、
//更新されたコンテンツを同じドキュメント/ファイルに保存する必要があります。
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
//ドキュメントインスタンスをインスタンス化する
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
//すべてのフィールドから値を取得する
foreach (Field formField in pdfDocument.Form)
{
	//フィールドのフルネームにA1が含まれている場合は、操作を実行します。
	if (formField.FullName.Contains("A1"))
	{
		//フォームフィールドをテキストボックスとしてキャストする
		TextBoxField textBoxField = formField as TextBoxField;
		//フィールド値を変更する
		textBoxField.Value = "Testing";
	}
}
//更新されたドキュメントをFileStreamに保存する
pdfDocument.Save();
//ファイルストリームオブジェクトを閉じる
fs.Close();
```

## 結論

このチュートリアルでは、Aspose.PDF for .NET を使用して PDF ドキュメント内のフォームの権限を保持する方法を学習しました。これらの手順に従うことで、アクセス権限と書き込み権限を保持しながら、フォーム フィールドに簡単にアクセスし、特定の変更を加えることができます。


### よくある質問

#### Q: PDF ドキュメント内の他のフィールドに影響を与えずに、特定のフォーム フィールドの権限を保持できますか?

 A: はい、`FullName`フォーム フィールドのプロパティを使用すると、他のフォーム フィールドに影響を与えずに、特定のフォーム フィールドのみを保存対象にすることができます。

#### Q: パスワードで保護された PDF ドキュメント内のフォームの権限を保持できますか?

A: はい、Aspose.PDF for .NET では、ファイルにアクセスして変更するための正しいパスワードを入力する限り、パスワードで保護された PDF ドキュメントでもフォームの権限を保持できます。

#### Q: 適切なアクセス権なしでフォーム フィールドを変更しようとするとどうなりますか?

A: 適切なアクセス権を持たずにフォーム フィールドを変更しようとすると、変更は PDF ドキュメントに保存されず、例外またはエラー メッセージが表示される場合があります。

#### Q: Aspose.PDF for .NET は、すべてのバージョンの .NET Framework と互換性がありますか?

A: はい、Aspose.PDF for .NET は、.NET Core および .NET Standard を含むすべてのバージョンの .NET Framework と互換性があります。

#### Q: C# 以外のプログラミング言語で PDF ドキュメントのフォーム権限をプログラム的に保持できますか?

A: はい、Aspose.PDF for .NET は C# に加えて、VB.NET や ASP.NET などのさまざまなプログラミング言語をサポートしています。