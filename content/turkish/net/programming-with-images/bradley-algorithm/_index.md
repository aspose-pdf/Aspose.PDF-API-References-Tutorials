---
title: Bradley Algoritması
linktitle: Bradley Algoritması
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET'te Bradley algoritmasını kullanarak bir PDF'yi TIFF'e nasıl dönüştüreceğinizi öğrenin. Sorunsuz dönüşüm için adım adım kılavuz, ön koşullar ve SSS.
type: docs
weight: 30
url: /tr/net/programming-with-images/bradley-algorithm/
---
## giriiş

PDF dosyalarıyla çalışmak bazen onları okumaktan veya düzenlemekten daha fazlasını gerektirebilir; onları resimlere dönüştürmeniz gerekebilir. PDF'leri TIFF resimlerine dönüştürmenin güçlü bir yolu, Aspose.PDF for .NET kitaplığı aracılığıyla Bradley Algoritmasını kullanmaktır. Bu yöntem, belge arşivleme ve diğer özel kullanım durumları için mükemmel olan yüksek kaliteli ikili resimler sağlar.

Bu eğitim, Bradley Binarization Algorithm ile bir PDF sayfasını TIFF görüntüsüne dönüştürmek için ayrıntılı ve kolay takip edilebilir bir süreçte size yol gösterecektir. Aspose.PDF for .NET bu görevi basitleştirerek belge iş akışlarınızı otomatikleştirme ve kolaylaştırma olanağı sağlar.

## Ön koşullar

Koda dalmadan önce, takip etmeniz gereken her şeye sahip olduğunuzdan emin olalım:

