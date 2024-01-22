---
title: Sayfa İçeriklerini PDF Dosyasına Sığdır
linktitle: Sayfa İçeriklerini PDF Dosyasına Sığdır
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF dosyasındaki sayfa içeriklerini ayarlamak için ayrıntılı adım adım kılavuz. Kolay uygulama ve ödüllendirici sonuç.
type: docs
weight: 50
url: /tr/net/programming-with-pdf-pages/fit-page-contents/
---
Bu eğitimde, Aspose.PDF for .NET'i kullanarak PDF dosyasındaki sayfa içeriğini ayarlamak için size adım adım yol göstereceğiz. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sunacağız. Bu eğitimin sonunda Aspose.PDF for .NET kullanarak PDF sayfalarının içeriğini nasıl ayarlayacağınızı öğreneceksiniz.

## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dili hakkında temel bilgi
- Aspose.PDF for .NET, geliştirme ortamınızda yüklü

## 1. Adım: Belge dizinini tanımlayın
Öncelikle belgeler dizininizin yolunu ayarlamanız gerekir. Bu, giriş PDF dosyanızın bulunduğu konumdur. "BELGELERİNİZ DİZİNİ"ni uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: PDF belgesini yükleyin
 Daha sonra PDF belgesini kullanarak yükleyebilirsiniz.`Document` Aspose.PDF sınıfı. Giriş PDF dosyasının doğru yolunu belirttiğinizden emin olun.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 3. Adım: Sayfa içeriğini ayarlayın
Artık belgenin tüm sayfaları arasında geçiş yapabilir ve her sayfanın içeriğini medya kutusunun boyutuna göre ayarlayabilirsiniz. Verilen örnekte, sayfanın genişliğini aynı yüksekliği koruyarak yatay modda (manzara) oluşturacak şekilde ayarlıyoruz. Yeni genişlik, medya kutusunun en boy oranına göre hesaplanır.

```csharp
foreach(Page page in doc.Pages)
{
     Rectangle r = page.MediaBox;
     double newHeight = r.Height;
     double newWidth = r.Height * r.Height / r.Width;
}
```

### Aspose.PDF for .NET kullanan Fit Page Contents için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Rectangle r = page.MediaBox;
	// Yeni yükseklik aynı
	double newHeight = r.Height;
	// Yönlendirmeyi yatay hale getirmek için yeni genişlik orantılı olarak genişletilir
	// (önceki yönlendirmenin dikey olduğunu varsayıyoruz)
	double newWidth = r.Height * r.Height / r.Width;
}          

```

## Çözüm
Bu eğitimde Aspose.PDF for .NET kullanarak PDF sayfa içeriğini nasıl ayarlayacağımızı öğrendik. Yukarıda özetlenen adımları takip ederek bu işlevselliği kendi projelerinizde kolaylıkla uygulayabilirsiniz. PDF dosyalarıyla çalışmaya yönelik diğer kullanışlı özellikleri keşfetmek için Aspose.PDF belgelerini daha ayrıntılı olarak incelemekten çekinmeyin.

### PDF dosyasındaki sayfa içeriklerine uygun SSS'ler

#### S: PDF sayfaları bağlamında "medya kutusu" neyi temsil eder?

C: PDF sayfaları bağlamında "medya kutusu", sayfa içeriğinin fiziksel boyutlarını tanımlayan sınırlayıcı kutuyu temsil eder. PDF belgesindeki sayfa içeriğinin genişliğini, yüksekliğini ve konumunu tanımlar.

#### S: Sağlanan C# kaynak kodu sayfa içeriğini nasıl ayarlar?

C: Sağlanan C# kaynak kodu, aynı yüksekliği korurken yatay modda görünmesini sağlamak için her sayfanın genişliğini yeniden boyutlandırarak sayfa içeriğini ayarlar. Yeni genişlik, medya kutusunun en boy oranına göre hesaplanır ve içeriğin orijinal oranlarını koruması sağlanır.

#### S: Sayfa içeriğini belirli bir boyuta veya en boy oranına uyacak şekilde ayarlayabilir miyim?

C: Evet, sağlanan C# kaynak kodundaki hesaplamayı değiştirerek sayfa içeriğini belirli bir boyuta veya en boy oranına uyacak şekilde ayarlayabilirsiniz. Örneğin sayfa içeriğini sabit bir boyuta sığdırmak istiyorsanız (örn. 8,5 x 11 inç), yeni genişlik ve yüksekliği buna göre hesaplayabilirsiniz.

#### S: Sayfa boyutunu ayarladıktan sonra sayfadaki içeriğe ne olacak?

C: Sağlanan C# kaynak kodunu kullanarak sayfa boyutunu ayarladıktan sonra sayfadaki içerik orantılı olarak yeniden boyutlandırılacaktır. Orijinal içeriğin en boy oranı yeni en boy oranından önemli ölçüde farklıysa içerik uzatılmış veya sıkıştırılmış görünebilir.

#### S: PDF belgesindeki tüm sayfalar yerine belirli sayfaların içeriğini ayarlayabilir miyim?

C: Evet, PDF belgesindeki tüm sayfalar yerine belirli sayfaların içeriğini ayarlayabilirsiniz. Sağlanan C# kaynak kodunda "foreach" döngüsü belgedeki tüm sayfalar boyunca yinelenir. Belirli sayfaların içeriğini ayarlamak için yalnızca istediğiniz sayfaları hedeflemek amacıyla döngü içindeki koşullu ifadeleri kullanabilirsiniz.