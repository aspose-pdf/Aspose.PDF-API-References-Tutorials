---
title: PDF Dosyasında Küçük Resim Görüntüleri Oluşturun
linktitle: PDF Dosyasında Küçük Resim Görüntüleri Oluşturun
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasında kolayca küçük resim görüntüsü oluşturun.
type: docs
weight: 100
url: /tr/net/programming-with-images/create-thumbnail-images/
---
Bu kılavuz, .NET için Aspose.PDF kullanarak PDF dosyasında küçük resim görüntüsünün nasıl oluşturulacağını adım adım gösterecektir. Ortamınızı önceden ayarladığınızdan ve aşağıdaki adımları izlediğinizden emin olun:

## Adım 1: Belge dizinini tanımlayın

Başlamadan önce, belgeler için doğru dizini ayarladığınızdan emin olun. Değiştir`"YOUR DOCUMENT DIRECTORY"` PDF dosyalarınızın bulunduğu dizinin yolunu içeren kodda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Bir dizindeki tüm PDF dosyalarının adlarını alın

 Bu adımda, C# kullanarak belirtilen dizinde bulunan tüm PDF dosyalarının adlarını alacağız`Directory`sınıf. Dosyalar bir dizi dizede saklanacaktır.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## Adım 3: Tüm PDF dosyalarına ve sayfalarına göz atın

 Bu adımda, resim küçük resimleri oluşturmak için tüm PDF dosyalarını ve sayfalarını inceleyeceğiz.`for` tüm dosyalar arasında yineleme yapmak için döngü.

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     // PDF belgesini açın
     Document pdfDocument = new Document(fileEntries[counter]);
    
     // Belgenin tüm sayfalarını inceleyin
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         // Küçük resim görüntüsünü kaydetmek için bir akış oluşturun
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             //Bir Resolution nesnesi oluşturun
             Resolution resolution = new Resolution(300);
            
             // Belirtilen niteliklere sahip bir JPEG aygıtı oluşturun
             JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
            
             // Belirli bir sayfayı dönüştürün ve görüntüyü akışa kaydedin
             jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
            
             // Akışı kapat
             imageStream.Close();
         }
     }
}
```

### .NET için Aspose.PDF kullanarak Küçük Resim Görüntüleri Oluşturmak için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belirli bir dizindeki tüm PDF dosyalarının adlarını alın
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
// Dizideki tüm dosya girişlerini yinele
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
			//JpegDevice jpegDevice = new JpegDevice(500, 700, çözünürlük, 100);
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

Tebrikler! Aspose.PDF for .NET kullanarak PDF dosyalarından resim küçük resimleri başarıyla oluşturdunuz. Resim küçük resimleri belirtilen dizine kaydedilir. Artık bu küçük resimleri kullanarak PDF dosyalarınızın görsel önizlemesini görüntüleyebilirsiniz.

### PDF dosyasında küçük resim görüntüleri oluşturmaya ilişkin SSS

#### S: Aspose.PDF for .NET kullanarak PDF dosyalarından küçük resim görüntüleri oluşturmanın amacı nedir?

A: PDF dosyalarından küçük resim görüntüleri oluşturmak, PDF'deki her sayfanın küçük görsel önizlemelerini oluşturmanıza olanak tanır; bu, içerikte hızlı bir şekilde önizleme yapmak ve gezinmek için yararlı olabilir.

#### S: Aspose.PDF for .NET, PDF dosyalarından küçük resim görüntüleri oluşturmayı nasıl kolaylaştırır?

 A: Aspose.PDF for .NET, PDF belgelerini açmak, sayfalarında gezinmek, küçük resim görüntüleri oluşturmak ve bunları belirtilen bir dizine kaydetmek için adım adım bir süreç sağlar.`JpegDevice` sınıf.

#### S: Küçük resim oluşturmaya başlamadan önce belge dizinini tanımlamak neden önemlidir?

A: Belge dizinini belirtmek, PDF dosyalarının doğru bir şekilde konumlandırılmasını ve ortaya çıkan küçük resim görüntülerinin istenen çıktı yoluna kaydedilmesini sağlar.

####  S: Nasıl?`Document` class in Aspose.PDF for .NET help in the creation of thumbnail images?

 A:`Document` sınıfı PDF belgelerini açmanıza ve düzenlemenize olanak tanır. Bu durumda, küçük resim görüntülerinin oluşturulacağı PDF dosyalarını yüklemek için kullanılır.

####  S: Rolü nedir?`JpegDevice` class play in the creation of thumbnail images?

 A:`JpegDevice` sınıf, PDF sayfalarını küçük resim olarak kullanılan JPEG görüntülerine dönüştürmekten sorumludur. Genişlik, yükseklik, çözünürlük ve kalite gibi nitelikleri belirtmenize olanak tanır.

#### S: PDF belgesinin her sayfası ayrı bir küçük resim görüntüsüne nasıl dönüştürülür?

 A: İç içe geçmiş`for` döngü, her PDF dosyası ve sayfalarında yineleme yapmak için kullanılır. Her sayfa için, belirtilen niteliklere sahip bir JPEG aygıtı oluşturulur ve`Process` Sayfanın küçük resim görüntüsüne dönüştürülmesi ve akışa kaydedilmesi için kullanılan yöntemdir.

#### S: Oluşturma işlemi sırasında ortaya çıkan küçük resim görüntülerinin çözünürlüğünü veya kalitesini ayarlayabilir miyim?

A: Evet, çözünürlük, genişlik, yükseklik ve kalite gibi nitelikleri yapılandırarak değiştirebilirsiniz.`JpegDevice` Her sayfayı dönüştürmeden önce nesne.

#### S: Oluşturulan küçük resim görüntülerini oluşturma işleminden sonra projelerimde veya uygulamalarımda nasıl kullanabilirim?

A: Ortaya çıkan küçük resim görüntüleri, PDF dosyalarının görsel önizlemesini sağlamak için kullanılabilir ve kullanıcıların içerikleri hızla tanımlamasına ve içerikler arasında gezinmesine yardımcı olur.

#### : Bu oluşturma süreci kullanılarak PDF dosyalarından oluşturulabilecek küçük resim sayısının bir sınırı var mıdır?

A: Oluşturulan küçük resim sayısı her PDF belgesindeki sayfa sayısına bağlıdır. Her sayfa ayrı bir küçük resim görüntüsüne dönüştürülecektir.