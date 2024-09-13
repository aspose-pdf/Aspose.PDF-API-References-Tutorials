---
title: Üstbilgi Altbilgi Bölümündeki Resim ve Sayfa Numarası
linktitle: Üstbilgi Altbilgi Bölümündeki Resim ve Sayfa Numarası
second_title: Aspose.PDF for .NET API Referansı
description: Bu adım adım eğitimde Aspose.PDF for .NET kullanarak PDF'nizin üst bilgi ve alt bilgisine nasıl resim ve sayfa numarası ekleyeceğinizi öğrenin.
type: docs
weight: 110
url: /tr/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
## giriiş

Profesyonel düzeyde PDF belgeleri oluşturmaya gelince, başlıklar ve altbilgiler gibi küçük ayrıntılar üzerinde kontrol sahibi olmak esastır. Belgelerinizin cilalı ve iyi düzenlenmiş görünmesini istersiniz, değil mi? Aspose.PDF for .NET ile belgenizin başlık ve altbilgi bölümlerine sorunsuz bir şekilde resim ve sayfa numaraları ekleyebilirsiniz. Bu eğitimde, her adımda size rehberlik edeceğiz ve takip etmeyi kolaylaştıracağız.

## Ön koşullar

Bu eğitimin ayrıntılarına dalmadan önce, aşağıdakilerin sıralandığından emin olun:

1. .NET Framework: Bilgisayarınızda .NET framework'ün herhangi bir sürümünün yüklü olması gerekir. Eğer yoksa, Microsoft web sitesinden kolayca indirebilirsiniz.
2.  .NET için Aspose.PDF: Aspose.PDF kullanacağımız için projenizde kurulu olduğundan emin olun. Deneme sürümünü indirebilirsiniz[Burada](https://releases.aspose.com/pdf/net/).
3. Temel C# Bilgisi: Temel C# programlama bilgisine sahip olmak, kodu fazla uğraşmadan anlamanıza yardımcı olacaktır.
4. Bir Resim Dosyası: PDF belgenizin başlığına koymak istediğiniz bir resme, örneğin bir logoya ihtiyacınız olacak. Bunu erişilebilir bir dizine kaydedin. 
5. IDE: .NET projenizle çalışmak için Visual Studio gibi istediğiniz bir Entegre Geliştirme Ortamı (IDE) kullanın.

Ön koşulları hazırladığınızda, muhteşem bir PDF dosyası oluşturmak için her şey hazır olacak!

## Paketleri İçe Aktar

Aspose.PDF for .NET'i kullanmaya başlamak için gerekli ad alanlarını içe aktarmanız gerekir. C# dosyanızın en üstüne şunu eklersiniz:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Image;
```

Bu ad alanları, PDF dosyalarının düzenlenmesi için gereken sınıflara erişmenizi sağlayacaktır.

Şimdi asıl konuya geçelim! PDF belgenizi oluşturmak için şu adımları izleyin, başlığa bir resim ve alt bilgiye sayfa numaraları ekleyin.

## Adım 1: Belge Dizininizi Ayarlayın

Her iyi proje organizasyonla başlar. Dosyalarınızı kaydedeceğiniz ve görüntünüzün bulunduğu belge dizininizi tanımlayın. İşte nasıl yapacağınız:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Değiştirmeyi unutmayın`"YOUR DOCUMENT DIRECTORY"` PDF'inizi kaydetmek istediğiniz gerçek yol ve görüntünüzün bulunduğu yer.

## Adım 2: Yeni bir PDF Belgesi Oluşturun

Şimdi, tüm sihrin gerçekleşeceği yeni bir PDF belgesi oluşturacağız:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

Bu noktada boş bir PDF belgesi oluşturdunuz. Heyecan verici, değil mi?

## Adım 3: Belgeye Bir Sayfa Ekleyin

PDF tamamen sayfalarla ilgilidir. Belgemize şunu kullanarak yeni bir sayfa ekleyelim:

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

Artık tasarlamaya başlayabileceğiniz bir tuvaliniz var!

## Adım 4: Başlık Bölümünü Oluşturun

Başlığınız, görüntülemek istediğiniz görseli (bir logo gibi) içerecektir. Başlık bölümünü aşağıdaki kodla oluşturun:

```csharp
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
page.Header = header;
```

Artık özelleştirebileceğiniz bir başlığınız var!

## Adım 5: Başlığa Bir Resim Ekleyin

Şimdi eğlenceli kısma geliyoruz! Resminizi başlığınıza eklemeniz gerekiyor. İlk olarak bir resim nesnesi oluşturun:

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
```

Resminizin dosya yolunu ayarlayın:

```csharp
image1.File = dataDir + "aspose-logo.jpg";
```

Son olarak başlığınıza görseli ekleyin:

```csharp
header.Paragraphs.Add(image1);
```

Tebrikler! PDF başlığınıza bir resim eklediniz.

## Adım 6: Altbilgi Bölümünü Oluşturun

Şimdi footer üzerinde çalışalım. Header sürecine benzer şekilde bir footer nesnesi oluşturun:

```csharp
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();
page.Footer = footer;
```

Sayfa numaranızı buraya koyacaksınız. 

## Adım 7: Altbilgiye Metin Ekleyin

Sayfa numarasını tutacak bir metin parçası oluşturun:

```csharp
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");
```

Daha sonra bu metin parçasını alt bilgiye ekleyin:

```csharp
footer.Paragraphs.Add(txt);
```

Ne kadar kolay olduğunu gördünüz mü? Sayfa numaranızı dinamik olarak ayarladınız!

## Adım 8: PDF Belgesini Kaydedin

Maceramızdaki son adım belgeyi kaydetmektir. Yeni oluşturduğunuz PDF'yi kaydetmek için bu komutu kullanın:

```csharp
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

Ve işte bu kadar, PDF'niz hazır ve alt bilgi kısmında başlık resmi ve sayfa numaralarıyla yükleniyor!

## Çözüm

Ve işte karşınızda! .NET için Aspose.PDF kullanarak başlıkta bir resim ve alt bilgide dinamik sayfa numaraları olan bir PDF oluşturdunuz. Birkaç satır kodun nasıl bu kadar cilalı bir çıktıya dönüşebildiği inanılmaz. İster kurumsal bir rapor ister kişiselleştirilmiş bir belge olsun, bu öğeleri eklemek PDF'nizin tonunu ve profesyonelliğini değiştirir.

## SSS

### Aspose.PDF'yi herhangi bir .NET platformunda kullanabilir miyim?
Evet, Aspose.PDF for .NET, .NET Framework, .NET Core ve daha fazlası dahil olmak üzere birden fazla .NET platformunu destekler.

### Aspose.PDF için ücretsiz deneme sürümü mevcut mu?
 Kesinlikle! Ücretsiz deneme sürümünü indirebilirsiniz[Burada](https://releases.aspose.com/).

### Başlıklar için hangi resim biçimleri destekleniyor?
Aspose.PDF, başlık ve altbilgiler için JPG, PNG ve BMP gibi en yaygın resim formatlarını destekler.

### Sayfa numarası biçimini özelleştirebilir miyim?
Evet, alt bilgi metnini ve formatını ihtiyaçlarınıza göre kolayca özelleştirebilirsiniz.

### Teknik destek mevcut mu?
 Evet, Aspose forumları aracılığıyla özel destek sağlar. Yardım için ulaşabilirsiniz[Burada](https://forum.aspose.com/c/pdf/10).