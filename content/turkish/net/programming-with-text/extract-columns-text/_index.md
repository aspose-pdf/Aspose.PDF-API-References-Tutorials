---
title: PDF Dosyasındaki Sütun Metnini Çıkar
linktitle: PDF Dosyasındaki Sütun Metnini Çıkar
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyalarından metin sütunlarını nasıl çıkaracağınızı öğrenin. Bu kılavuz, her adımı kod örnekleri ve açıklamalarla açıklar.
type: docs
weight: 150
url: /tr/net/programming-with-text/extract-columns-text/
---
## giriiş

PDF dosyalarıyla mı çalışıyorsunuz ve belirli bir sütun biçiminde metin çıkarmanız mı gerekiyor? Fatura, rapor veya yapılandırılmış herhangi bir belge işliyor olun, bir PDF'den metni doğru bir şekilde çıkarmak zorlu bir iş olabilir. İşte bu noktada Aspose.PDF for .NET süreci basitleştirmek için devreye giriyor. Bu eğitimde, bir PDF dosyasından metin sütunlarını kolayca nasıl çıkaracağınızı göstereceğiz. 

## Ön koşullar

Koda dalmadan önce, ihtiyacınız olacak temel şeyleri ele alalım:

-  Aspose.PDF for .NET: Aspose.PDF for .NET'in en son sürümünün yüklü olduğundan emin olun. Değilse,[buradan indirin](https://releases.aspose.com/pdf/net/).
- Geliştirme Ortamı: Kodla çalışmak için Visual Studio veya başka bir .NET geliştirme ortamına ihtiyacınız olacak.
- PDF Belgesi: Elinizde bir örnek PDF belgesi bulundurun, tercihen metin sütunları olan bir belge olsun, çünkü ondan metin çıkaracağız.

 Aspose.PDF for .NET'i henüz yüklemediyseniz, bir tane edinebilirsiniz[ücretsiz deneme](https://releases.aspose.com/) veya[lisans satın al](https://purchase.aspose.com/buy) tüm özellikler için. Ayrıca bir başvuruda bulunabilirsiniz[geçici lisans](https://purchase.aspose.com/temporary-license) eğer gerekirse.

## Ad Alanlarını İçe Aktar

Projenizde Aspose.PDF for .NET'i kullanmak için aşağıdaki ad alanlarını içe aktarmanız gerekir:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

## Adım Adım Kılavuz: PDF'den Metin Sütunlarını Çıkarma

Şimdi, kodun her bir bölümünü daha iyi anlamak için parçalara ayıralım. Sürecin her bir bölümünü açıklayarak adım adım ilerlerken bizi takip edin.

## Adım 1: PDF Belgesini Yükleyin

 Yapmanız gereken ilk şey PDF dosyanızı yüklemektir.`Document`nesne. Aspose.PDF'in belgenizle etkileşimi bu şekildedir.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

 Bu adımda, PDF belgenizin depolandığı dizini tanımlıyoruz. Değiştir`"YOUR DOCUMENT DIRECTORY"` yerel PDF dosyanızın yolu ile.`Document` nesne PDF'yi belleğe yükleyerek, daha sonraki işlemler için erişilebilir hale getirir.

## Adım 2: Metin Parçası Emicisini Ayarlayın

 Daha sonra bir tane kullanacağız`TextFragmentAbsorber` PDF dosyasındaki tüm metni emmek veya yakalamak için. Bu emici sınıf, PDF'nizdeki belirli alanlardan metin parçalarını çıkarmak için tasarlanmıştır, bu da onu metin sütunlarını çıkarmak için ideal hale getirir.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
