---
title: Metin Aygıtını Kullanarak Metni Çıkarın
linktitle: Metin Aygıtını Kullanarak Metni Çıkarın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET'teki Metin Aygıtını kullanarak bir PDF belgesinden metnin nasıl çıkarılacağını öğrenin.
type: docs
weight: 210
url: /tr/net/programming-with-text/extract-text-using-text-device/
---
## giriiş

Bir PDF'den metin çıkarmak, özellikle çeşitli biçimler, gömülü yazı tipleri veya karmaşık düzenler içeren belgelerle uğraşırken zor olabilir. Ancak .NET için Aspose.PDF ile bu süreç çocuk oyuncağı haline gelir! Bir PDF'nin sayfalarını daha fazla analiz için düz metne dönüştürmek veya yalnızca belirli bölümleri çıkarmak istemeniz fark etmez, Aspose.PDF sizin için her şeyi yapar. Bu eğitimde, Aspose.PDF'deki TextDevice sınıfını kullanarak bir PDF'den metnin nasıl çıkarılacağını adım adım açıklayacağız. Ayrıca, aynı yöntemleri kendi projelerinize kolayca uygulayabilmeniz için net açıklamalar da sunacağız.

## Ön koşullar

Koda geçmeden önce, takip etmek için her şeyin yerli yerinde olduğundan emin olun. İhtiyacınız olanlar şunlar:

