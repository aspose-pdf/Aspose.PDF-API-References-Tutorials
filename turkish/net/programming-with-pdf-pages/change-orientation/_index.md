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