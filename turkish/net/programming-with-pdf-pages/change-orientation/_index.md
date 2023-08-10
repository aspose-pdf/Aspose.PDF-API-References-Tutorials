---
title: Yönü Değiştir
linktitle: Yönü Değiştir
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir PDF'nin sayfa yönünü değiştirmek için adım adım kılavuz. Takip etmesi ve projelerinizde uygulaması kolaydır.
type: docs
weight: 10
url: /tr/net/programming-with-pdf-pages/change-orientation/
---
Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF belgesinin sayfa yönünü değiştirmek için adım adım süreci size göstereceğiz. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sağlayacağız. Bu eğitimin sonunda, Aspose.PDF for .NET kullanarak PDF belgelerinizin sayfa yönünü nasıl değiştireceğinizi öğreneceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dili hakkında temel bilgi
- Aspose.PDF for .NET geliştirme ortamınızda yüklü

## 1. Adım: Belge dizinini tanımlayın
Öncelikle, belgeler dizininize giden yolu ayarlamanız gerekir. Bu, girdi PDF dosyanızın bulunduğu ve değiştirilmiş çıktı PDF dosyanızı kaydetmek istediğiniz konumdur. "BELGELER DİZİNİNİZİ" uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: PDF belgesini yükleyin
 Ardından, PDF belgesini giriş dosyasından yükleyebilirsiniz.`Document` Aspose.PDF sınıfı. PDF dosyasının doğru yolunu belirttiğinizden emin olun.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 3. Adım: Sayfa yönünü değiştirin
Şimdi belgenin her sayfasını inceleyeceğiz ve yönünü değiştireceğiz. Her sayfa için medya kutusunun boyutlarını değiştiriyoruz (`MediaBox`) genişliği ve yüksekliği değiştirerek, sayfanın konumunu korumak için medya kutusunun koordinatlarını ayarlıyoruz. Son olarak sayfa döndürmeyi 90 dereceye ayarladık.

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

## 4. Adım: Değiştirilen PDF belgesini kaydedin
 Son olarak, değiştirilmiş PDF belgesini kullanarak bir çıktı dosyasına kaydedebilirsiniz.`Save()` yöntemi`Document`sınıf. Doğru yolu ve dosya adını belirttiğinizden emin olun.

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Yön Değiştirme için örnek kaynak kodu 

```csharp

// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Aspose.Pdf.Rectangle r = page.MediaBox;
	double newHeight = r.Width;
	double newWidth = r.Height;
	double newLLX = r.LLX;
	// Değişen sayfa boyutunu telafi etmek için sayfayı yukarı taşımalıyız
	// (sayfanın alt kenarı 0,0'dır ve bilgiler genellikle
	// Sayfanın en üstünde. Bu nedenle, aralarındaki farkta sevgili kenarını yukarı taşıyoruz.
	// Eski ve yeni yükseklik.
	double newLLY = r.LLY + (r.Height - newHeight);
	page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Bazen CropBox'ı da ayarlamamız gerekir (eğer orijinal dosyada ayarlanmışsa)
	page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Sayfanın Dönme açısını ayarlama
	page.Rotate = Rotation.on90;
}
dataDir = dataDir + "ChangeOrientation_out.pdf";
// Çıktı dosyasını kaydet
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);

```

## Çözüm
Bu öğreticide, Aspose.PDF for .NET kullanarak bir PDF belgesinin sayfa yönünün nasıl değiştirileceğini öğrendik. Yukarıda özetlenen adımları izleyerek, bu işlevi kendi projelerinize kolayca uygulayabilirsiniz. PDF dosyalarıyla çalışmaya yönelik diğer yararlı özellikleri keşfetmek için Aspose.PDF belgelerini daha fazla keşfetmekten çekinmeyin.

### SSS

#### S: Bir PDF belgesinde sayfa yönünü değiştirmenin amacı nedir?

Y: Bir PDF belgesinde sayfa yönünü değiştirmek, sayfanın içeriğini 90 derece döndürmenize olanak tanır. Bu, orijinal içeriğin dikeyden yatay moda geçiş veya tam tersi gibi farklı bir yönde görüntülenmesi veya yazdırılması gereken senaryolarda yararlı olabilir.

#### S: PDF belgesindeki belirli sayfaların yönünü değiştirebilir miyim?

 C: Evet, PDF belgesindeki belirli sayfaların yönünü değiştirebilirsiniz. Sağlanan C# kaynak kodunda,`foreach` döngü, belgenin her sayfasından geçmek ve yönünü değiştirmek için kullanılır. Yalnızca belirli sayfaların yönünü değiştirmek istiyorsanız, bu sayfaları sayfa numaralarına veya diğer ölçütlere göre hedeflemek için döngüyü değiştirebilirsiniz.

#### S: Sayfa yönünü değiştirmek, sayfadaki içeriğin düzenini etkiler mi?

C: Evet, sayfa yönünün değiştirilmesi sayfadaki içeriğin düzenini etkiler. İçerik 90 derece döndürülecek ve sayfanın genişliği ve yüksekliği değiştirilecektir. Sonuç olarak, sayfadaki içeriğin yerleşimi ve hizalaması değişebilir.

#### S: Sayfayı 90 dereceden farklı bir açıyla döndürebilir miyim?

 A: Sağlanan C# kaynak kodunda, sayfa dönüşü kullanılarak 90 dereceye ayarlanmıştır.`page.Rotate = Rotate.on90;` . Ancak gerekirse dönüş açısını başka değerlerle değiştirebilirsiniz. Örneğin, kullanabilirsiniz`Rotate.on180` sayfayı 180 derece döndürmek için veya`Rotate.on270` 270 derece döndürmek için

#### S: Yönü değiştirdikten sonra taşan sayfa içeriğini nasıl ele alabilirim?

C: Sayfa yönünü değiştirirken, sayfanın boyutları değişebilir ve bu da içeriğin taşmasına neden olabilir. Bunu halletmek için, sayfadaki içeriğin düzenini ve biçimlendirmesini ayarlamanız gerekebilir. Aspose.PDF for .NET tarafından sağlanan, öğeleri yeniden boyutlandırma, kenar boşluklarını ayarlama veya içeriği yeniden düzenleme gibi özellikleri, yön değişikliğinden sonra sayfa içeriğinin düzgün bir şekilde sığmasını sağlamak için kullanabilirsiniz.