```

Burada, bir örnek oluşturuyoruz`TextFragmentAbsorber` ve bunu PDF'in tüm sayfalarına uygulayın`Accept()` .`TextFragmentCollection` çıkarılan metni depolar ve bu koleksiyondan ihtiyaç halinde metni işleyebilir veya çıkarabiliriz.

## Adım 3: Çıkarılan Metnin Yazı Tipi Boyutunu Ayarlayın

Metin parçalarını yakaladıktan sonra, özellikle orijinal metin çok büyük olduğunda, yazı tipi boyutunu küçültmek isteyebilirsiniz. Bu örnekte, yazı tipi boyutunu %70 oranında küçültüyoruz.

```csharp
foreach (TextFragment tf in tfc)
{
    // Yazı tipi boyutunu %70 oranında azalt
    tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

Bu kod her bir döngüde ilerler`TextFragment` koleksiyonda ve yazı tipi boyutunu %70 oranında azaltır. Yazı tipi boyutunu ayarlamak, özellikle farklı amaçlar için biçimlendiriyorsanız, çıkarılan metnin yönetilmesini kolaylaştırabilir.

## Adım 4: Belgeyi bir Bellek Akışına Kaydedin

 Metni değiştirdikten sonra PDF'yi bir`MemoryStream`Bu, belgeyi diske geri yazmaya gerek kalmadan daha sonraki işlemler için bellekte tutmamızı sağlar.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
```

Burada, PDF'yi bir bellek akışına kaydediyoruz ve ardından belgeyi yeniden yüklüyoruz. Bu yöntem, büyük dosyalarla çalışırken ve gereksiz disk işlemlerinden kaçınmak istediğinizde kullanışlıdır.

## Adım 5: Text Absorber'ı Kullanarak Tüm Metni Çıkarın

 PDF'yi hazırladığımıza göre, metni çıkarma zamanı geldi. Kullanacağız`TextAbsorber` Belgedeki tüm metni almak için.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
```

 Bu adımda,`TextAbsorber` PDF'den tüm metni alır ve çıkarılan metin şurada saklanır:`extractedText` string. Sihrin gerçekleştiği yer burasıdır—metin sütunlarınız artık düz metin biçimindedir!

## Adım 6: Çıkarılan Metni Bir Dosyaya Kaydedin

 Son olarak, çıkarılan metni bir`.txt` Kolay erişim ve daha sonraki kullanım için dosyayı indirin.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

 Bu kod çıkarılan metni yeni bir dosyaya yazar.`.txt` dosyayı açar ve belirtilen dizine kaydeder. İşlemin başarılı olduğunu onaylamak için konsolda bir mesaj görüntülenir.

## Çözüm

İşte oldu! Aspose.PDF for .NET kullanarak bir PDF dosyasından metin sütunlarını çıkarmak düşündüğünüzden daha kolaydır. Sadece birkaç satır kodla bir PDF yükleyebilir, belirli bir metni çıkarabilir, biçimlendirmeyi ayarlayabilir ve sonuçları bir metin dosyasına kaydedebilirsiniz.

Bu teknik, tablolar, raporlar veya sütunlarda düzenlenmiş herhangi bir içerik gibi yapılandırılmış belgeleri işlemek için inanılmaz derecede kullanışlıdır. Veri çıkarmayı otomatikleştirmeniz veya toplu belgeleri işlemeniz gerekip gerekmediğine bakılmaksızın, Aspose.PDF bunu verimli bir şekilde gerçekleştirmek için gereken araçları sağlar.

## SSS

### PDF'in belirli sayfalarından metin çıkarabilir miyim?  
 Evet! Değiştirebilirsiniz`TextFragmentAbsorber` belirli sayfaları hedeflemek için`pdfDocument.Pages[pageIndex].Accept(tfa);` Yöntem.

### Çok sütunlu bir PDF'te yalnızca bir sütundan metin çıkarmak mümkün müdür?  
 Evet, ancak metin parçalarının koordinatlarıyla çalışmanız gerekecek`TextFragment.Rectangle` belgenin belirli alanlarını hedeflemek için.

### Metin çıkarma işleminin doğruluğunu nasıl artırabilirim?  
 Daha iyi doğruluk için PDF'nin yapısının iyi tanımlandığından emin olun ve karmaşık düzenlere sahip belgelerden kaçının. Ayrıca,`TextFragmentAbsorber` Yazı tipi stilleri, boyutları veya bölgelerine göre metin çıkarmak için.

### Aspose.PDF taranmış belgelerden metin çıkarmayı destekliyor mu?  
Evet, ancak OCR (Optik Karakter Tanıma) teknolojisini kullanmanız gerekecek. Aspose bunun için de araçlar sağlar.

### Binlerce sayfadan oluşan büyük PDF dosyalarını nasıl işlerim?  
Büyük PDF'ler için, yüksek bellek kullanımını önlemek amacıyla metni birkaç sayfadan tek tek çıkararak belgeyi parçalar halinde işleyin.