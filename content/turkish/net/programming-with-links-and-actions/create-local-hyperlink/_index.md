---
title: PDF Dosyasında Yerel Köprü Oluşturun
linktitle: PDF Dosyasında Yerel Köprü Oluşturun
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'i kullanarak PDF dosyasında kolayca yerel köprüler oluşturun.
type: docs
weight: 40
url: /tr/net/programming-with-links-and-actions/create-local-hyperlink/
---
PDF dosyasında yerel köprüler oluşturmak, kullanıcıları aynı PDF belgesindeki diğer sayfalara yönlendiren tıklanabilir bağlantılar oluşturmanıza olanak tanır. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu izleyerek bu tür bağlantıları kolayca oluşturabilirsiniz:

## 1. Adım: Gerekli Kitaplıkları İçe Aktarın

Başlamadan önce C# projeniz için gerekli kütüphaneleri içe aktarmanız gerekir. Gerekli ithalat direktifi aşağıdadır:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda, ortaya çıkan PDF dosyasını kaydetmek istediğiniz klasörün yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"`belgeler klasörünüzün gerçek yolunu içeren aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3. Adım: Belgenin bir örneğini oluşturun

 Bunun bir örneğini oluşturacağız`Document` PDF belgemizi temsil edecek sınıf. İşte ilgili kod:

```csharp
Document doc = new Document();
```

## 4. Adım: Köprülerle sayfa ve metin ekleyin

Bu adımda PDF belgemize bir sayfa ekleyeceğiz ve yerel köprüler içeren bazı metinler ekleyeceğiz. Her bağlantı için hedef sayfaları tanımlayacağız. İşte ilgili kod:

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

 Şimdi güncellenen PDF dosyasını kullanarak kaydedelim.`Save` yöntemi`doc` nesne. İşte ilgili kod:

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
// Bağlantı örneği için hedef sayfayı ayarlayın
link.TargetPageNumber = 7;
// TextFragment köprüsünü ayarla
text.Hyperlink = link;
//Sayfanın paragraf koleksiyonuna metin ekleme
page.Paragraphs.Add(text);
// Yeni TextFragment örneği oluştur
text = new TextFragment("link page number test to page 1");
// TextFragment yeni sayfaya eklenmelidir
text.IsInNewPage = true;
// Başka bir yerel köprü örneği oluşturun
link = new LocalHyperlink();
// İkinci köprü için Hedef sayfayı ayarlayın
link.TargetPageNumber = 1;
// İkinci TextFragment için bağlantıyı ayarla
text.Hyperlink = link;
// Sayfa nesnesinin paragraf koleksiyonuna metin ekleme
page.Paragraphs.Add(text);    
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
// Güncellenen belgeyi kaydet
doc.Save(dataDir);
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);            
```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF'de yerel köprüler oluşturmak için adım adım kılavuza sahipsiniz. Kullanıcıları aynı belgedeki diğer sayfalara yönlendiren tıklanabilir bağlantılar oluşturmak için bu kodu kullanabilirsiniz.

Gelişmiş köprü oluşturma özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine göz atmayı unutmayın.

### PDF dosyasında yerel köprü oluşturmaya ilişkin SSS

#### S: PDF dosyasındaki yerel köprüler nelerdir?

C: Bir PDF dosyasındaki yerel köprüler, kullanıcıları aynı belge içindeki farklı sayfalara yönlendiren tıklanabilir bağlantılardır. Bu bağlantılar gezinmeyi geliştirir ve okuyucuların ilgili bölümlere hızlı bir şekilde erişmesine olanak tanır.

#### S: Yerel köprüler PDF belgeme nasıl fayda sağlayabilir?

C: Yerel köprüler, ilgili içeriği aynı PDF belgesine bağlamak için etkili bir yol sağlar. Okuyucuların tüm belgeyi kaydırmadan belirli bölümlere hızlı bir şekilde atlamasını sağlayarak kullanıcı deneyimini geliştirir.

#### S: Aspose.PDF for .NET yerel köprülerin oluşturulmasını nasıl destekliyor?
C: Aspose.PDF for .NET, yerel köprüler oluşturmak için kapsamlı destek sunar. Bu kılavuzda sağlanan adım adım eğitim, C# kullanarak PDF belgenize yerel köprülerin nasıl ekleneceğini gösterir.

#### S: Yerel köprülerin görünümünü özelleştirebilir miyim?

C: Evet, belgenizin tasarımıyla eşleştiğinden ve tutarlı bir görsel deneyim sağladığından emin olmak için yerel köprülerin görünümünü metin rengi ve stili dahil olmak üzere özelleştirebilirsiniz.

#### S: Tek bir PDF sayfasında birden çok yerel köprü oluşturmak mümkün müdür?

C: Kesinlikle! Tek bir PDF sayfasında birden fazla yerel köprü oluşturarak okuyucuların ihtiyaç duydukları çeşitli bölümlere veya sayfalara atlamalarına olanak tanıyabilirsiniz. Her yerel köprü, ilgili hedefine göre uyarlanabilir.

#### S: Yerel köprüleri kullanarak bir sayfanın belirli bölümlerine bağlantı verebilir miyim?

C: Yerel köprüler genellikle sayfaların tamamına giderken, hedeflenen bağlantılara ulaşmak için PDF belgenizde bağlantılar veya yer imleri oluşturabilirsiniz. Aspose.PDF for .NET çeşitli köprü oluşturma seçeneklerini destekler.

#### S: Yerel köprülerimin düzgün çalıştığını nasıl doğrulayabilirim?

C: Sağlanan öğreticiyi ve örnek kodu takip ederek, işlevsel yerel köprüleri güvenle oluşturabilirsiniz. Oluşturulan PDF belgesini açıp köprü bağlantılı metne tıklayarak bağlantıları test edebilirsiniz.

#### S: Yerel köprüleri kullanırken herhangi bir sınırlama var mı?

C: Yerel köprüler belgede gezinmeyi geliştirmenin etkili bir yoludur, ancak belgenin yapısının açık ve sezgisel kalmasını sağlamak önemlidir. Düzgün etiketlenmiş köprüler ve bağlantılar olumlu bir kullanıcı deneyimine katkıda bulunur.

#### S: Tablolar veya resimler içinde yerel köprüler oluşturabilir miyim?

C: Evet, PDF belgenizin tablolar, resimler ve metin dahil çeşitli öğelerinde yerel köprüler oluşturabilirsiniz. Aspose.PDF for .NET, farklı içerik türlerine köprü ekleme konusunda esneklik sunar.