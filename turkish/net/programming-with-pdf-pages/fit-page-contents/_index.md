---
title: Sayfa İçeriğini Sığdır
linktitle: Sayfa İçeriğini Sığdır
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF sayfa içeriğini ayarlamak için ayrıntılı adım adım kılavuz. Kolay uygulama ve ödüllendirici sonuç.
type: docs
weight: 50
url: /tr/net/programming-with-pdf-pages/fit-page-contents/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak PDF sayfa içeriğini ayarlama sürecini adım adım anlatacağız. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sağlayacağız. Bu eğitimin sonunda, Aspose.PDF for .NET kullanarak PDF sayfalarının içeriğini nasıl ayarlayacağınızı öğreneceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dili hakkında temel bilgi
- Aspose.PDF for .NET geliştirme ortamınızda yüklü

## 1. Adım: Belge dizinini tanımlayın
Öncelikle, belgeler dizininize giden yolu ayarlamanız gerekir. Bu, giriş PDF dosyanızın bulunduğu konumdur. "BELGELER DİZİNİNİZİ" uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: PDF belgesini yükleyin
 Ardından, PDF belgesini kullanarak yükleyebilirsiniz.`Document` Aspose.PDF sınıfı. Giriş PDF dosyasının doğru yolunu belirttiğinizden emin olun.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 3. Adım: Sayfa içeriğini ayarlayın
Artık belgenin tüm sayfaları arasında geçiş yapabilir ve her sayfanın içeriğini ortam kutusunun boyutuna göre ayarlayabilirsiniz. Verilen örnekte, aynı yüksekliği koruyarak yatay modda (yatay) oluşturmak için sayfanın genişliğini ayarlıyoruz. Yeni genişlik, ortam kutusunun en boy oranına göre hesaplanır.

```csharp
foreach(Page page in doc.Pages)
{
     Rectangle r = page.MediaBox;
     double newHeight = r.Height;
     double newWidth = r.Height * r.Height / r.Width;
}
```

### Aspose.PDF for .NET kullanan Sayfa İçeriklerini Sığdırmak için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Rectangle r = page.MediaBox;
	// Yeni yükseklik aynı
	double newHeight = r.Height;
	// Yönlendirmeyi yatay yapmak için yeni genişlik orantılı olarak genişletildi
	// (önceki yönlendirmenin portre olduğunu varsayıyoruz)
	double newWidth = r.Height * r.Height / r.Width;
}          

```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kullanarak PDF sayfa içeriğini nasıl ayarlayacağımızı öğrendik. Yukarıda özetlenen adımları izleyerek, bu işlevi kendi projelerinize kolayca uygulayabilirsiniz. PDF dosyalarıyla çalışmaya yönelik diğer yararlı özellikleri keşfetmek için Aspose.PDF belgelerini daha fazla keşfetmekten çekinmeyin.
