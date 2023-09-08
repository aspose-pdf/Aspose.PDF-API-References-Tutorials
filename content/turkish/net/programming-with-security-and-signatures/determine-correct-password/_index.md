---
title: PDF Dosyasında Doğru Şifreyi Belirleyin
linktitle: PDF Dosyasında Doğru Şifreyi Belirleyin
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile PDF dosyasında doğru şifreyi nasıl belirleyeceğinizi öğrenin.
type: docs
weight: 30
url: /tr/net/programming-with-security-and-signatures/determine-correct-password/
---
Bu eğitimde, Aspose.PDF for .NET'i kullanarak PDF dosyasında doğru şifreyi belirleme sürecinde size yol göstereceğiz. Bu özellik, bir PDF dosyasının parola korumalı olup olmadığını kontrol etmenize ve önceden tanımlanmış bir listeden doğru parolayı bulmanıza olanak tanır.

## 1. Adım: Önkoşullar

Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

- C# programlama dili hakkında temel bilgi
- Visual Studio'yu makinenize yükleme
- .NET için Aspose.PDF kütüphanesi kuruldu

## 2. Adım: Ortam kurulumu

Başlamak için geliştirme ortamınızı ayarlamak üzere şu adımları izleyin:

1. Visual Studio'yu açın ve yeni bir C# projesi oluşturun.
2. Gerekli ad alanlarını kod dosyanıza aktarın:

```csharp
using Aspose.Pdf;
```

## 3. Adım: Kaynak PDF dosyasını yükleme

İlk adım, doğrulamak istediğiniz kaynak PDF dosyasını yüklemektir. Bu örnekte belirtilen dizinde "IsPasswordProtected.pdf" adında bir PDF dosyanızın olduğunu varsayıyoruz.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
```

Yer tutucuları PDF dosyanızın gerçek konumlarıyla değiştirdiğinizden emin olun.

## Adım 4: Kaynak PDF Şifrelemesini Belirleyin

Kaynak PDF dosyasını yükledikten sonra, şifreli olup olmadığını aşağıdaki düğmeyi kullanarak belirleyebilirsiniz:`IsEncrypted` yöntemi`PdfFileInfo` nesne.

```csharp
Console.WriteLine("The file is password protected: " + info.IsEncrypted);
```

Bu ifade, PDF dosyasının parola korumalı olup olmadığını görüntüler.

## Adım 5: Doğru şifreyi bulma

Daha sonra, önceden tanımlanmış bir şifre listesini kullanarak doğru şifreyi arayacağız. Listedeki her şifreyi inceliyoruz ve PDF belgesini bu şifreyle yüklemeye çalışıyoruz.

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

Bu döngü listedeki her geçiş kelimesini test eder. Şifre doğruysa belgedeki sayfa sayısı görüntülenir. Aksi halde şifrenin doğru olmadığını belirten bir mesaj görüntülenir.


### Aspose.PDF for .NET kullanarak Doğru Şifreyi Belirlemek için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";            
// Kaynak PDF dosyasını yükle
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
// Kaynak PDF'nin şifrelenip şifrelenmediğini belirleme
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

Tebrikler! Aspose.PDF for .NET'i kullanarak bir PDF dosyası için doğru şifreyi başarıyla belirlediniz. Bu eğitimde, dosya şifrelemesinin doğrulanmasından önceden tanımlanmış bir listeden doğru şifrenin bulunmasına kadar adım adım süreç anlatılmıştır. Artık PDF dosyalarınızın doğru şifresini kontrol etmek ve bulmak için bu özelliği kullanabilirsiniz.

### PDF dosyasında doğru şifreyi belirlemek için SSS

#### S: Bu eğitimin amacı nedir?

C: Bu eğitimin amacı, Aspose.PDF for .NET kullanarak bir PDF dosyası için doğru şifreyi belirleme sürecinde size rehberlik etmektir. Bu özellik, bir PDF dosyasının parola korumalı olup olmadığını kontrol etmenize ve önceden tanımlanmış bir listeden doğru parolayı bulmaya çalışmanıza olanak tanır.

#### S: Başlamadan önce hangi önkoşullar gereklidir?

C: Başlamadan önce, C# programlama dili hakkında temel bilgiye sahip olduğunuzdan, makinenizde Visual Studio'nun kurulu olduğundan ve Aspose.PDF kütüphanesinin .NET için kurulu olduğundan emin olun.

#### S: Geliştirme ortamını nasıl kurarım?

C: Visual Studio'da yeni bir C# projesi oluşturma ve gerekli ad alanlarını içe aktarma da dahil olmak üzere geliştirme ortamınızı kurmak için sağlanan adımları izleyin.

#### S: Bir PDF dosyasının şifrelenip şifrelenmediğini nasıl belirleyebilirim?

 C: Kullan`PdfFileInfo` Kaynak PDF dosyasını bağlamak için sınıf. Daha sonra şunu kullanın:`IsEncrypted` PDF dosyasının parola korumalı olup olmadığını belirleme özelliği.

#### S: Bir PDF dosyası için doğru şifreyi nasıl bulabilirim?

C: PDF dosyasının şifrelendiğini belirledikten sonra, önceden tanımlanmış bir şifre listesini kullanarak doğru şifreyi bulmayı deneyebilirsiniz. Sağlanan örnek kod, listede nasıl döngü yapılacağını, her parolanın nasıl deneneceğini ve parolanın doğru olup olmadığının nasıl belirleneceğini gösterir.

#### S: Doğru şifre bulunursa ne olur?

C: Doğru şifre bulunursa örnek kod, PDF belgesindeki sayfa sayısını gösterecektir.

#### S: Şifre doğru değilse ne olur?

 C: Şifre doğru değilse örnek kod,`InvalidPasswordException` ve şifrenin doğru olmadığını belirten bir mesaj görüntüleyin.

#### S: Farklı bir şifre listesi kullanabilir miyim?

 C: Evet, değiştirebilirsiniz`passwords` test etmek istediğiniz şifreleri içerecek şekilde örnek koddaki dizi.

#### S: Şifrenin başarıyla belirlendiğini nasıl bileceğim?

C: Örnek kod, PDF belgesini şifreyle başarıyla yüklüyor ve sayfa sayısını gösteriyorsa bu, doğru şifrenin belirlendiği anlamına gelir.

#### S: Test sırasında şifrelerimin güvenliğini nasıl sağlayabilirim?

C: Önceden tanımlanmış bir şifre listesi kullanırken dikkatli olun ve hassas veya gizli şifreleri test amacıyla kullanmaktan kaçının. Ayrıca uygulamanızı dağıtmadan önce test kodunu kaldırın veya değiştirin.