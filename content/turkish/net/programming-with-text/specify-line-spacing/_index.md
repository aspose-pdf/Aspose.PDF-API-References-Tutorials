---
title: PDF Dosyasında Satır Aralığını Belirleyin
linktitle: PDF Dosyasında Satır Aralığını Belirleyin
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım kılavuzla .NET için Aspose.PDF kullanarak bir PDF'de satır aralığını nasıl belirleyeceğinizi öğrenin. Hassas metin biçimlendirmesi arayan geliştiriciler için mükemmeldir.
type: docs
weight: 510
url: /tr/net/programming-with-text/specify-line-spacing/
---
## giriiş

PDF dosyasındaki satır aralığını kontrol etmekte hiç zorluk çektiniz mi? Belki de çok sıkışık görünen veya istediğiniz kadar cilalı görünmeyen metinleriniz olmuştur. Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF'de satır aralığını nasıl kolayca belirleyebileceğinizi göstereceğiz. Sizi boş bir PDF'den özel satır aralığı içeren bir PDF'ye götürecek basit, adım adım bir kılavuz kullanacağız. Raporlar, faturalar veya sertifikalar gibi belgeler için metin düzeninizde hassasiyete ihtiyacınız varsa bu mükemmeldir.

## Ön koşullar

Koda geçmeden önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