1.  Aspose.PDF for .NET: En son sürümü şu adresten indirin:[Aspose.PDF for .NET indirme sayfası](https://releases.aspose.com/pdf/net/).
2. Geliştirme Ortamı: Visual Studio veya herhangi bir C# geliştirme ortamı.
3. .NET Framework: Projenizin .NET Framework 4.x veya üzerini hedeflediğinden emin olun.
4. Giriş PDF Dosyası: Metin çıkarmak için kullanacağınız bir PDF dosyası. Bunu makinenizdeki bir dizine yerleştirin (buna şu şekilde atıfta bulunacağız:`YOUR DOCUMENT DIRECTORY`).

## Paketleri İçe Aktar

Kodunuzun en üstünde, Aspose.PDF ile çalışmak için gerekli ad alanlarını içe aktarmanız gerekecek:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Devices;
using System;
using System.Text;
```

## Adım 1: PDF Belgenizi Yükleyin

 Metni çıkarmadan önce PDF belgesini belleğe yüklememiz gerekir. Bu adımda, PDF'nizi Aspose.PDF'in`Document` sınıf. Bu, dosyadaki tüm sayfalara ve içeriklere erişmenizi sağlayacaktır.

```csharp
// PDF belgenize giden yolu tanımlayın
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF belgesini yükleyin
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Burada, şunu kullanıyoruz`Document pdfDocument = new Document(dataDir + "input.pdf");` PDF'yi yüklemek için`dataDir` değişkeni PDF dosyanızın dizin yolunu tutar. Bu bize tüm belgeye erişim sağlayacak, sayfalar arasında dolaşıp içerik çıkarmamızı sağlayacaktır.

## Adım 2: Metin Depolama için Bir Dize Oluşturucu Ayarlayın

 Artık belge yüklendiğine göre, çıkarılan metni depolamanın bir yoluna ihtiyacımız var. Bunun için bir`StringBuilder` verimli dize birleştirmeye olanak tanır.

```csharp
// Çıkarılan metni tutacak StringBuilder
StringBuilder builder = new StringBuilder();
```

 Birini başlatıyoruz`StringBuilder`her sayfadan çıkarılan metni toplayacak olan örnek. Döngüdeki normal dize birleştirmeye kıyasla büyük dizeleri işlemenin daha verimli bir yoludur.

## Adım 3: PDF Sayfaları Arasında Döngü

 Sonra, metni çıkarmak için PDF belgesinin her sayfasında döngü oluşturacağız. Her sayfayı tek tek şu şekilde işleyeceğiz:`TextDevice` PDF içeriğini metin formatına dönüştürmekten sorumlu sınıf.

```csharp
// PDF'deki tüm sayfalarda dolaş
foreach (Page pdfPage in pdfDocument.Pages)
{
    // Her sayfayı metin çıkarma işlemi için işle
}
```

Bu döngü PDF'nin her sayfasından geçer (`pdfDocument.Pages` ). Her sayfa için metni çıkarıp kendimize ekleyeceğiz.`StringBuilder`.

## Adım 4: Her Sayfadan Metni Çıkarın

 Şimdi, her sayfa için metin çıkarma işlemini ayarlıyoruz. Burada, bir`TextDevice` nesneyi kullanın ve PDF sayfalarını işlemek için kullanın.`TextDevice` Ayarladığımız çıkarma seçeneklerine göre ham veya biçimlendirilmiş metni çıkarır.

```csharp
using (MemoryStream textStream = new MemoryStream())
{
    // Metin çıkarma için bir metin aygıtı oluşturun
    TextDevice textDevice = new TextDevice();
    
    // Metin çıkarma seçeneklerini 'Saf' moduna ayarlayın
    TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
    textDevice.ExtractionOptions = textExtOptions;

    //Metni geçerli sayfadan çıkarın ve bellek akışına kaydedin
    textDevice.Process(pdfPage, textStream);

    // Bellek akışını metne dönüştür
    string extractedText = Encoding.Unicode.GetString(textStream.ToArray());

    // Çıkarılan metni StringBuilder'a ekleyin
    builder.Append(extractedText);
}
```

- `TextDevice textDevice = new TextDevice();` : :`TextDevice` sınıfı PDF'den metin çıkarmak için kullanılır.
- `TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);` : Bu seçenek, yazı tipleri veya konumlar gibi herhangi bir biçimlendirmeyi korumadan ham metni çıkarır. Ayrıca şunu da kullanabilirsiniz:`TextFormattingMode.Raw` Biçimlendirme üzerinde daha fazla kontrole ihtiyacınız varsa.
- `textDevice.Process(pdfPage, textStream);` : Bu, PDF'nin her sayfasını işler ve çıkarılan metni bir`MemoryStream`.
-  Son olarak metni şu şekilde dönüştürüyoruz:`MemoryStream` bir dizeye ekleyin ve onu dizeye ekleyin`StringBuilder`.

## Adım 5: Çıkarılan Metni Bir Dosyaya Kaydet

 Tüm sayfalar işlendikten sonra metin şuraya kaydedilir:`StringBuilder`Son adım, çıkarılan bu metni bir dosyaya kaydetmektir.

```csharp
// Metin dosyası için çıktı yolunu tanımlayın
dataDir = dataDir + "input_Text_Extracted_out.txt";

// Çıkarılan metni bir dosyaya kaydedin
File.WriteAllText(dataDir, builder.ToString());

Console.WriteLine("\nText extracted successfully from PDF document.\nFile saved at " + dataDir);
```

- `File.WriteAllText(dataDir, builder.ToString());` : Bu, tüm içeriği yazar`StringBuilder` Bir metin dosyasına.
- Çıktı dosyasının yolu, bir dosya adı eklenerek ayarlanır (`"input_Text_Extracted_out.txt"` ) için`dataDir` yol.

## Çözüm

Aspose.PDF for .NET kullanarak bir PDF'den metin çıkarmak basit ve etkili bir işlemdir. Bu kılavuzda özetlenen adımları izleyerek PDF belgelerini kolayca açabilir, sayfalar arasında dolaşabilir ve metni bir metin dosyasına çıkarabilirsiniz. Bu özellikle büyük hacimli PDF verilerini işlemek, metin analizi yapmak veya belgeleri daha fazla düzenleme için dönüştürmek için kullanışlıdır.

Aspose.PDF ile metin çıkarmayla sınırlı değilsiniz; açıklamaları işleyebilir, görselleri düzenleyebilir veya hatta PDF'leri HTML veya Word gibi diğer biçimlere dönüştürebilirsiniz. Bu kitaplığın esnekliği ve gücü onu .NET uygulamalarında PDF yönetimi için paha biçilmez bir araç haline getirir.

## SSS

### Aspose.PDF resim tabanlı PDF'lerden metin çıkarabilir mi?
Hayır, Aspose.PDF içerik tabanlı PDF'lerden metin çıkarmak için tasarlanmıştır. Görüntü tabanlı PDF'ler için OCR teknolojisi gereklidir.

### Aspose.PDF metin çıkartılırken biçimlendirmeyi koruyor mu?
Varsayılan olarak metin biçimlendirme olmadan çıkarılır, ancak bazı biçimlendirmeleri korumak istiyorsanız çıkarma seçeneklerini ayarlayabilirsiniz.

### Belirli bir sayfa aralığından metin çıkarabilir miyim?
Evet, kodu tüm sayfalar yerine belirli bir sayfa aralığı üzerinde döngü oluşturacak şekilde değiştirebilirsiniz.

### Aspose.PDF'de metin çıkarma modları nelerdir?
Aspose.PDF iki mod sunar: Raw ve Pure. Raw modu orijinal düzeni korumaya çalışırken, Pure modu biçimlendirme yapmadan yalnızca metni çıkarır.

### Aspose.PDF for .NET, .NET Core ile uyumlu mudur?
Evet, Aspose.PDF for .NET, .NET Core ve .NET Framework ile tam uyumludur.