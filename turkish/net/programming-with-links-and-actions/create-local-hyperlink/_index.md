---
title: PDF Dosyasında Yerel Köprü Oluşturma
linktitle: PDF Dosyasında Yerel Köprü Oluşturma
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasında kolayca yerel köprüler oluşturun.
type: docs
weight: 40
url: /tr/net/programming-with-links-and-actions/create-local-hyperlink/
---
PDF dosyasında yerel köprüler oluşturmak, kullanıcıları aynı PDF belgesindeki diğer sayfalara götüren tıklanabilir bağlantılar oluşturmanıza olanak tanır. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu izleyerek bu tür bağlantıları kolayca oluşturabilirsiniz:

## 1. Adım: Gerekli Kitaplıkları İçe Aktarın

Başlamadan önce, C# projeniz için gerekli kitaplıkları içe aktarmanız gerekir. İşte gerekli ithalat yönergesi:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda, ortaya çıkan PDF dosyasını kaydetmek istediğiniz klasörün yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"`belgeler klasörünüzün gerçek yolu ile aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3. Adım: Bir Belge örneği oluşturun

 örneğini oluşturacağız`Document` sınıfı PDF belgemizi temsil edecek. İşte ilgili kod:

```csharp
Document doc = new Document();
```

## 4. Adım: Köprülerle sayfa ve metin ekleyin

Bu adımda, PDF belgemize bir sayfa ekleyeceğiz ve yerel köprüler içeren bazı metinler ekleyeceğiz. Her bağlantı için hedef sayfaları tanımlayacağız. İşte ilgili kod:

```csharp
Page page = doc.Pages.Add();

TextFragment text = new TextFragment("Link to page 7");
LocalHyperlink link = new LocalHyperlink();
link.TargetPageNumber = 7;
text. Hyperlink = link;
page.Paragraphs.Add(text);

text = new TextFragment("Link to page 1");
text. IsInNewPage = true;
link = new LocalHyperlink();
link.TargetPageNumber = 1;
text. Hyperlink = link;
page.Paragraphs.Add(text);
```

## 5. Adım: Güncellenen belgeyi kaydedin

 Şimdi güncellenmiş PDF dosyasını kullanarak kaydedelim.`Save` yöntemi`doc` nesne. İşte ilgili kod:

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
doc.Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Yerel Köprü Oluşturma için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge örneği oluştur
Document doc = new Document();
// PDF dosyasının sayfa koleksiyonuna sayfa ekle
Page page = doc.Pages.Add();
// Metin Parçası örneği oluştur
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
// Yerel köprü örneği oluştur
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink();
// Bağlantı örneği için hedef sayfa ayarla
link.TargetPageNumber = 7;
// TextFragment köprüsünü ayarla
text.Hyperlink = link;
//Sayfanın paragraf koleksiyonuna metin ekleyin
page.Paragraphs.Add(text);
// Yeni TextFragment örneği oluştur
text = new TextFragment("link page number test to page 1");
// TextFragment yeni sayfanın üzerine eklenmelidir
text.IsInNewPage = true;
// Başka bir yerel köprü örneği oluştur
link = new LocalHyperlink();
// İkinci köprü için Hedef sayfası ayarla
link.TargetPageNumber = 1;
// İkinci TextFragment için bağlantıyı ayarla
text.Hyperlink = link;
// Sayfa nesnesinin paragraf koleksiyonuna metin ekleyin
page.Paragraphs.Add(text);    
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
// Güncellenen belgeyi kaydet
doc.Save(dataDir);
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);            
```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF'de yerel köprüler oluşturmak için adım adım bir kılavuzunuz var. Bu kodu, kullanıcıları aynı belgedeki diğer sayfalara götüren tıklanabilir bağlantılar oluşturmak için kullanabilirsiniz.

Gelişmiş hiper bağlantı özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine baktığınızdan emin olun.

### PDF dosyasında yerel köprü oluşturmak için SSS

#### S: Bir PDF dosyasındaki yerel köprüler nelerdir?

Y: Bir PDF dosyasındaki yerel köprüler, kullanıcıları aynı belge içinde farklı sayfalara yönlendiren tıklanabilir bağlantılardır. Bu bağlantılar gezinmeyi geliştirir ve okuyucuların ilgili bölümlere hızla erişmelerini sağlar.

#### S: Yerel köprüler PDF belgeme nasıl fayda sağlayabilir?

C: Yerel köprüler, aynı PDF belgesindeki ilgili içeriği bağlamak için etkili bir yol sağlar. Okuyucuların tüm belgeyi kaydırmadan belirli bölümlere hızlı bir şekilde atlamasını sağlayarak kullanıcı deneyimini geliştirirler.

#### S: Aspose.PDF for .NET yerel köprülerin oluşturulmasını nasıl destekliyor?
Y: Aspose.PDF for .NET, yerel köprüler oluşturmak için kapsamlı destek sunar. Bu kılavuzda sağlanan adım adım öğretici, C# kullanarak PDF belgenize yerel köprülerin nasıl ekleneceğini gösterir.

#### S: Yerel köprülerin görünümünü özelleştirebilir miyim?

Y: Evet, metin rengi ve stili de dahil olmak üzere yerel köprülerin görünümünü, belgenizin tasarımına uymasını sağlamak ve tutarlı bir görsel deneyim sağlamak için özelleştirebilirsiniz.

#### S: Tek bir PDF sayfasında birden çok yerel köprü oluşturmak mümkün müdür?

C: Kesinlikle! Tek bir PDF sayfasında birden çok yerel hiper bağlantı oluşturarak, okuyucuların gerektiğinde çeşitli bölümlere veya sayfalara atlamasını sağlayabilirsiniz. Her yerel köprü, ilgili hedefine göre uyarlanabilir.

#### S: Yerel köprüleri kullanarak bir sayfanın belirli bölümlerine bağlanabilir miyim?

C: Yerel köprüler tipik olarak sayfaların tamamında gezinirken, hedeflenen bağlantıya ulaşmak için PDF belgenizde bağlantı noktaları veya yer imleri oluşturabilirsiniz. Aspose.PDF for .NET, çeşitli hiper bağlantı seçeneklerini destekler.

#### S: Yerel köprülerimin düzgün çalıştığını nasıl doğrulayabilirim?

Y: Sağlanan öğretici ve örnek kodu izleyerek, güvenle işlevsel yerel köprüler oluşturabilirsiniz. Oluşturulan PDF belgesini açıp hiper bağlantılı metne tıklayarak bağlantıları test edebilirsiniz.

#### S: Yerel köprüleri kullanırken herhangi bir sınırlama var mı?

C: Yerel köprüler, belgede gezinmeyi geliştirmenin etkili bir yoludur, ancak belge yapısının açık ve sezgisel kalmasını sağlamak önemlidir. Düzgün bir şekilde etiketlenmiş köprüler ve bağlantılar, olumlu bir kullanıcı deneyimine katkıda bulunur.

#### S: Tablolar veya resimler içinde yerel köprüler oluşturabilir miyim?

Y: Evet, PDF belgenizin tablolar, resimler ve metin dahil olmak üzere çeşitli öğelerinde yerel köprüler oluşturabilirsiniz. Aspose.PDF for .NET, farklı içerik türlerine hiper bağlantı ekleme esnekliği sunar.