1.  .NET için Aspose.PDF yüklü. Eğer yoksa, şuradan edinin:[Aspose.PDF indirme sayfası](https://releases.aspose.com/pdf/net/).
2. .NET geliştirme ortamı (Visual Studio gibi).
3. Bir TrueType yazı tipi dosyası (`.ttf` ) örnekte kullanacağımız yazı tipi. Herhangi bir fontu kullanabilirsiniz, ancak bu kılavuz için,`HPSimplified.TTF` font.
4. C# ve PDF düzenleme konusunda temel bilgi.

Hazırsanız gerekli paketleri import etmeye geçelim.

## Paketleri İçe Aktar

C# projenizde, PDF işlevleriyle çalışmak için Aspose.PDF ad alanlarını içe aktarmanız gerekir. Bunu şu şekilde yapabilirsiniz:

```csharp
using Aspose.Pdf.Text;
using System.IO;
```

Bu ad alanları, PDF belgeleri oluşturmanıza ve düzenlemenize, ayrıca metin biçimlendirme ve yazı tipi seçenekleriyle çalışmanıza olanak tanır.

Bunu kolayca takip edebilmeniz için küçük adımlara böleceğiz. Her adım, PDF'nizi ayarlamaktan satır aralığını belirlemeye kadar sürecin önemli bir kısmına odaklanacaktır.

## Adım 1: Projenizi Kurun ve Belge Dizinini Tanımlayın

Yapmamız gereken ilk şey dosyalarımızın nerede bulunduğunu tanımlamaktır. Bu, programın yazı tipini nerede bulacağını ve ortaya çıkan PDF'i nereye kaydedeceğini bilmesine yardımcı olur.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
```

 Bu adımda, şunu değiştireceksiniz:`"YOUR DOCUMENT DIRECTORY"` Dosyalarınızı depoladığınız gerçek yol ile. Bu, yazı tipi dosyanızı yerleştireceğiniz yer olacaktır (`HPSimplified.TTF`) ve PDF'in nereye kaydedileceği.

## Adım 2: Bir PDF Belgesi Yükleyin

Şimdi yeni bir PDF belgesi oluşturmamız gerekiyor. Bu kılavuz için boş bir belgeyle başlayacağız, ancak gerekirse mevcut bir PDF'yi de yükleyebilirsiniz.

```csharp
Document doc = new Document();
```

Bu yeni, boş bir PDF belgesi oluşturur. Kolay, değil mi?

## Adım 3: Metin Biçimlendirme Seçeneklerini Ayarlayın

 İşte sihir burada gerçekleşiyor. PDF'ye eklemek istediğimiz metin için satır aralığı modunu belirteceğiz. Aspose.PDF bize birkaç seçenek sunuyor, ancak bu kılavuzda,`LineSpacingMode.FullSize`Satır aralıklarının tam olarak korunmasını sağlar.

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

 Bu kod satır aralığı modunu ayarlar`FullSize` , metnin uygun aralıklarla görüntülenmesini sağlar. Diğer seçenekler de vardır`Proportional` farklı aralık davranışları istiyorsanız, ancak şimdilik, buna bağlı kalalım`FullSize`.

## Adım 4: Bir Metin Parçası Oluşturun

Şimdi, PDF'e yerleştirilecek gerçek metni oluşturacağız. Bu metin, tanımladığımız satır aralığına uyacaktır.

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

 Dize ile bir metin parçası oluşturduk`"Hello world"`Elbette bu metni istediğiniz gibi özelleştirebilirsiniz.

## Adım 5: Özel bir Yazı Tipi Yükleyin ve Uygulayın

Metnin öne çıkmasını sağlamak için, bir dosyadan özel bir TrueType yazı tipi yükleyeceğiz. Bu adım isteğe bağlıdır, ancak PDF'lerinize profesyonel bir dokunuş katabilir.

```csharp
if (fontFile != "")
{
    using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
    {
        textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
```

Burada, font dosyasını yükleyip metin parçasına uygularız. Dosya yolu geçerliyse, font kullanılır. Aksi takdirde, varsayılan font uygulanır.

## Adım 6: Metin Konumunu ve Biçimlendirmeyi Ayarlayın

Sonra, metni PDF'e yerleştirmemiz gerekiyor. Ayrıca daha önce oluşturduğumuz biçimlendirme seçeneklerini de uygulayacağız.

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

 The`Position` method metnin sayfada görüneceği koordinatları ayarlar (bu durumda, soldan 100 birim ve alttan 600 birim). Satır aralığı modu da dahil olmak üzere biçimlendirme seçenekleri burada uygulanır.

## Adım 7: PDF Sayfasına Metin Ekleyin

Artık metnimiz biçimlendirilip konumlandırıldığına göre, onu PDF belgesine eklemenin zamanı geldi.

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

Bu kod PDF belgesinde yeni bir sayfa oluşturur ve metin parçasını ona ekler.

## Adım 8: PDF'yi kaydedin

Son adıma ulaştık! Artık her şey ayarlandığına göre, PDF'yi kaydedelim.

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

Böylece PDF'iniz belirtilen satır aralığıyla kaydedilir ve dosyanız hazır olur!

## Çözüm

Ve işte bu kadar! Aspose.PDF for .NET kullanarak özel satır aralığına sahip bir PDF belgesi oluşturdunuz. PDF dosyalarınızın her yönünü kontrol etmenizi sağlayan güçlü bir araçtır ve bu, başarabileceğiniz şeylerin sadece bir örneğidir. Metin yerleşiminden biçimlendirmeye kadar olasılıklar sonsuzdur.

PDF manipülasyonunda daha derinlere dalmak istiyorsanız, Aspose.PDF keşfedebileceğiniz çok sayıda özellik sunar. Belgelerinizle neler yapabileceğinizin sınırlarını zorlamak ve denemekten çekinmeyin!

## SSS

### Satır aralığını diğer modlara göre ayarlayabilir miyim?  
 Evet, şu gibi diğer modları da kullanabilirsiniz:`Proportional` veya`Fixed` ihtiyaçlarınıza bağlı olarak.

### Fontları dosya yerine sistemden yüklemek mümkün müdür?  
 Evet, sistem tarafından yüklenen yazı tiplerini kullanarak yükleyebilirsiniz.`FontRepository`.

### Aspose.PDF for .NET'i diğer dosya formatlarıyla birlikte kullanabilir miyim?  
Kesinlikle! Aspose.PDF for .NET, XML, HTML ve daha fazlası gibi çeşitli formatları destekler.

### Aspose.PDF for .NET'i kullanmak için lisansa ihtiyacım var mı?  
Evet, tam işlevsellik için edinebileceğiniz bir lisansa ihtiyacınız olacak[Burada](https://purchase.aspose.com/buy).

### Birden fazla paragraf için satır aralığını nasıl ayarlarım?  
 Başvurabilirsiniz`TextFormattingOptions` her birine`TextFragment` veya`TextParagraph` birden fazla satır veya paragraf için aralıkları kontrol etmek için.