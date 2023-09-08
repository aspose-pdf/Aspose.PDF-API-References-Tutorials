---
title: Yönü Değiştir
linktitle: Yönü Değiştir
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile bir PDF'nin sayfa yönünü değiştirmek için adım adım kılavuz. Takip edilmesi ve projelerinizde uygulanması kolaydır.
type: docs
weight: 10
url: /tr/net/programming-with-pdf-pages/change-orientation/
---
Bu eğitimde, Aspose.PDF for .NET'i kullanarak bir PDF belgesinin sayfa yönünü değiştirme işlemini adım adım anlatacağız. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sunacağız. Bu eğitimin sonunda Aspose.PDF for .NET'i kullanarak PDF belgelerinizin sayfa yönünü nasıl değiştireceğinizi öğreneceksiniz.

## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- C# programlama dili hakkında temel bilgi
- Aspose.PDF for .NET, geliştirme ortamınızda yüklü

## 1. Adım: Belge dizinini tanımlayın
Öncelikle belgeler dizininizin yolunu ayarlamanız gerekir. Bu, giriş PDF dosyanızın bulunduğu ve değiştirilen çıktı PDF dosyanızı kaydetmek istediğiniz konumdur. "BELGELERİNİZ DİZİNİ"ni uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: PDF belgesini yükleyin
 Daha sonra PDF belgesini giriş dosyasından aşağıdaki komutu kullanarak yükleyebilirsiniz:`Document` Aspose.PDF sınıfı. PDF dosyasının doğru yolunu belirttiğinizden emin olun.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 3. Adım: Sayfa yönünü değiştirin
Şimdi belgenin her sayfasını inceleyeceğiz ve yönünü değiştireceğiz. Her sayfa için medya kutusunun boyutlarını değiştiriyoruz (`MediaBox`) genişliği ve yüksekliği değiştirerek medya kutusunun koordinatlarını sayfanın konumunu koruyacak şekilde ayarlıyoruz. Son olarak sayfa dönüşünü 90 dereceye ayarlıyoruz.

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
 Son olarak, değiştirilen PDF belgesini aşağıdaki komutu kullanarak bir çıktı dosyasına kaydedebilirsiniz:`Save()` yöntemi`Document`sınıf. Doğru yolu ve dosya adını belirttiğinizden emin olun.

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
	// Değişen sayfa boyutunu telafi etmek için sayfayı yukarıya taşımamız gerekiyor
	// (sayfanın alt kenarı 0,0 olup bilgiler genellikle
	// Sayfanın en üstünde. Bu yüzden aradaki fark üzerinde sevgilinin kenarını yukarı kaydırıyoruz
	// Eski ve yeni yükseklik.
	double newLLY = r.LLY + (r.Height - newHeight);
	page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Bazen CropBox'u da ayarlamamız gerekir (eğer orijinal dosyada ayarlanmışsa)
	page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Sayfanın Döndürme açısının ayarlanması
	page.Rotate = Rotation.on90;
}
dataDir = dataDir + "ChangeOrientation_out.pdf";
// Çıkış dosyasını kaydet
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);

```

## Çözüm
Bu eğitimde Aspose.PDF for .NET kullanarak bir PDF belgesinin sayfa yönünü nasıl değiştireceğimizi öğrendik. Yukarıda özetlenen adımları takip ederek bu işlevselliği kendi projelerinizde kolaylıkla uygulayabilirsiniz. PDF dosyalarıyla çalışmaya yönelik diğer kullanışlı özellikleri keşfetmek için Aspose.PDF belgelerini daha ayrıntılı olarak incelemekten çekinmeyin.

### SSS'ler

#### S: Bir PDF belgesinde sayfa yönünü değiştirmenin amacı nedir?

C: Bir PDF belgesinde sayfa yönünü değiştirmek, sayfanın içeriğini 90 derece döndürmenize olanak tanır. Bu, orijinal içeriğin dikey moddan yatay moda veya tam tersi gibi farklı bir yönde görüntülenmesi veya yazdırılması gereken senaryolarda yararlı olabilir.

#### S: PDF belgesindeki belirli sayfaların yönünü değiştirebilir miyim?

 C: Evet, PDF belgesindeki belirli sayfaların yönünü değiştirebilirsiniz. Sağlanan C# kaynak kodunda,`foreach` döngü belgenin her sayfasından geçmek ve yönünü değiştirmek için kullanılır. Yalnızca belirli sayfaların yönünü değiştirmek istiyorsanız döngüyü, bu sayfaları sayfa numaralarına veya diğer ölçütlere göre hedefleyecek şekilde değiştirebilirsiniz.

#### S: Sayfa yönünü değiştirmek sayfadaki içeriğin düzenini etkiler mi?

C: Evet, sayfa yönünü değiştirmek sayfadaki içeriğin düzenini etkileyecektir. İçerik 90 derece döndürülecek ve sayfanın genişliği ve yüksekliği değiştirilecektir. Bunun sonucunda içeriğin sayfadaki yerleşimi ve hizalaması değişebilir.

#### S: Sayfayı 90 dereceden farklı bir açıyla döndürebilir miyim?

 C: Sağlanan C# kaynak kodunda sayfa döndürme, kullanılarak 90 dereceye ayarlanmıştır.`page.Rotate = Rotate.on90;` . Ancak gerekirse dönüş açısını başka değerlere değiştirebilirsiniz. Örneğin şunları kullanabilirsiniz:`Rotate.on180` sayfayı 180 derece döndürmek veya`Rotate.on270` 270 derece döndürmek için.

#### S: Yönü değiştirdikten sonra taşan sayfa içeriğini nasıl halledebilirim?

C: Sayfa yönünü değiştirirken sayfanın boyutları değişebilir, bu da içerik taşmasına neden olabilir. Bunu halletmek için sayfadaki içeriğin düzenini ve biçimlendirmesini ayarlamanız gerekebilir. Oryantasyon değişikliğinden sonra sayfa içeriğinin düzgün şekilde sığmasını sağlamak için öğeleri yeniden boyutlandırma, kenar boşluklarını ayarlama veya içeriği yeniden düzenleme gibi Aspose.PDF for .NET tarafından sağlanan özellikleri kullanabilirsiniz.