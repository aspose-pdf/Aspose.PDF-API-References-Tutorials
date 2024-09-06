---
title: PDF Dosyasında Yerel Köprü Oluştur
linktitle: PDF Dosyasında Yerel Köprü Oluştur
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasında kolayca yerel köprüler oluşturun.
type: docs
weight: 40
url: /tr/net/programming-with-links-and-actions/create-local-hyperlink/
---
PDF dosyasında yerel köprüler oluşturmak, kullanıcıları aynı PDF belgesindeki diğer sayfalara götüren tıklanabilir bağlantılar oluşturmanıza olanak tanır. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu izleyerek bu tür bağlantıları kolayca oluşturabilirsiniz:

## Adım 1: Gerekli Kitaplıkları İçe Aktarın

Başlamadan önce, C# projeniz için gerekli kütüphaneleri içe aktarmanız gerekir. İşte gerekli içe aktarma yönergesi:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## Adım 2: Belgeler klasörüne giden yolu ayarlayın

 Bu adımda, ortaya çıkan PDF dosyasını kaydetmek istediğiniz klasörün yolunu belirtmeniz gerekir. Değiştir`"YOUR DOCUMENT DIRECTORY"` Aşağıdaki kodda belgeler klasörünüzün gerçek yolunu bulabilirsiniz:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 3: Bir Belge örneği oluşturun

 Bir örneğini oluşturacağız`Document` PDF belgemizi temsil eden sınıf. İşte karşılık gelen kod:

```csharp
Document doc = new Document();
```

## Adım 4: Sayfa ve metni köprü metinlerle ekleyin

Bu adımda, PDF belgemize bir sayfa ekleyeceğiz ve yerel köprüler içeren bir metin ekleyeceğiz. Her bağlantı için hedef sayfaları tanımlayacağız. İşte karşılık gelen kod:

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

## Adım 5: Güncellenen belgeyi kaydedin

Şimdi güncellenen PDF dosyasını kullanarak kaydedelim`Save` yöntemi`doc` nesne. İşte karşılık gelen kod:

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
doc.Save(dataDir);
```

### .NET için Aspose.PDF kullanarak Yerel Köprü Oluşturma için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge örneği oluştur
Document doc = new Document();
// PDF dosyasının sayfa sayfa koleksiyonunu ekle
Page page = doc.Pages.Add();
// Metin Parçası örneği oluştur
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
// Yerel köprü metni örneği oluştur
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink();
// Bağlantı örneği için hedef sayfayı ayarla
link.TargetPageNumber = 7;
// TextFragment köprü metni ayarla
text.Hyperlink = link;
// Sayfanın paragraf koleksiyonuna metin ekle
page.Paragraphs.Add(text);
// Yeni TextFragment örneği oluştur
text = new TextFragment("link page number test to page 1");
// TextFragment yeni sayfaya eklenmelidir
text.IsInNewPage = true;
// Başka bir yerel köprü metni örneği oluşturun
link = new LocalHyperlink();
// İkinci köprü metni için Hedef sayfasını ayarla
link.TargetPageNumber = 1;
// İkinci TextFragment için bağlantıyı ayarla
text.Hyperlink = link;
// Sayfa nesnesinin paragraf koleksiyonuna metin ekle
page.Paragraphs.Add(text);    
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
// Güncellenen belgeyi kaydet
doc.Save(dataDir);
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);            
```

## Çözüm

Tebrikler! Artık .NET için Aspose.PDF kullanarak bir PDF'de yerel köprüler oluşturmak için adım adım bir kılavuzunuz var. Bu kodu, kullanıcıları aynı belgedeki diğer sayfalara götüren tıklanabilir bağlantılar oluşturmak için kullanabilirsiniz.

Gelişmiş köprüleme özellikleri hakkında daha fazla bilgi edinmek için resmi Aspose.PDF belgelerine göz atmayı unutmayın.

### PDF dosyasında yerel köprü metni oluşturmaya ilişkin SSS

#### S: PDF dosyasındaki yerel köprü metinleri nelerdir?

A: Bir PDF dosyasındaki yerel köprüler, kullanıcıları aynı belgedeki farklı sayfalara yönlendiren tıklanabilir bağlantılardır. Bu bağlantılar gezinmeyi geliştirir ve okuyucuların ilgili bölümlere hızla erişmesini sağlar.

#### S: Yerel köprü metinleri PDF dokümanıma nasıl fayda sağlar?

A: Yerel köprüler, aynı PDF belgesindeki ilgili içerikleri birbirine bağlamanın etkili bir yolunu sunar. Okuyucuların tüm belgeyi kaydırmadan belirli bölümlere hızla atlamasını sağlayarak kullanıcı deneyimini iyileştirir.

#### S: Aspose.PDF for .NET yerel köprü metinlerinin oluşturulmasını nasıl destekliyor?
A: Aspose.PDF for .NET, yerel köprüler oluşturmak için kapsamlı destek sunar. Bu kılavuzda sağlanan adım adım eğitim, C# kullanarak PDF belgenize yerel köprülerin nasıl ekleneceğini gösterir.

#### S: Yerel köprü metinlerinin görünümünü özelleştirebilir miyim?

C: Evet, yerel köprü metinlerinin rengini ve stilini özelleştirerek, bunların belgenizin tasarımına uymasını ve tutarlı bir görsel deneyim sağlamasını sağlayabilirsiniz.

#### S: Tek bir PDF sayfası içerisinde birden fazla yerel köprü oluşturmak mümkün müdür?

A: Kesinlikle! Tek bir PDF sayfasında birden fazla yerel köprü metni oluşturabilir ve okuyucuların ihtiyaç duyduklarında çeşitli bölümlere veya sayfalara atlayabilmelerini sağlayabilirsiniz. Her yerel köprü metni kendi hedef kitlesine göre uyarlanabilir.

#### S: Yerel köprü metinleri kullanarak bir sayfanın belirli bölümlerine bağlantı verebilir miyim?

A: Yerel köprü metinleri genellikle tüm sayfalara yönlendirirken, hedeflenen bağlantı elde etmek için PDF belgeniz içinde bağlantılar veya yer imleri oluşturabilirsiniz. Aspose.PDF for .NET çeşitli köprü metni seçeneklerini destekler.

#### S: Yerel köprü metinlerimin doğru çalıştığını nasıl doğrulayabilirim?

A: Verilen öğreticiyi ve örnek kodu takip ederek, işlevsel yerel köprü metinleri güvenle oluşturabilirsiniz. Oluşturulan PDF belgesini açıp köprü metni üzerine tıklayarak bağlantıları test edebilirsiniz.

#### S: Yerel köprü metinlerini kullanırken herhangi bir sınırlama var mı?

A: Yerel köprü metinleri belge gezintisini geliştirmenin etkili bir yoludur, ancak belgenin yapısının açık ve sezgisel kalmasını sağlamak önemlidir. Uygun şekilde etiketlenen köprü metinleri ve bağlantılar olumlu bir kullanıcı deneyimine katkıda bulunur.

#### S: Tablolar veya resimler içerisinde yerel köprüler oluşturabilir miyim?

A: Evet, tablolar, resimler ve metin dahil olmak üzere PDF belgenizin çeşitli öğelerinde yerel köprüler oluşturabilirsiniz. Aspose.PDF for .NET, farklı içerik türlerine köprüler ekleme konusunda esneklik sunar.