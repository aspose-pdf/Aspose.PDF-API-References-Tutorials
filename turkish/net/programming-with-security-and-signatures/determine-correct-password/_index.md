---
title: PDF Dosyasında Doğru Parolayı Belirleyin
linktitle: PDF Dosyasında Doğru Parolayı Belirleyin
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasında doğru parolayı nasıl belirleyeceğinizi öğrenin.
type: docs
weight: 30
url: /tr/net/programming-with-security-and-signatures/determine-correct-password/
---
Bu öğreticide, Aspose.PDF for .NET kullanarak PDF dosyasında doğru parolayı belirleme sürecinde size yol göstereceğiz. Bu özellik, bir PDF dosyasının parola korumalı olup olmadığını kontrol etmenizi ve önceden tanımlanmış bir listeden doğru parolayı bulmanızı sağlar.

## 1. Adım: Önkoşullar

Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

- C# programlama dili hakkında temel bilgi
- Visual Studio'yu makinenize yükleme
- .NET için Aspose.PDF kitaplığı kurulu

## 2. Adım: Ortam kurulumu

Başlamak için, geliştirme ortamınızı kurmak üzere şu adımları izleyin:

1. Visual Studio'yu açın ve yeni bir C# projesi oluşturun.
2. Gerekli ad alanlarını kod dosyanıza aktarın:

```csharp
using Aspose.Pdf;
```

## 3. Adım: Kaynak PDF dosyası yükleniyor

İlk adım, doğrulamak istediğiniz kaynak PDF dosyasını yüklemektir. Bu örnekte, belirtilen dizinde "IsPasswordProtected.pdf" adlı bir PDF dosyanız olduğunu varsayıyoruz.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
```

Yer tutucuları, PDF dosyanızın gerçek konumlarıyla değiştirdiğinizden emin olun.

## 4. Adım: Kaynak PDF Şifrelemesini Belirleyin

 Kaynak PDF dosyasını yükledikten sonra, bunun şifrelenip şifrelenmediğini belirleyebilirsiniz.`IsEncrypted` yöntemi`PdfFileInfo` nesne.

```csharp
Console.WriteLine("The file is password protected: " + info.IsEncrypted);
```

Bu ifade, PDF dosyasının parola korumalı olup olmadığını gösterir.

## 5. Adım: Doğru şifreyi bulma

Ardından, önceden tanımlanmış bir parola listesi kullanarak doğru parolayı arayacağız. Listedeki her şifreyi gözden geçiriyoruz ve PDF belgesini bu şifreyle yüklemeye çalışıyoruz.

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

Bu döngü, listeden geçen her kelimeyi test eder. Parola doğruysa belgedeki sayfa sayısı görüntülenir. Aksi takdirde, şifrenin doğru olmadığını belirten bir mesaj görüntülenir.


### Aspose.PDF for .NET kullanarak Doğru Parolayı Belirlemek için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";            
// Kaynak PDF dosyasını yükle
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
//Kaynak PDF'nin şifrelenip şifrelenmediğini belirleme
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

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF dosyası için doğru parolayı başarıyla belirlediniz. Bu eğitim, dosya şifrelemenin doğrulanmasından önceden tanımlanmış bir listeden doğru parolanın bulunmasına kadar adım adım süreci kapsıyordu. Artık PDF dosyalarınızın doğru şifresini kontrol etmek ve bulmak için bu özelliği kullanabilirsiniz.

### PDF dosyasında doğru şifreyi belirlemek için SSS

#### S: Bu eğitimin amacı nedir?

Y: Bu eğitim, Aspose.PDF for .NET kullanarak bir PDF dosyası için doğru parolayı belirleme sürecinde size rehberlik etmeyi amaçlamaktadır. Bu özellik, bir PDF dosyasının parola korumalı olup olmadığını kontrol etmenize ve önceden tanımlanmış bir listeden doğru parolayı bulmaya çalışmanıza olanak tanır.

#### S: Başlamadan önce hangi ön koşullar gereklidir?

C: Başlamadan önce, C# programlama dilini temel düzeyde anladığınızdan, makinenizde Visual Studio'nun kurulu olduğundan ve Aspose.PDF kitaplığının .NET için kurulu olduğundan emin olun.

#### S: Geliştirme ortamını nasıl kurarım?

Y: Visual Studio'da yeni bir C# projesi oluşturmak ve gerekli ad alanlarını içeri aktarmak dahil olmak üzere, geliştirme ortamınızı ayarlamak için sağlanan adımları izleyin.

#### S: Bir PDF dosyasının şifrelenip şifrelenmediğini nasıl anlarım?

 C: Şunu kullanın:`PdfFileInfo` kaynak PDF dosyasını bağlamak için sınıf. Ardından,`IsEncrypted`PDF dosyasının parola korumalı olup olmadığını belirleme özelliği.

#### S: Bir PDF dosyası için doğru şifreyi nasıl bulabilirim?

Y: PDF dosyasının şifreli olduğunu belirledikten sonra, önceden tanımlanmış bir parola listesi kullanarak doğru parolayı bulmaya çalışabilirsiniz. Sağlanan örnek kod, listede nasıl dolaşılacağını, her parolanın nasıl deneneceğini ve parolanın doğru olup olmadığının nasıl belirleneceğini gösterir.

#### S: Doğru parola bulunursa ne olur?

Y: Doğru parola bulunursa, örnek kod, PDF belgesindeki sayfa sayısını görüntüler.

#### S: Parola doğru değilse ne olur?

 A: Parola doğru değilse, örnek kod`InvalidPasswordException` ve parolanın doğru olmadığını belirten bir mesaj görüntüler.

#### S: Farklı bir parola listesi kullanabilir miyim?

 A: Evet, değiştirebilirsiniz`passwords` test etmek istediğiniz parolaları eklemek için örnek koddaki dizi.

#### S: Parolanın başarıyla belirlendiğini nasıl bilebilirim?

C: Örnek kod, PDF belgesini bir parolayla başarıyla yükler ve sayfa sayısını görüntülerse, bu, doğru parolanın belirlendiği anlamına gelir.

#### S: Test ederken şifrelerimin güvenliğini nasıl sağlayabilirim?

Y: Önceden tanımlanmış bir parola listesi kullanırken dikkatli olun ve test amacıyla hassas veya gizli parolalar kullanmaktan kaçının. Ayrıca, uygulamanızı dağıtmadan önce test kodunu kaldırın veya değiştirin.