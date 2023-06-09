---
title: Ayrıcalıklar Belirle
linktitle: Ayrıcalıklar Belirle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyalarınız için erişim ayrıcalıklarını kolayca ayarlayın.
type: docs
weight: 100
url: /tr/net/programming-with-security-and-signatures/set-privileges/
---

PDF dosyaları için genellikle belirli erişim ayrıcalıkları ayarlamak gerekir. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu kullanarak erişim ayrıcalıklarını kolayca ayarlayabilirsiniz:

## 1. Adım: Gerekli kitaplıkları içe aktarın

Başlamadan önce, C# projeniz için gerekli kitaplıkları içe aktarmanız gerekir. İşte gerekli ithalat direktifleri:

```csharp
using Aspose.Pdf;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda, düzenlemek istediğiniz PDF dosyasını içeren klasörün yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` belgeler klasörünüzün gerçek yolu ile aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 3. Adım: Kaynak PDF dosyasını yükleyin

Şimdi kaynak PDF dosyasını aşağıdaki kodu kullanarak yükleyeceğiz:

```csharp
using (Document document = new Document(dataDir + "input.pdf"))
```

## 4. Adım: Erişim Ayrıcalıklarını Ayarlayın

 Bu adımda,`DocumentPrivilege` istenen erişim ayrıcalıklarını ayarlamak için nesne. Kullanarak tüm ayrıcalıklara kısıtlamalar uygulayabilirsiniz.`DocumentPrivilege.ForbidAll` . Örneğin, yalnızca ekran okumaya izin vermek istiyorsanız, ayarlayabilirsiniz.`AllowScreenReaders` ile`true`. İşte ilgili kod:

```csharp
DocumentPrivilege documentPrivilege = DocumentPrivilege.ForbidAll;
documentPrivilege.AllowScreenReaders = true;
```

## 5. Adım: Belgeyi şifreleyin ve kaydedin

 Son olarak, PDF belgesini kullanarak bir kullanıcı ve sahip parolasıyla şifreleyebiliriz.`Encrypt` ve istenen şifreleme algoritmasının belirtilmesi. Ardından güncellenen belgeyi kaydediyoruz. İşte ilgili kod:

```csharp
document.Encrypt("user", "owner", documentPrivilege, CryptoAlgorithm.AESx128, false);
document.Save(dataDir + "SetPrivileges_out.pdf");
```

### Aspose.PDF for .NET kullanarak Set Privileges için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Bir kaynak PDF dosyası yükleyin
using (Document document = new Document(dataDir + "input.pdf"))
{
	// Belge Ayrıcalıkları nesnesini Örnekle
	// Tüm ayrıcalıklara kısıtlamalar uygulayın
	DocumentPrivilege documentPrivilege = DocumentPrivilege.ForbidAll;
	// Yalnızca ekran okumaya izin ver
	documentPrivilege.AllowScreenReaders = true;
	// Dosyayı Kullanıcı ve Sahip parolasıyla şifreleyin.
	// Parolayı ayarlamanız gerekir, böylece kullanıcı dosyayı kullanıcı parolasıyla görüntülediğinde,
	//Yalnızca ekran okuma seçeneği etkin
	document.Encrypt("user", "owner", documentPrivilege, CryptoAlgorithm.AESx128, false);
	// Güncellenen belgeyi kaydet
	document.Save(dataDir + "SetPrivileges_out.pdf");
}
```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF belgesi için erişim ayrıcalıklarını ayarlamak için adım adım bir kılavuza sahipsiniz. Bu kodu, belirli kısıtlamalar uygulamak ve gerektiğinde PDF dosyalarınızı korumak için kullanabilirsiniz.

Gelişmiş PDF belge güvenliği ve erişim ayrıcalık yönetimi özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine baktığınızdan emin olun.