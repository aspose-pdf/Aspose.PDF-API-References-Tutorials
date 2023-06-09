---
title: Sayfalardan Görsellere
linktitle: Sayfalardan Görsellere
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile bir PDF belgesinin sayfalarını kolayca görüntülere dönüştürün.
type: docs
weight: 200
url: /tr/net/programming-with-images/pages-to-images/
---

Bu eğitimde, Aspose.PDF kitaplığını .NET kullanarak bir PDF belgesinin sayfalarını tek tek görüntülere dönüştürmeniz için size adım adım rehberlik edeceğiz. Sağlanan C# kaynak kodu, bir PDF belgesini nasıl açacağınızı, her sayfadan nasıl resim oluşturacağınızı ve bunları nasıl kaydedeceğinizi gösterir. Süreci derinlemesine anlamanıza yardımcı olmak için her adımı ayrıntılı olarak açıklayacağız.

## Önkoşullar
Başlamadan önce, aşağıdaki öğelere sahip olduğunuzdan emin olun:
- C# programlama dili hakkında temel bilgi.
- Projenizde yüklü olan .NET için Aspose.PDF kitaplığı.
- Görüntülere dönüştürmek istediğiniz bir PDF belgesi.

## Adım 1: Proje Kurulumu
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. Projenizde Aspose.PDF kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın
C# dosyanızın başında, Aspose.PDF sınıflarına ve yöntemlerine erişmek için gereken ad alanlarını içe aktarın. İşte bir örnek :
```csharp
using System;
using Aspose.Pdf;
using System.IO;
```

## 3. Adım: Değişkenleri ve yolları başlatma
Dönüşümü gerçekleştirmeden önce gerekli değişkenleri ve yolları yapılandırmamız gerekiyor.
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` belgeler dizininize giden gerçek yolla.

## 4. Adım: Sayfaları Görüntülere Dönüştürme
PDF belge sayfalarını görüntülere dönüştürmek için şu adımları izleyin:
1.  kullanarak PDF belgesini açın.`Document` sınıf.
```csharp
Document pdfDocument = new Document(dataDir + "PagesToImages.pdf");
```
2.  kullanarak belgenin her sayfasını yineleyin.`for` döngü.
```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
//Her sayfayı bir resme dönüştürmek için kod
}
```
3. Döngünün içinde, kaydedilecek her görüntü için bir dosya akışı oluşturun.
```csharp
using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".jpg", FileMode.Create))
{
// Sayfayı bir resme dönüştürmek için kod
}
```
4.  İçinde`using` bloke et, oluştur`Resolution` görüntü çözünürlüğünü ayarlamak için nesne.
```csharp
Resolution resolution = new Resolution(300);
```
5.  Oluşturmak`JpegDevice` belirtilen çözünürlüğü ve kaliteyi kullanarak nesne.
```csharp
JpegDevice jpegDevice = new JpegDevice(resolution, 100);
```
6.  Kullan`Process` yöntemi`jpegDevice` belirli bir sayfayı bir görüntüye dönüştürmek ve görüntüyü akışa kaydetmek için nesne.
```csharp
jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
```
7. Görüntü akışını kapatın.
```csharp
imageStream.Close();
```
8. Belgenin her sayfası için bu adımları tekrarlayın.
9. İşlemin sonunda bir başarı mesajı görüntüleyin.
```csharp
Console.WriteLine("PDF pages converted to individual images successfully!");
```

### Aspose.PDF for .NET kullanan Pages To Images için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "PagesToImages.pdf");
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".jpg", FileMode.Create))
	{
		// Belirtilen özniteliklere sahip JPEG aygıtı oluştur
		// Genişlik, Yükseklik, Çözünürlük, Kalite
		// Kalite [0-100], 100 Maksimum
		// Çözünürlük nesnesi oluştur
		Resolution resolution = new Resolution(300);
		// JpegDevice jpegDevice = yeni JpegDevice(500, 700, çözünürlük, 100);
		JpegDevice jpegDevice = new JpegDevice(resolution, 100);
		// Belirli bir sayfayı dönüştürün ve görüntüyü akışa kaydedin
		jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// Akışı kapat
		imageStream.Close();
	}
}
System.Console.WriteLine("PDF pages are converted to individual images successfully!");
```

## Çözüm
Bu adım adım kılavuzu takip ederek, Aspose.PDF for .NET kitaplığını kullanarak bir PDF belgesinin sayfalarını ayrı ayrı görüntülere nasıl dönüştüreceğinizi öğrendiniz. Bu süreç, projeyi kurmayı, gerekli ad alanlarını içe aktarmayı, değişkenleri ve yolları başlatmayı ve sayfaları görüntülere dönüştürmeyi içerir. Artık bu kodu kendi projelerinize entegre edebilir ve özel ihtiyaçlarınıza uyacak şekilde değiştirebilirsiniz.