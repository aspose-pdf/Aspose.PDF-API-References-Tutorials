---
title: Yazı Tipini PDF Dosyasına Göm
linktitle: Yazı Tipini PDF Dosyasına Göm
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuz ile Aspose.PDF for .NET kullanarak bir PDF dosyasına yazı tiplerini nasıl gömeceğinizi öğrenin. Belgelerinizin herhangi bir cihazda doğru şekilde görüntülendiğinden emin olun.
type: docs
weight: 120
url: /tr/net/programming-with-document/embedfont/
---
Bu öğreticide, Aspose.PDF for .NET kullanılarak bir PDF dosyasına yazı tiplerinin nasıl gömüleceğini tartışacağız. Aspose.PDF for .NET, geliştiricilerin PDF belgelerini program aracılığıyla oluşturmasına, düzenlemesine ve işlemesine olanak sağlayan güçlü bir kitaplıktır. Bu kitaplık, metin, resim, tablo ve çok daha fazlasını ekleme dahil olmak üzere PDF belgeleriyle çalışmak için çok çeşitli özellikler sağlar. Yazı tiplerini bir PDF dosyasına gömmek, gerekli yazı tiplerinin bu cihazlarda yüklü olup olmadığına bakılmaksızın, PDF dosyasının farklı cihazlarda doğru şekilde görüntülendiğinden emin olmak isteyen geliştiriciler için ortak bir gerekliliktir.

## 1. Adım: Yeni bir C# Konsol Uygulaması oluşturun
Başlamak için Visual Studio'da yeni bir C# Konsol Uygulaması oluşturun. Adını ne istersen koyabilirsin. Proje oluşturulduktan sonra Aspose.PDF for .NET kitaplığına bir referans eklemeniz gerekir.

## Adım 2: Aspose.PDF Ad Alanını İçeri Aktarın
Aspose.PDF ad alanını içe aktarmak için C# dosyanızın en üstüne aşağıdaki kod satırını ekleyin:

```csharp
using Aspose.Pdf;
```

## 3. Adım: Mevcut bir PDF Dosyasını Yükleyin
Yazı tiplerini mevcut bir PDF dosyasına gömmek için bu dosyayı Document sınıfını kullanarak yüklemeniz gerekir. Aşağıdaki kod, mevcut bir PDF dosyasının nasıl yükleneceğini gösterir:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mevcut bir PDF dosyasını yükleyin
Document doc = new Document(dataDir + "input.pdf");
```

## 4. Adım: Tüm Sayfaları yineleyin
PDF dosyasını yükledikten sonra, belgedeki tüm sayfaları yinelemeniz gerekir. Her sayfa için herhangi bir yazı tipi kullanılıp kullanılmadığını kontrol etmeniz ve kullanılıyorsa bu yazı tiplerini gömmeniz gerekir. Aşağıdaki kod, PDF dosyasındaki tüm sayfaları nasıl yineleyeceğinizi ve yazı tiplerini nasıl gömeceğinizi gösterir:

```csharp
foreach (Page page in doc.Pages)
{
    if (page.Resources.Fonts != null)
    {
        foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
        {
            // Yazı tipinin zaten gömülü olup olmadığını kontrol edin
            if (!pageFont.IsEmbedded)
                pageFont.IsEmbedded = true;
        }
    }

    // Form nesnelerini kontrol edin
    foreach (XForm form in page.Resources.Forms)
    {
        if (form.Resources.Fonts != null)
        {
            foreach (Aspose.Pdf.Text.Font formFont in form.Resources.Fonts)
            {
                // Yazı tipinin gömülü olup olmadığını kontrol edin
                if (!formFont.IsEmbedded)
                    formFont.IsEmbedded = true;
            }
        }
    }
}
```

## Adım 5: PDF Belgesini Kaydedin
Tüm yazı tiplerini PDF dosyasına yerleştirdikten sonra, belgeyi kaydetmeniz gerekir. Aşağıdaki kod, PDF dosyasının nasıl kaydedileceğini gösterir:

```csharp
dataDir = dataDir + "EmbedFont_out.pdf";
// PDF Belgesini Kaydet
doc.Save(dataDir);

