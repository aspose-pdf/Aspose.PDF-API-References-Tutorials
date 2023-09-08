---
title: PDF Dosyasında Küçük Resim Görüntüleri Oluşturun
linktitle: PDF Dosyasında Küçük Resim Görüntüleri Oluşturun
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile PDF dosyasında kolayca küçük resim oluşturun.
type: docs
weight: 100
url: /tr/net/programming-with-images/create-thumbnail-images/
---
Bu kılavuz, Aspose.PDF for .NET kullanarak PDF dosyasında küçük resim görüntüsünün nasıl oluşturulacağını adım adım anlatacaktır. Ortamınızı zaten kurduğunuzdan emin olun ve aşağıdaki adımları izleyin:

## 1. Adım: Belge dizinini tanımlayın

 Başlamadan önce belgeler için doğru dizini ayarladığınızdan emin olun. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` PDF dosyalarınızı içeren dizinin yolunu içeren kodda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Bir dizindeki tüm PDF dosyalarının adlarını alın

 Bu adımda, C#'ın komutlarını kullanarak belirtilen dizinde bulunan tüm PDF dosyalarının adlarını alacağız.`Directory` sınıf. Dosyalar bir dizi dizide saklanacaktır.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## 3. Adım: Tüm PDF dosyalarına ve sayfalarına göz atın

 Bu adımda, görsel küçük resimleri oluşturmak için tüm PDF dosyalarını ve sayfalarını inceleyeceğiz. Bir kullanacağız`for` tüm dosyalar arasında yineleme yapmak için döngü.

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     //PDF belgesini açın
     Document pdfDocument = new Document(fileEntries[counter]);
    
     // Belgenin tüm sayfalarını inceleyin
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         // Küçük resim görüntüsünü kaydetmek için bir akış oluşturun
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             // Çözünürlük nesnesi oluşturma
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

### Aspose.PDF for .NET kullanarak Küçük Resim Görüntüleri Oluşturmak için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Belirli bir dizindeki tüm PDF dosyalarının adlarını alın
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

Tebrikler! Aspose.PDF for .NET'i kullanarak PDF dosyalarından görsel küçük resimlerini başarıyla oluşturdunuz. Görüntünün küçük resimleri belirtilen dizine kaydedilir. Artık PDF dosyalarınızın görsel bir önizlemesini görüntülemek için bu küçük resimleri kullanabilirsiniz.

### PDF dosyasında küçük resimler oluşturmaya ilişkin SSS'ler

#### S: Aspose.PDF for .NET kullanarak PDF dosyalarından küçük resimler oluşturmanın amacı nedir?

C: PDF dosyalarından küçük resimler oluşturmak, PDF'deki her sayfanın küçük görsel önizlemelerini oluşturmanıza olanak tanır; bu, içeriği hızlı bir şekilde önizlemek ve gezinmek için yararlı olabilir.

#### S: Aspose.PDF for .NET, PDF dosyalarından küçük resim oluşturmayı nasıl kolaylaştırır?

C: Aspose.PDF for .NET, PDF belgelerini açmak, sayfalarında yinelemek, küçük resimler oluşturmak ve bunları, PDF belgelerini kullanarak belirli bir dizine kaydetmek için adım adım bir süreç sağlar.`JpegDevice` sınıf.

#### S: Küçük resim görüntüleri oluşturmaya başlamadan önce belge dizinini tanımlamak neden önemlidir?

C: Belge dizininin belirtilmesi, PDF dosyalarının doğru şekilde konumlandırılmasını ve sonuçta ortaya çıkan küçük resimlerin istenen çıktı yoluna kaydedilmesini sağlar.

####  S: Nasıl`Document` class in Aspose.PDF for .NET help in the creation of thumbnail images?

 C:`Document` class, PDF belgelerini açmanıza ve değiştirmenize olanak tanır. Bu durumda küçük resimlerin oluşturulacağı PDF dosyalarını yüklemek için kullanılır.

####  S: Hangi rol`JpegDevice` class play in the creation of thumbnail images?

 C:`JpegDevice` sınıfı, PDF sayfalarını küçük resim görüntüleri olarak kullanılan JPEG görüntülerine dönüştürmekten sorumludur. Genişlik, yükseklik, çözünürlük ve kalite gibi nitelikleri belirtmenize olanak tanır.

#### S: PDF belgesinin her sayfası ayrı bir küçük resim görüntüsüne nasıl dönüştürülür?

 A: İç içe geçmiş bir`for`döngü, her PDF dosyası ve sayfaları arasında yineleme yapmak için kullanılır. Her sayfa için belirtilen niteliklere sahip bir JPEG aygıtı oluşturulur ve`Process` yöntemi, sayfayı küçük resim görüntüsüne dönüştürmek ve akışa kaydetmek için kullanılır.

#### S: Oluşturma işlemi sırasında ortaya çıkan küçük resimlerin çözünürlüğünü veya kalitesini ayarlayabilir miyim?

 C: Evet, çözünürlük, genişlik, yükseklik ve kalite gibi özellikleri yapılandırarak değiştirebilirsiniz.`JpegDevice` her sayfayı dönüştürmeden önce nesne.

#### S: Oluşturulan küçük resimleri, oluşturma sürecinden sonra projelerimde veya uygulamalarımda nasıl kullanabilirim?

C: Ortaya çıkan küçük resimler, PDF dosyalarının görsel bir önizlemesini sağlamak için kullanılabilir ve kullanıcıların içeriği hızlı bir şekilde tanımlamasına ve içinde gezinmesine yardımcı olur.

#### : Bu oluşturma işlemi kullanılarak PDF dosyalarından oluşturulabilecek küçük resim sayısında herhangi bir sınırlama var mı?

C: Oluşturulan küçük resimlerin sayısı, her PDF belgesindeki sayfa sayısına bağlıdır. Her sayfa ayrı bir küçük resim görüntüsüne dönüştürülecektir.