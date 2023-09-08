---
title: Yazı Tipini PDF Dosyasına Göm
linktitle: Yazı Tipini PDF Dosyasına Göm
second_title: .NET API Referansı için Aspose.PDF
description: Bu adım adım kılavuzla Aspose.PDF for .NET kullanarak yazı tiplerini bir PDF dosyasına nasıl yerleştireceğinizi öğrenin. Belgelerinizin her cihazda doğru şekilde görüntülendiğinden emin olun.
type: docs
weight: 120
url: /tr/net/programming-with-document/embedfont/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak yazı tiplerinin bir PDF dosyasına nasıl gömüleceğini tartışacağız. Aspose.PDF for .NET, geliştiricilerin PDF belgelerini programlı olarak oluşturmasına, düzenlemesine ve değiştirmesine olanak tanıyan güçlü bir kitaplıktır. Bu kitaplık, PDF belgeleriyle çalışmak için metin, resim, tablo ekleme ve çok daha fazlasını içeren çok çeşitli özellikler sunar. Yazı tiplerini bir PDF dosyasına gömmek, gerekli yazı tiplerinin bu aygıtlarda yüklü olup olmadığına bakılmaksızın, PDF dosyasının farklı aygıtlarda doğru şekilde görüntülendiğinden emin olmak isteyen geliştiriciler için ortak bir gereksinimdir.

## 1. Adım: Yeni bir C# Konsol Uygulaması oluşturun
Başlamak için Visual Studio'da yeni bir C# Konsol Uygulaması oluşturun. İstediğiniz ismi verebilirsiniz. Proje oluşturulduktan sonra Aspose.PDF for .NET kütüphanesine bir referans eklemeniz gerekir.

## Adım 2: Aspose.PDF Ad Alanını İçe Aktarın
Aspose.PDF ad alanını içe aktarmak için C# dosyanızın en üstüne aşağıdaki kod satırını ekleyin:

```csharp
using Aspose.Pdf;
```

## 3. Adım: Mevcut bir PDF Dosyasını Yükleyin
Yazı tiplerini mevcut bir PDF dosyasına gömmek için bu dosyayı Document sınıfını kullanarak yüklemeniz gerekir. Aşağıdaki kod mevcut bir PDF dosyasının nasıl yükleneceğini gösterir:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mevcut bir PDF dosyasını yükleyin
Document doc = new Document(dataDir + "input.pdf");
```

## Adım 4: Tüm Sayfaları yineleyin
PDF dosyasını yükledikten sonra belgedeki tüm sayfaları yinelemeniz gerekir. Her sayfada herhangi bir yazı tipinin kullanılıp kullanılmadığını kontrol etmeniz ve eğer öyleyse bu yazı tiplerini yerleştirmeniz gerekir. Aşağıdaki kod, PDF dosyasındaki tüm sayfaların nasıl yineleneceğini ve yazı tiplerinin nasıl gömüleceğini gösterir:

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
Tüm yazı tiplerini PDF dosyasına gömdükten sonra belgeyi kaydetmeniz gerekir. Aşağıdaki kod PDF dosyasının nasıl kaydedileceğini gösterir:

```csharp
dataDir = dataDir + "EmbedFont_out.pdf";
// PDF Belgesini Kaydet
doc.Save(dataDir);

Console.WriteLine("\nFont embedded successfully in a PDF file.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET kullanan Embed Font için örnek kaynak kodu

Aspose.PDF for .NET kullanarak bir yazı tipini gömmek için tam kaynak kodunu burada bulabilirsiniz.


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


## Sonuç PDF dosyasına yazı tipi yerleştirme
Bu makalede, Aspose.PDF for .NET kullanarak yazı tiplerinin bir PDF dosyasına nasıl gömüleceğini tartıştık. Aspose.PDF for .NET, yazı tipi ekleme ve gömme de dahil olmak üzere PDF belgeleriyle çalışmak için basit ve kullanımı kolay bir API sağlar. Yazı tiplerini bir PDF dosyasına gömmek, gerekli yazı tiplerinin bu aygıtlarda yüklü olup olmadığına bakılmaksızın, belgenin farklı aygıtlarda doğru şekilde görüntülenmesini sağlamak için önemli bir adımdır

### SSS'ler

#### S: Fontları bir PDF dosyasına gömmek neden önemlidir?

C: Yazı tiplerini bir PDF dosyasına gömmek, belgenin farklı aygıtlarda ve sistemlerde doğru şekilde görünmesini sağlamak için çok önemlidir. Yazı tipleri gömüldüğünde PDF dosyasının bir parçası haline gelirler ve görüntüleme cihazında yüklü olan harici yazı tiplerine olan bağımlılığı ortadan kaldırırlar.

#### S: Kullanılan tüm yazı tiplerini bir PDF dosyasına gömebilir miyim?

C: Evet, kullanılan tüm yazı tiplerini bir PDF dosyasına gömebilirsiniz. Aspose.PDF for .NET, bir PDF dosyasında kullanılan tüm yazı tiplerini yinelemek ve bunları çeşitli cihazlarda doğru işleme sağlamak üzere gömmek için basit bir yaklaşım sunar.

#### S: Aspose.PDF for .NET farklı yazı tipi formatlarıyla uyumlu mudur?

C: Evet, Aspose.PDF for .NET, TrueType, OpenType, Type 1 ve CFF yazı tipleri dahil olmak üzere çeşitli yazı tipi formatlarını destekler. Formatlarına bakılmaksızın yazı tiplerini PDF dosyasına gömebilir.

#### S: Yazı tiplerini gömmek PDF belgesinin dosya boyutunu artırır mı?

C: Evet, yazı tipi verileri PDF dosyasının kendisinde yer aldığından, bir PDF belgesine yazı tipleri eklemek dosya boyutunu artırabilir. Ancak bu, görüntüleme aygıtındaki yazı tipinin kullanılabilirliğine bakılmaksızın belgenin görünümünün tutarlı kalmasını sağlar.

#### S: Yazı tipi yerleştirme işlemini özelleştirebilir miyim?

C: Evet, Aspose.PDF for .NET yazı tipi yerleştirme işlemini özelleştirmenize olanak tanır. Dosya boyutunu optimize etmek için hangi yazı tiplerinin gömüleceğini seçebilir, belirli yazı tiplerini hariç tutabilir veya bir yazı tipinin yalnızca belirli alt kümelerini gömebilirsiniz.