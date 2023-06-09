---
title: Küçük Resim Oluşturma
linktitle: Küçük Resim Oluşturma
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyalarından kolayca küçük resimler oluşturun.
type: docs
weight: 100
url: /tr/net/programming-with-images/create-thumbnail-images/
---

Bu kılavuz, Aspose.PDF for .NET kullanarak PDF dosyalarından küçük resimlerin nasıl oluşturulacağını adım adım gösterecek. Ortamınızı zaten kurduğunuzdan emin olun ve aşağıdaki adımları izleyin:

## 1. Adım: Belge dizinini tanımlayın

 Başlamadan önce, belgeler için doğru dizini ayarladığınızdan emin olun. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` PDF dosyalarınızı içeren dizinin yolunu içeren kodda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Bir dizindeki tüm PDF dosyalarının adlarını alın

 Bu adımda, belirtilen dizinde bulunan tüm PDF dosyalarının adlarını C# kullanarak alacağız.`Directory`sınıf. Dosyalar bir dizi dizide saklanacaktır.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## 3. Adım: Tüm PDF dosyalarına ve sayfalarına göz atın

 Bu adımda, küçük resimler oluşturmak için tüm PDF dosyalarını ve sayfalarını inceleyeceğiz. bir kullanacağız`for` tüm dosyalar arasında yineleme yapmak için döngü.

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     // PDF belgesini aç
     Document pdfDocument = new Document(fileEntries[counter]);
    
     // Belgenin tüm sayfalarını gözden geçirin
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         // Küçük resmi kaydetmek için bir akış oluşturun
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             // Çözünürlük nesnesi oluşturma
             Resolution resolution = new Resolution(300);
            
             // Belirtilen niteliklere sahip bir JPEG aygıtı oluşturun
             JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
            
             // Belirli bir sayfayı dönüştürün ve görüntüyü akışa kaydedin
             jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
            
             // akışı kapat
             imageStream.Close();
         }
     }
}
```

### Aspose.PDF for .NET kullanarak Küçük Resim Oluşturma için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belirli bir dizindeki tüm PDF dosyalarının adlarını alın
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
// Dizideki tüm dosya girişlerini yineleyin
for (int counter = 0; counter < fileEntries.Length; counter++)
{
	//Belgeyi aç
	Document pdfDocument = new Document(fileEntries[counter]);
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "\\Thumbanils" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
		{
			//Çözünürlük nesnesi oluştur
			Resolution resolution = new Resolution(300);
			//JpegDevice jpegDevice = yeni JpegDevice(500, 700, çözünürlük, 100);
			JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
			//Belirli bir sayfayı dönüştürün ve görüntüyü akışa kaydedin
			jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
			//Akışı kapat
			imageStream.Close();
		}
	}
}
System.Console.WriteLine("PDF pages are converted to thumbnails successfully!");
```

## Çözüm

Tebrikler! Aspose.PDF for .NET'i kullanarak PDF dosyalarından başarılı bir şekilde küçük resimler oluşturdunuz. Görüntü küçük resimleri belirtilen dizine kaydedilir. Artık bu küçük resimleri, PDF dosyalarınızın görsel bir önizlemesini görüntülemek için kullanabilirsiniz.