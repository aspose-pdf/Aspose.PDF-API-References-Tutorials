---
title: PDF Dosyasında Küçük Resim Resimleri Oluşturun
linktitle: PDF Dosyasında Küçük Resim Resimleri Oluşturun
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasında kolayca küçük resim oluşturun.
type: docs
weight: 100
url: /tr/net/programming-with-images/create-thumbnail-images/
---
Bu kılavuz, Aspose.PDF for .NET kullanarak PDF dosyasında nasıl küçük resim oluşturacağınızı adım adım gösterecek. Ortamınızı zaten kurduğunuzdan emin olun ve aşağıdaki adımları izleyin:

## 1. Adım: Belge dizinini tanımlayın

 Başlamadan önce, belgeler için doğru dizini ayarladığınızdan emin olun. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` PDF dosyalarınızı içeren dizinin yolunu içeren kodda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Bir dizindeki tüm PDF dosyalarının adlarını alın

 Bu adımda, belirtilen dizinde bulunan tüm PDF dosyalarının adlarını C# kullanarak alacağız.`Directory` sınıf. Dosyalar bir dizi dizide saklanacaktır.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## 3. Adım: Tüm PDF dosyalarına ve sayfalarına göz atın

 Bu adımda, küçük resimler oluşturmak için tüm PDF dosyalarını ve sayfalarını inceleyeceğiz. bir kullanacağız`for` tüm dosyalar arasında yineleme yapmak için döngü.

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     //PDF belgesini aç
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

### PDF dosyasında küçük resimler oluşturmak için SSS

#### S: Aspose.PDF for .NET kullanarak PDF dosyalarından küçük resimler oluşturmanın amacı nedir?

Y: PDF dosyalarından küçük resimler oluşturmak, PDF'deki her sayfanın küçük görsel önizlemelerini oluşturmanıza olanak tanır; bu, içerikte hızlı bir şekilde önizleme yapmak ve gezinmek için yararlı olabilir.

#### S: Aspose.PDF for .NET, PDF dosyalarından küçük resimlerin oluşturulmasını nasıl kolaylaştırır?

Y: Aspose.PDF for .NET, PDF belgelerini açmak, sayfalarında gezinmek, küçük resimler oluşturmak ve bunları belirli bir dizine kaydetmek için adım adım bir süreç sağlar.`JpegDevice` sınıf.

#### S: Küçük resimlerin oluşturulmasına başlamadan önce belge dizinini tanımlamak neden önemlidir?

A: Belge dizininin belirtilmesi, PDF dosyalarının doğru bir şekilde konumlandırılmasını ve ortaya çıkan küçük resimlerin istenen çıktı yoluna kaydedilmesini sağlar.

####  S: nasıl`Document` class in Aspose.PDF for .NET help in the creation of thumbnail images?

 C:`Document` class, PDF belgelerini açmanıza ve değiştirmenize olanak tanır. Bu durumda, küçük resimlerin oluşturulacağı PDF dosyalarını yüklemek için kullanılır.

####  S: Hangi rolü yapar?`JpegDevice` class play in the creation of thumbnail images?

 C:`JpegDevice` class, PDF sayfalarını küçük resim olarak kullanılan JPEG resimlere dönüştürmekten sorumludur. Genişlik, yükseklik, çözünürlük ve kalite gibi nitelikleri belirtmenize olanak tanır.

#### S: PDF belgesinin her sayfası ayrı bir küçük resim görüntüsüne nasıl dönüştürülür?

 A: İç içe geçmiş`for`döngü, her bir PDF dosyasını ve sayfalarını yinelemek için kullanılır. Her sayfa için, belirtilen niteliklere sahip bir JPEG aygıtı oluşturulur ve`Process` yöntemi, sayfayı bir küçük resim görüntüsüne dönüştürmek ve akışa kaydetmek için kullanılır.

#### S: Ortaya çıkan küçük resimlerin çözünürlüğünü veya kalitesini oluşturma işlemi sırasında ayarlayabilir miyim?

 C: Evet, çözünürlük, genişlik, yükseklik ve kalite gibi özellikleri değiştirebilirsiniz.`JpegDevice` her sayfayı dönüştürmeden önce nesne.

#### S: Oluşturma sürecinden sonra oluşturulan küçük resimleri projelerimde veya uygulamalarımda nasıl kullanabilirim?

C: Ortaya çıkan küçük resimler, PDF dosyalarının görsel bir ön izlemesini sağlamak için kullanılabilir ve kullanıcıların içeriği hızlı bir şekilde tanımlamasına ve bunlar arasında gezinmesine yardımcı olur.

#### : Bu oluşturma işlemi kullanılarak PDF dosyalarından oluşturulabilecek küçük resimlerin sayısında herhangi bir sınır var mı?

A: Oluşturulan küçük resimlerin sayısı, her bir PDF belgesindeki sayfa sayısına bağlıdır. Her sayfa ayrı bir küçük resim görüntüsüne dönüştürülecektir.