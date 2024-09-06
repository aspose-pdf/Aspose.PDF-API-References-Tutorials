---
title: PDF Dosyasında Doğru Şifreyi Belirleyin
linktitle: PDF Dosyasında Doğru Şifreyi Belirleyin
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasındaki doğru şifrenin nasıl belirleneceğini öğrenin.
type: docs
weight: 30
url: /tr/net/programming-with-security-and-signatures/determine-correct-password/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak PDF dosyasında doğru parolayı belirleme sürecinde size yol göstereceğiz. Bu özellik, bir PDF dosyasının parola korumalı olup olmadığını kontrol etmenizi ve önceden tanımlanmış bir listeden doğru parolayı bulmanızı sağlar.

## Adım 1: Ön koşullar

Başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

- C# programlama dilinin temel bilgisi
- Visual Studio'yu makinenize yükleme
- .NET için Aspose.PDF kütüphanesi yüklendi

## Adım 2: Ortam kurulumu

Başlamak için geliştirme ortamınızı kurmak üzere şu adımları izleyin:

1. Visual Studio'yu açın ve yeni bir C# projesi oluşturun.
2. Gerekli ad alanlarını kod dosyanıza aktarın:

```csharp
using Aspose.Pdf;
```

## Adım 3: Kaynak PDF dosyasını yükleme

İlk adım, doğrulamak istediğiniz kaynak PDF dosyasını yüklemektir. Bu örnekte, belirtilen dizinde "IsPasswordProtected.pdf" adlı bir PDF dosyanız olduğunu varsayıyoruz.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
```

Yer tutucuları PDF dosyanızın gerçek konumlarıyla değiştirdiğinizden emin olun.

## Adım 4: Kaynak PDF Şifrelemesini Belirleyin

 Kaynak PDF dosyasını yükledikten sonra, şifrelenip şifrelenmediğini belirlemek için şunu kullanabilirsiniz:`IsEncrypted` yöntemi`PdfFileInfo` nesne.

```csharp
Console.WriteLine("The file is password protected: " + info.IsEncrypted);
```

Bu ifade PDF dosyasının şifreyle korunup korunmadığını gösterir.

## Adım 5: Doğru şifreyi bulma

Daha sonra, önceden tanımlanmış bir parola listesi kullanarak doğru parolayı arayacağız. Listedeki her parolayı inceleyip o parolayla PDF belgesini yüklemeye çalışacağız.

```csharp
String[] passwords = new String[5] { "test", "test1", "test2", "test3", "sample" };
for (int passwordcount = 0; passwordcount < passwords.Length; passwordcount++)
{
try
{
Document doc = new Document(dataDir + "IsPasswordProtected.pdf", passwords[passwordcount]);
if (doc.Pages.Count > 0)
Console.WriteLine("The document contains " + doc.Pages.Count + " pages.");
}
catch (InvalidPasswordException)
{
Console.WriteLine("The password " + passwords[passwordcount] + " is not correct.");
}
}
```

Bu döngü, listeden geçen her sözcüğü test eder. Parola doğruysa, belgedeki sayfa sayısı görüntülenir. Aksi takdirde, parolanın doğru olmadığını belirten bir mesaj görüntülenir.


### .NET için Aspose.PDF kullanarak Doğru Parolayı Belirleme için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";            
// Kaynak PDF dosyasını yükle
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
//Kaynak PDF'nin şifrelenmiş olup olmadığını belirleyin
Console.WriteLine("File is password protected " + info.IsEncrypted);
String[] passwords = new String[5] { "test", "test1", "test2", "test3", "sample" };
for (int passwordcount = 0; passwordcount < passwords.Length; passwordcount++)
{
	try
	{
		Document doc = new Document(dataDir + "IsPasswordProtected.pdf", passwords[passwordcount]);
		if (doc.Pages.Count > 0)
			Console.WriteLine("Number of Page in document are = " + doc.Pages.Count);
	}
	catch (InvalidPasswordException)
	{
		Console.WriteLine("Password = " + passwords[passwordcount] + "  is not correct");
	}
}
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF dosyası için doğru parolayı başarıyla belirlediniz. Bu eğitim, dosya şifrelemesini doğrulamaktan önceden tanımlanmış bir listeden doğru parolayı bulmaya kadar adım adım süreci kapsıyordu. Artık bu özelliği kullanarak PDF dosyalarınızın doğru parolasını kontrol edebilir ve bulabilirsiniz.

### PDF dosyasında doğru şifreyi belirlemek için SSS

#### S: Bu eğitimin amacı nedir?

A: Bu eğitim, .NET için Aspose.PDF kullanarak bir PDF dosyası için doğru parolayı belirleme sürecinde size rehberlik etmeyi amaçlamaktadır. Bu özellik, bir PDF dosyasının parola korumalı olup olmadığını kontrol etmenizi ve önceden tanımlanmış bir listeden doğru parolayı bulmaya çalışmanızı sağlar.

#### S: Başlamadan önce hangi ön koşullar gereklidir?

C: Başlamadan önce, C# programlama dili hakkında temel bir anlayışa sahip olduğunuzdan, makinenizde Visual Studio'nun ve .NET için Aspose.PDF kütüphanesinin yüklü olduğundan emin olun.

#### S: Geliştirme ortamını nasıl kurarım?

A: Visual Studio'da yeni bir C# projesi oluşturmak ve gerekli ad alanlarını içe aktarmak da dahil olmak üzere geliştirme ortamınızı kurmak için verilen adımları izleyin.

#### S: Bir PDF dosyasının şifreli olup olmadığını nasıl belirlerim?

 A: Şunu kullanın:`PdfFileInfo` kaynak PDF dosyasını bağlamak için sınıf. Ardından, şunu kullanın`IsEncrypted`PDF dosyasının parola korumalı olup olmadığını belirlemek için kullanılan özellik.

#### S: Bir PDF dosyasının doğru şifresini nasıl bulabilirim?

A: PDF dosyasının şifrelendiğini belirledikten sonra, önceden tanımlanmış bir parola listesi kullanarak doğru parolayı bulmayı deneyebilirsiniz. Sağlanan örnek kod, listede nasıl dolaşılacağını, her parolanın nasıl deneneceğini ve parolanın doğru olup olmadığının nasıl belirleneceğini gösterir.

#### S: Doğru şifre bulunursa ne olur?

A: Doğru şifre bulunursa, örnek kod PDF belgesindeki sayfa sayısını gösterecektir.

#### S: Şifre doğru değilse ne olur?

 A: Şifre doğru değilse, örnek kod bunu yakalayacaktır.`InvalidPasswordException` ve şifrenin doğru olmadığını belirten bir mesaj görüntülenir.

#### S: Farklı bir şifre listesi kullanabilir miyim?

 A: Evet, değiştirebilirsiniz`passwords` Örnek kodda test etmek istediğiniz şifreleri içeren dizi.

#### S: Şifrenin başarıyla belirlendiğini nasıl bileceğim?

A: Eğer örnek kod PDF dokümanını şifreli bir şekilde başarıyla yüklüyorsa ve sayfa sayısını gösteriyorsa doğru şifre belirlenmiş demektir.

#### S: Test sırasında şifrelerimin güvenliğini nasıl sağlayabilirim?

A: Önceden tanımlanmış bir parola listesi kullanırken dikkatli olun ve test amaçlı hassas veya gizli parolalar kullanmaktan kaçının. Ayrıca, uygulamanızı dağıtmadan önce test kodunu kaldırın veya değiştirin.