---
title: Yönelimi Değiştir
linktitle: Yönelimi Değiştir
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF'in sayfa yönünü değiştirmek için adım adım kılavuz. Projelerinizde takip etmesi ve uygulaması kolaydır.
type: docs
weight: 10
url: /tr/net/programming-with-pdf-pages/change-orientation/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesinin sayfa yönünü değiştirmek için adım adım süreci adım adım anlatacağız. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği kendi projelerinizde anlamanıza ve uygulamanıza yardımcı olacak kapsamlı bir kılavuz sunacağız. Bu eğitimin sonunda, Aspose.PDF for .NET kullanarak PDF belgelerinizin sayfa yönünü nasıl değiştireceğinizi öğreneceksiniz.

## Ön koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dilinin temel bilgisi
- Geliştirme ortamınıza .NET için Aspose.PDF yüklendi

## Adım 1: Belge dizinini tanımlayın
Öncelikle, belgeler dizininize giden yolu ayarlamanız gerekir. Bu, giriş PDF dosyanızın bulunduğu ve değiştirilmiş çıktı PDF dosyanızı kaydetmek istediğiniz konumdur. "YOUR DOCUMENTS DIRECTORY" ifadesini uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: PDF belgesini yükleyin
 Daha sonra giriş dosyasından PDF belgesini yükleyebilirsiniz.`Document` Aspose.PDF sınıfı. PDF dosyasına doğru yolu belirttiğinizden emin olun.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Adım 3: Sayfa yönünü değiştirin
Şimdi belgenin her sayfasını inceleyip yönünü değiştireceğiz. Her sayfa için medya kutusunun boyutlarını değiştiriyoruz (`MediaBox`) genişlik ve yüksekliği değiştirerek, ardından sayfanın konumunu korumak için medya kutusunun koordinatlarını ayarlıyoruz. Son olarak, sayfa dönüşünü 90 dereceye ayarlıyoruz.

```csharp
foreach(Page page in doc.Pages)
{
Aspose.Pdf.Rectangle r = page.MediaBox;
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page. Rotate = Rotate. on90;
}
```

## Adım 4: Değiştirilen PDF belgesini kaydedin
 Son olarak, değiştirilen PDF belgesini bir çıktı dosyasına kaydetmek için şunu kullanabilirsiniz:`Save()` yöntemi`Document`sınıf. Doğru yolu ve dosya adını belirttiğinizden emin olun.

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
```

### .NET için Aspose.PDF kullanarak Yönlendirmeyi Değiştirme için örnek kaynak kodu 

```csharp

// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Aspose.Pdf.Rectangle r = page.MediaBox;
	double newHeight = r.Width;
	double newWidth = r.Height;
	double newLLX = r.LLX;
	// Değişen sayfa boyutunu telafi etmek için sayfayı yukarı taşımalıyız
	// (sayfanın alt kenarı 0,0'dır ve bilgiler genellikle sayfadan yerleştirilir.
	// Sayfanın üstü. Bu yüzden sevgili kenarını farklar arasında yukarıya taşıyoruz
	// Eski ve yeni yükseklik.
	double newLLY = r.LLY + (r.Height - newHeight);
	page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Bazen CropBox'ı da ayarlamamız gerekir (eğer orijinal dosyada ayarlanmışsa)
	page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Sayfanın Dönme Açısını Ayarlama
	page.Rotate = Rotation.on90;
}
dataDir = dataDir + "ChangeOrientation_out.pdf";
// Çıktı dosyasını kaydet
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);

```

## Çözüm
Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesinin sayfa yönünü nasıl değiştireceğinizi öğrendik. Yukarıda özetlenen adımları izleyerek, bu işlevselliği kendi projelerinizde kolayca uygulayabilirsiniz. PDF dosyalarıyla çalışmak için diğer yararlı özellikleri keşfetmek üzere Aspose.PDF belgelerini daha fazla incelemekten çekinmeyin.

### SSS

#### S: PDF belgesinde sayfa yönünü değiştirmenin amacı nedir?

A: Bir PDF belgesinde sayfa yönünü değiştirmek, sayfanın içeriğini 90 derece döndürmenize olanak tanır. Bu, orijinal içeriğin farklı bir yönde görüntülenmesi veya yazdırılması gereken senaryolarda, örneğin portre modundan manzara moduna veya tam tersine geçişte yararlı olabilir.

#### S: PDF belgesinde belirli sayfaların yönünü değiştirebilir miyim?

 A: Evet, PDF belgesindeki belirli sayfaların yönünü değiştirebilirsiniz. Sağlanan C# kaynak kodunda,`foreach` döngü, belgenin her sayfasını dolaşıp yönünü değiştirmek için kullanılır. Yalnızca belirli sayfaların yönünü değiştirmek istiyorsanız, döngüyü sayfa numaralarına veya diğer ölçütlere göre bu sayfaları hedefleyecek şekilde değiştirebilirsiniz.

#### S: Sayfa yönlendirmesini değiştirmek sayfadaki içeriğin düzenini etkiler mi?

C: Evet, sayfa yönlendirmesini değiştirmek sayfadaki içeriğin düzenini etkileyecektir. İçerik 90 derece döndürülecek ve sayfanın genişliği ve yüksekliği yer değiştirecektir. Sonuç olarak, sayfadaki içeriğin yerleşimi ve hizalaması değişebilir.

#### S: Sayfayı 90 dereceden farklı bir açıyla döndürebilir miyim?

 A: Sağlanan C# kaynak kodunda, sayfa dönüşü 90 dereceye ayarlanmıştır.`page.Rotate = Rotate.on90;` Ancak, gerekirse dönüş açısını başka değerlere değiştirebilirsiniz. Örneğin, şunu kullanabilirsiniz:`Rotate.on180` sayfayı 180 derece döndürmek veya`Rotate.on270` 270 derece döndürmek için.

#### S: Sayfanın yönünü değiştirdikten sonra taşan sayfa içeriğini nasıl halledebilirim?

A: Sayfa yönlendirmesi değiştirildiğinde, sayfanın boyutları değişebilir ve bu da içerik taşmasına neden olabilir. Bunu halletmek için sayfadaki içeriğin düzenini ve biçimlendirmesini ayarlamanız gerekebilir. Yönlendirme değişikliğinden sonra sayfa içeriğinin düzgün bir şekilde sığmasını sağlamak için Aspose.PDF for .NET tarafından sağlanan öğeleri yeniden boyutlandırma, kenar boşluklarını ayarlama veya içeriği yeniden düzenleme gibi özellikleri kullanabilirsiniz.