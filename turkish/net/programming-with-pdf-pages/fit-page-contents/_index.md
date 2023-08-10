---
title: Sayfa İçeriğini PDF Dosyasına Sığdır
linktitle: Sayfa İçeriğini PDF Dosyasına Sığdır
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki sayfa içeriklerini ayarlamak için ayrıntılı adım adım kılavuz. Kolay uygulama ve ödüllendirici sonuç.
type: docs
weight: 50
url: /tr/net/programming-with-pdf-pages/fit-page-contents/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak PDF dosyasındaki sayfa içeriklerini ayarlamak için size adım adım yol göstereceğiz. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sağlayacağız. Bu eğitimin sonunda, Aspose.PDF for .NET kullanarak PDF sayfalarının içeriğini nasıl ayarlayacağınızı öğreneceksiniz.

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

### PDF dosyasındaki sığdırma sayfası içerikleriyle ilgili SSS

#### S: "Medya kutusu", PDF sayfaları bağlamında neyi temsil eder?

C: PDF sayfaları bağlamında, "ortam kutusu", sayfa içeriğinin fiziksel boyutlarını tanımlayan sınırlayıcı kutuyu temsil eder. PDF belgesindeki sayfa içeriğinin genişliğini, yüksekliğini ve konumunu tanımlar.

#### S: Sağlanan C# kaynak kodu, sayfa içeriğini nasıl ayarlar?

A: Sağlanan C# kaynak kodu, aynı yüksekliği korurken yatay modda görünmesini sağlamak için her sayfanın genişliğini yeniden boyutlandırarak sayfa içeriğini ayarlar. Yeni genişlik, ortam kutusunun en boy oranına göre hesaplanır ve içeriğin orijinal oranlarını koruması sağlanır.

#### S: Sayfa içeriğini belirli bir boyuta veya en boy oranına uyacak şekilde ayarlayabilir miyim?

C: Evet, sağlanan C# kaynak kodundaki hesaplamayı değiştirerek sayfa içeriğini belirli bir boyuta veya en boy oranına sığacak şekilde ayarlayabilirsiniz. Örneğin, sayfa içeriğini sabit bir boyuta (örn. 8,5 x 11 inç) sığdırmak istiyorsanız, yeni genişlik ve yüksekliği buna göre hesaplayabilirsiniz.

#### S: Sayfa boyutunu ayarladıktan sonra sayfadaki içeriğe ne olacak?

A: Sağlanan C# kaynak kodunu kullanarak sayfa boyutunu ayarladıktan sonra, sayfadaki içerik orantılı olarak yeniden boyutlandırılacaktır. Orijinal içeriğin en boy oranı yeni en boy oranından önemli ölçüde farklıysa içerik uzatılmış veya sıkıştırılmış görünebilir.

#### S: PDF belgesindeki tüm sayfalar yerine belirli sayfaların içeriğini ayarlayabilir miyim?

C: Evet, PDF belgesindeki tüm sayfalar yerine belirli sayfaların içeriğini ayarlayabilirsiniz. Sağlanan C# kaynak kodunda, "foreach" döngüsü belgedeki tüm sayfaları yineler. Belirli sayfaların içeriğini ayarlamak için, yalnızca istenen sayfaları hedeflemek için döngü içindeki koşullu ifadeleri kullanabilirsiniz.