-  .NET için Aspose.PDF: Kütüphaneye ihtiyacınız olacak. Buradan indirin[Burada](https://releases.aspose.com/pdf/net/).
- Visual Studio (veya herhangi bir C# IDE).
- Temel C# bilgisi.
-  Geçerli bir lisans veya[geçici lisans](https://purchase.aspose.com/temporary-license/) Aspose'dan.

## Paketleri İçe Aktar

İlk önce, gerekli ad alanlarını projenize aktardığınızdan emin olun. Bu kütüphaneler size PDF belgelerini düzenlemeniz, bunları TIFF formatına dönüştürmeniz ve Bradley ikilileştirme algoritmasını uygulamanız için araçlar sağlayacaktır.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Süreci sorunsuz bir şekilde takip edebilmeniz için süreci kolay adımlara bölelim. Bu kılavuzun sonunda, Bradley algoritmasını kullanarak bir PDF sayfasını ikili TIFF görüntüsüne başarıyla dönüştürmüş olacaksınız.

## Adım 1: Belge Dizinini Ayarlayın

İlk adım, PDF belgenizin bulunduğu dizine giden yolu belirtmektir. Ayrıca, oluşturulacak TIFF görüntüleri için çıktı yollarını da tanımlayacaksınız.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // PDF dosyanıza giden yol
```

Burada hem kaynak PDF'yi hem de dönüştürülmüş TIFF dosyalarını depolarsınız. Kodun dosyaları hatasız okuyabilmesi ve yazabilmesi için dizinin düzgün ayarlandığından emin olun.

## Adım 2: PDF Belgesini açın

Artık yol ayarlandığına göre, dönüştürmek istediğiniz PDF belgesini açmanın zamanı geldi. Aspose.PDF for .NET, daha fazla işlem için bir belgenin yüklenmesini kolaylaştırır.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

 Burada,`PageToTIFF.pdf` örnek dosyadır. Bunu istediğiniz herhangi bir PDF dosyasıyla değiştirebilirsiniz. Belge nesnesi artık daha fazla düzenleme için PDF'yi tutar.

## Adım 3: Görüntüler için Çıktı Yollarını Tanımlayın

Daha sonra, hem standart TIFF hem de ikili sürüm dahil olmak üzere, oluşturulan TIFF dosyaları için çıktı yollarını belirteceksiniz.

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

Bu yolları ayırarak, standart TIFF dönüşümü için bir dosyanız ve Bradley algoritması uygulandıktan sonra ikili görüntü için başka bir dosyanız olur.

## Adım 4: Bir Çözünürlük Nesnesi Oluşturun

PDF'leri TIFF'e dönüştürürken çözünürlük, görüntü kalitesini belirlemede önemli bir rol oynar. Bizim amacımız için, yüksek kaliteli çıktı sağlamak için bunu 300 DPI olarak ayarlayacağız.

```csharp
Resolution resolution = new Resolution(300);
```

Daha yüksek DPI, özellikle yazdırılacak veya arşivlenecek belgeler söz konusu olduğunda daha iyi görüntü netliği anlamına gelir.

## Adım 5: TIFF Ayarlarını Yapılandırın

Sonra, TIFF görüntüsü için ayarları yapılandırmanız gerekecek. Burada, LZW Sıkıştırmayı kullanacağız ve ikili bir görüntü elde etmek için renk derinliğini 1bpp'ye (piksel başına 1 bit) ayarlayacağız.

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

Derinliği 1bpp'ye ayarlayarak görüntüyü ikili çıktı için hazırlıyoruz. LZW sıkıştırma, kaliteyi kaybetmeden dosya boyutunu azaltmadaki verimliliği nedeniyle seçilmiştir.

## Adım 6: TIFF Aygıtını Oluşturun

Şimdi, dönüşümü işleyecek bir TIFF aygıtı oluşturmanız gerekecek. Bu aygıt daha önce tanımlanan çözünürlük ve TIFF ayarlarını kullanır.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

TIFF aygıtı bu işlemin çekirdeğidir. PDF belgesini alır ve her sayfayı önceden tanımladığınız ayarlara göre bir TIFF görüntüsüne dönüştürür.

## Adım 7: PDF Sayfasını TIFF'e Dönüştürün

 PDF'yi işleme ve ilk sayfayı bir TIFF görüntüsüne dönüştürme zamanı.`Process` yöntemi belirli sayfaları veya tüm belgeyi dönüştürmenize olanak tanır. Bu örnekte, ilk sayfayı dönüştürüyoruz.

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

Yöntem tamamlandığında, daha önce tanımladığınız konuma kaydedilmiş bir TIFF görüntünüz olacak.

## Adım 8: Bradley İkilileştirme Algoritmasını Uygulayın

Şimdi sihir geliyor—Bradley Algoritması! Bu algoritma, gri tonlamalı TIFF görüntüsünü ikili bir görüntüye dönüştürerek belge tanıma sistemleri için optimize eder.

```csharp
using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
{
    using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
    {
        tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
    }
}
```

 BinarizeBradley yöntemi iki dosya akışı (giriş ve çıkış) ve bir eşik değeri (burada) alır`0.1`) ikilileştirme seviyesini belirler. Yürütmenin ardından, kullanıma hazır mükemmel bir şekilde ikilileştirilmiş bir görüntünüz olacak.

## Adım 9: Başarılı Dönüşümü Onaylayın

Son olarak, kullanıcıya işlemin başarılı olduğunu bildirmek iyi bir uygulamadır. Bunu basit bir konsol çıktısıyla yapabilirsiniz.

```csharp
System.Console.WriteLine("Conversion using Bradley algorithm performed successfully!");
```

Bunu yazdırdığınızda PDF sayfanızın ikili TIFF görüntüsüne başarıyla dönüştürüldüğünü anlarsınız!

## Çözüm

İşte oldu! Aspose.PDF for .NET kullanarak bir PDF sayfasını bir TIFF görüntüsüne nasıl dönüştüreceğinizi ve Bradley ikilileştirme algoritmasını nasıl uygulayacağınızı öğrendiniz. Bu işlem, belge arşivleme, optik karakter tanıma (OCR) ve diğer profesyonel uygulamalar için olmazsa olmazdır. Yüksek kaliteli çözünürlük ve verimli sıkıştırma ile belge görüntülerinizin hem net hem de boyut olarak yönetilebilir olmasını sağlayabilirsiniz.

## SSS

### Bradley Algoritması Nedir?
Bradley Algoritması, her piksel için çevresine bağlı olarak uyarlanabilir bir eşik değeri belirleyerek gri tonlamalı görüntüleri ikili (siyah-beyaz) görüntülere dönüştüren bir ikilileştirme tekniğidir.

### Bu yöntemi kullanarak birden fazla PDF sayfasını TIFF'e dönüştürebilir miyim?
 Evet, değiştirebilirsiniz`Process` Belgedeki sayfalar arasında döngü yaparak tüm sayfaları dönüştürme yöntemi.

### PDF'leri TIFF'e dönüştürmek için en uygun çözünürlük nedir?
Yüksek kaliteli görüntüler için genellikle 300 DPI önerilir. Ancak bu değeri ihtiyaçlarınıza göre ayarlayabilirsiniz.

### Renk derinliğinde 1bpp ne anlama geliyor?
1bpp (piksel başına 1 bit), görüntünün siyah beyaz olacağı ve her pikselin ya tamamen siyah ya da tamamen beyaz olacağı anlamına gelir.

### Bradley Algoritması OCR için uygun mudur?
Evet, Bradley Algoritması taranan belgelerdeki metnin kontrastını artırdığı için OCR ön işlemede sıklıkla kullanılır.