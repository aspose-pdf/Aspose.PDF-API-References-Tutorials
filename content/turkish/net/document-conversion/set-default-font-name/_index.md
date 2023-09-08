---
title: Varsayılan Yazı Tipi Adını Ayarla
linktitle: Varsayılan Yazı Tipi Adını Ayarla
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF dosyasında varsayılan yazı tipi adını ayarlamak için adım adım kılavuz.
type: docs
weight: 270
url: /tr/net/document-conversion/set-default-font-name/
---
Bu eğitimde size Aspose.PDF for .NET kullanarak bir PDF dosyasında varsayılan yazı tipi adını nasıl ayarlayacağınızı göstereceğiz. Bazen bir PDF dosyasından görsel ayıkladığınızda eksik yazı tipi sorunlarıyla karşılaşabilirsiniz. Varsayılan bir yazı tipi adı belirterek, çıkarılan metnin doğru şekilde görüntülenmesini sağlayabilirsiniz. Bir PDF dosyasında varsayılan yazı tipi adını ayarlamak için aşağıdaki adımları izleyin.

## Önkoşullar
Başlamadan önce aşağıdaki önkoşulları karşıladığınızdan emin olun:

- C# programlama dili hakkında temel bilgiler.
- Sisteminizde yüklü olan .NET için Aspose.PDF kütüphanesi.
- Visual Studio gibi bir geliştirme ortamı.

## 1. Adım: PDF belgesini yükleme
 İlk adım, PDF belgesini bir`Document` nesne. Aşağıdaki kodu kullanın:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     // Eklenecek kod
}
```

 Değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` PDF dosyanızın bulunduğu gerçek dizinle.

## 2. Adım: Varsayılan yazı tipi adını ayarlayın
 Daha sonra, varsayılan yazı tipi adını kullanarak ayarlayacağız.`DefaultFontName` seçeneği`RenderingOptions` nesne. Aşağıdaki kodu kullanın:

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
     {
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         RenderingOptions ro = new RenderingOptions();
         ro.DefaultFontName = "Arial";
         pngDevice.RenderingOptions = ro;
        
         // Eklenecek kod
     }
}
```

 Değiştirdiğinizden emin olun`"Arial"` İstenilen yazı tipi adı ile.

## Adım 3: Görüntü Çıkarma
Daha sonra görüntüyü PDF belgesinin belirtilen sayfasından çıkaracağız. Aşağıdaki kodu kullanın:

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```

 Doğru sayfa numarasını belirttiğinizden emin olun.`pdfDocument.Pages[1]`.

### Aspose.PDF for .NET kullanarak Varsayılan Yazı Tipi Adını Ayarla için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
	using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
	{
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		RenderingOptions ro = new RenderingOptions();
		ro.DefaultFontName = "Arial";
		pngDevice.RenderingOptions = ro;
		pngDevice.Process(pdfDocument.Pages[1], imageStream);
	}
}
```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasında varsayılan yazı tipi adının nasıl ayarlanacağını öğrendik. Varsayılan bir yazı tipi adı belirterek, çıkarılan metnin doğru şekilde görüntülenmesini sağlayabilirsiniz. PDF dosyalarından görsel ayıklarken eksik yazı tipi sorunlarını çözmek için bu yöntemi kullanın.

### SSS'ler

#### S: Aspose.PDF for .NET nedir?

C: Aspose.PDF for .NET, geliştiricilerin C# uygulamalarında PDF belgeleriyle çalışmasına olanak tanıyan güçlü bir kitaplıktır. Bir PDF dosyasında varsayılan yazı tipi adını ayarlamak da dahil olmak üzere çeşitli işlevler sunar.

#### S: Bir PDF dosyasında neden varsayılan yazı tipi adını ayarlamam gerekiyor?

C: Varsayılan yazı tipi adını ayarlamak, bir PDF belgesinden metin çıkarırken kullanışlıdır. PDF, çıkarma makinesinde bulunmayan yazı tiplerine sahip metin içeriyorsa, varsayılan bir yazı tipi adının belirtilmesi, metnin doğru görüntülenmesini sağlar.

#### S: Aspose.PDF for .NET'i kullanarak bir PDF belgesini nasıl yükleyebilirim ve varsayılan yazı tipi adını nasıl ayarlayabilirim?

 C: Bir PDF belgesi yüklemek ve varsayılan yazı tipi adını ayarlamak için`Document`PDF dosyasını yüklemek için sınıf ve`RenderingOptions.DefaultFontName` İstenilen varsayılan yazı tipi adını belirtmek için özellik.

#### S: Varsayılan yazı tipi adı olarak herhangi bir yazı tipini seçebilir miyim?

C:Evet, çıkarma makinesinde bulunan herhangi bir yazı tipini varsayılan yazı tipi adı olarak seçebilirsiniz. Doğru metin oluşturmayı sağlamak için orijinal PDF'deki eksik yazı tipleriyle yakından eşleşen bir yazı tipi kullanın.

#### S: Varsayılan yazı tipi adının ayarlanması PDF dosyasında kalıcı bir değişiklik midir?

C: Hayır, varsayılan yazı tipi adını Aspose.PDF for .NET kullanarak ayarlamak, metin çıkarma sırasında yapılan geçici bir değişikliktir. Orijinal PDF dosyasını değiştirmez.