Console.WriteLine("\nFont embedded successfully in a PDF file.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET kullanan Yazı Tipini Gömmek için örnek kaynak kodu

İşte Aspose.PDF for .NET kullanarak bir yazı tipini gömmek için tam kaynak kodu.


```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mevcut bir PDF dosyasını yükleyin
Document doc = new Document(dataDir + "input.pdf");

// Tüm sayfaları yineleyin
foreach (Page page in doc.Pages)
{
	if (page.Resources.Fonts != null)
	{
		foreach (Aspose.Pdf.Text.Font pageFont in page.Resources.Fonts)
		{
			// Yazı tipinin zaten gömülü olup olmadığını kontrol edin
			if (!pageFont.IsEmbedded)
				pageFont.IsEmbedded = true;
		}
	}

	// Form nesnelerini kontrol edin
	foreach (XForm form in page.Resources.Forms)
	{
		if (form.Resources.Fonts != null)
		{
			foreach (Aspose.Pdf.Text.Font formFont in form.Resources.Fonts)
			{
				// Yazı tipinin gömülü olup olmadığını kontrol edin
				if (!formFont.IsEmbedded)
					formFont.IsEmbedded = true;
			}
		}
	}
}
dataDir = dataDir + "EmbedFont_out.pdf";
// PDF Belgesini Kaydet
doc.Save(dataDir);

Console.WriteLine("\nFont embedded successfully in a PDF file.\nFile saved at " + dataDir);
```


## Sonuç yazı tipini PDF dosyasına göm
Bu makalede, Aspose.PDF for .NET kullanılarak bir PDF dosyasına yazı tiplerinin nasıl gömüleceğini ele aldık. Aspose.PDF for .NET, yazı tipi ekleme ve gömme de dahil olmak üzere PDF belgeleriyle çalışmak için basit ve kullanımı kolay bir API sağlar. Yazı tiplerini bir PDF dosyasına gömmek, gerekli yazı tiplerinin bu cihazlarda yüklü olup olmadığına bakılmaksızın, belgenin farklı cihazlarda doğru şekilde görüntülenmesini sağlamak için önemli bir adımdır.

### SSS

#### S: Yazı tiplerini bir PDF dosyasına gömmek neden önemlidir?

C: Yazı tiplerini bir PDF dosyasına gömmek, belgenin farklı aygıtlarda ve sistemlerde doğru şekilde görünmesini sağlamak için gereklidir. Yazı tipleri gömüldüklerinde, PDF dosyasının bir parçası haline gelirler ve görüntüleme cihazında yüklü olan harici yazı tiplerine olan bağımlılığı ortadan kaldırırlar.

#### S: Bir PDF dosyasında kullanılan tüm yazı tiplerini gömebilir miyim?

C: Evet, bir PDF dosyasında kullanılan tüm yazı tiplerini gömebilirsiniz. Aspose.PDF for .NET, bir PDF dosyasında kullanılan tüm yazı tiplerini yinelemek ve çeşitli cihazlarda doğru işlemeyi sağlamak için bunları gömmek için basit bir yaklaşım sağlar.

#### S: Aspose.PDF for .NET farklı yazı tipi biçimleriyle uyumlu mu?

C: Evet, Aspose.PDF for .NET, TrueType, OpenType, Type 1 ve CFF yazı tipleri dahil olmak üzere çeşitli yazı tipi biçimlerini destekler. Formatları ne olursa olsun yazı tiplerini PDF dosyasına gömebilir.

#### S: Yazı tiplerini gömmek PDF belgesinin dosya boyutunu artırır mı?

C: Evet, yazı tipi verileri PDF dosyasının kendisinde bulunduğundan, yazı tiplerini bir PDF belgesine gömmek dosya boyutunu artırabilir. Ancak bu, görüntüleme aygıtındaki yazı tipi kullanılabilirliğine bakılmaksızın belgenin görünümünün tutarlı kalmasını sağlar.

#### S: Yazı tipi gömme işlemini özelleştirebilir miyim?

C: Evet, Aspose.PDF for .NET, yazı tipi gömme sürecini özelleştirmenize izin verir. Dosya boyutunu optimize etmek için hangi yazı tiplerinin gömüleceğini seçebilir, belirli yazı tiplerini hariç tutabilir veya bir yazı tipinin yalnızca belirli alt kümelerini gömebilirsiniz.