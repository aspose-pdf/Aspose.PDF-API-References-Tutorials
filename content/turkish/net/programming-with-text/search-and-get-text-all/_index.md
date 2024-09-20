---
title: Ara ve Tüm Metni Al
linktitle: Ara ve Tüm Metni Al
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesinin tüm sayfalarında nasıl arama yapacağınızı ve metin alacağınızı öğrenin.
type: docs
weight: 420
url: /tr/net/programming-with-text/search-and-get-text-all/
---
## giriiş

PDF'den belirli bir metni çıkarmanız gerekti mi ama bu zor oldu mu? PDF'ler bazen kilitli kaplar gibi hissettirebilir ve bu da ihtiyacınız olan bilgileri edinmeyi zorlaştırır. Ancak iyi haber şu: Aspose.PDF for .NET ile herhangi bir PDF'den kolayca metin arayabilir ve alabilirsiniz. Bu güçlü kitaplık, .NET uygulamalarınızda PDF'lerle çalışmak için ihtiyacınız olan her şeyi sağlayarak metin çıkarmayı çocuk oyuncağı haline getirir. Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasından metin arama ve çıkarma sürecini adım adım ele alacağız. İster bir metin analiz aracı oluşturuyor olun, ister sadece PDF raporlarından veri çıkarmayı otomatikleştirmeniz gereksin, doğru yerdesiniz!

## Ön koşullar

Koda geçmeden önce her şeyin ayarlandığından emin olalım:

1. .NET için Aspose.PDF: .NET için Aspose.PDF'i indirip yüklemeniz gerekecek. İndirme sayfasından edinebilirsiniz[Burada](https://releases.aspose.com/pdf/net/).
2. .NET Ortamı: Geliştirme makinenizde .NET Framework veya .NET Core'un kurulu olduğundan emin olun.
3. Temel C## Bilgisi: C# ve .NET projeleriyle çalışma konusunda biraz bilgi sahibi olmanız önerilir.
4.  PDF Belgesi: Metni çıkaracağımız örnek bir PDF dosyası. Bu örnekte, şunu kullanacağız:`SearchAndGetTextFromAll.pdf`.

## Paketleri İçe Aktar

Herhangi bir kod yazmadan önce, Aspose.PDF ile çalışmak için gerekli ad alanlarını projenize aktarmanız gerekir.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Bu ad alanları PDF'nin belge nesne modeline erişim sağlar ve dosya içindeki metni düzenlememize olanak tanır.

Süreci kolayca takip edebilmeniz için basit adımlara bölelim.

## Adım 1: Belge Dizinini Ayarlayın

İlk önce, PDF'nizin bulunduğu dizine giden yolu belirtmeniz gerekir. Bu, uygulamanın metni çıkaracağınız dosyayı bulmasına yardımcı olur.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  The`dataDir` değişken, dosyanızın bulunduğu dizini işaret etmelidir`SearchAndGetTextFromAll.pdf` dosya saklandı.
-  Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` makinenizdeki gerçek yol ile.

## Adım 2: PDF Belgesini açın

Daha sonra, Aspose.PDF'i kullanarak PDF belgesini açacağız`Document` nesne.

```csharp
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

-  Yeni bir örnek oluşturuyoruz`Document` PDF'nin tam dosya yolunu geçirerek sınıfa ekleyin.
- Bu, PDF'i belleğe yükleyerek işleme hazır hale getirecektir.

## Adım 3: Bir Metin Emici Oluşturun

 The`TextFragmentAbsorber` nesne, PDF içinde belirli bir metni aramak için kullanılır. Bu durumda, "metin" kelimesini arayacağız.

```csharp
// Giriş arama ifadesinin tüm örneklerini bulmak için TextAbsorber nesnesi oluşturun
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

-  The`TextFragmentAbsorber` dizeyle başlatılır`"text"`Bu, PDF belgesinde "metin" kelimesinin herhangi bir örneğini arayacağı anlamına gelir.

## Adım 4: Tüm Sayfalar için Absorber'ı Kabul Edin

Şimdi PDF belgesine emiciyi kabul etmesini ve metni tüm sayfalarda aramasını söyleyeceğiz.

```csharp
// Tüm sayfalar için emiciyi kabul et
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

-  The`Accept` yöntem belgenin sayfalarına uygulanır. Bu, belirtilen metin için tüm sayfaları arayacaktır.

## Adım 5: Metin Parçalarını Çıkarın

Emici belgeyi taradıktan sonra, çıkarılan metin parçalarını alabiliriz.

```csharp
// Çıkarılan metin parçalarını alın
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

-  The`TextFragments` mülkiyeti`TextFragmentAbsorber` Arama terimiyle eşleşen tüm metin parçalarının bir koleksiyonunu döndürür.

## Adım 6: Metin Parçaları Arasında Döngü

Artık metin parçaları koleksiyonumuz var, bunları dolaşıp ayrıntılarını çıkaracağız.

```csharp
// Parçalar arasında döngü
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text : {0} ", textFragment.Text);
    Console.WriteLine("Position : {0} ", textFragment.Position);
    Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

-  The`foreach` döngü her birini yineler`TextFragment` koleksiyonda.
- Her bir parçanın gerçek metni, sayfadaki konumu, yazı tipi ayrıntıları ve yazı tipi boyutu gibi çeşitli özelliklerini yazdırıyoruz.
-  The`XIndent` Ve`YIndent` özellikler PDF içindeki metin parçasının tam koordinatlarını verir.

## Çözüm

İşte karşınızda! Sadece birkaç satır kodla, .NET için Aspose.PDF kullanarak bir PDF'den metni başarıyla aradık ve çıkardık. Aspose.PDF'nin esnekliği, PDF'leri çok sayıda şekilde düzenlemenize olanak tanır ve bu da onu .NET ortamlarında sağlam PDF çözümlerine ihtiyaç duyan geliştiriciler için mükemmel bir seçim haline getirir. Bu örneği, diğer kelimeleri aramak, daha fazla ayrıntı çıkarmak veya hatta ihtiyaçlarınıza göre PDF içeriğini düzenlemek için kolayca genişletebilirsiniz. Umarım bu kılavuz, PDF'lerle çalışmak için size açık ve anlaşılır bir yaklaşım sağlamıştır. Devam edin ve kendi PDF'lerinizle deneyin!

## SSS

### Birden fazla kelimeyi aynı anda arayabilir miyim?  
 Evet, değiştirebilirsiniz`TextFragmentAbsorber` Arama dizesini buna göre ayarlayarak birden fazla ifadeyi aramak.

### Peki ya metin birden fazla satıra yayılıyorsa?  
Aspose.PDF, birden fazla satıra yayılmış olsa bile metni tanıyacak ve çıkaracaktır. Bu parçaları ayrı ayrı işleyebilirsiniz.

### Çıkarılan metni bir dosyaya nasıl kaydederim?  
 Çıkarılan metni, aşağıdaki gibi standart C# dosya G/Ç işlemlerini kullanarak bir dosyaya yazabilirsiniz:`StreamWriter`.

### Aspose.PDF taranmış PDF'lerden metin çıkarmayı destekliyor mu?  
Aspose.PDF OCR'yi desteklemez. Taranan PDF'ler için metni tanımak için bir OCR aracına ihtiyacınız olacaktır.

### Şifrelenmiş PDF'leri nasıl işlerim?  
PDF'niz parola korumalıysa, belgeyi yüklerken parolayı girerek Aspose.PDF'yi kullanarak kilidi açabilirsiniz.