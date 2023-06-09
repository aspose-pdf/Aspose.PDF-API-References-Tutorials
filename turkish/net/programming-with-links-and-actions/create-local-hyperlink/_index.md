---
title: Yerel Köprü Oluştur
linktitle: Yerel Köprü Oluştur
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF dosyasında kolayca yerel köprüler oluşturun.
type: docs
weight: 40
url: /tr/net/programming-with-links-and-actions/create-local-hyperlink/
---

Bir PDF dosyasında yerel köprüler oluşturmak, kullanıcıları aynı PDF belgesindeki diğer sayfalara götüren tıklanabilir bağlantılar oluşturmanıza olanak tanır. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu izleyerek bu tür bağlantıları kolayca oluşturabilirsiniz:

## 1. Adım: Gerekli Kitaplıkları İçe Aktarın

Başlamadan önce, C# projeniz için gerekli kitaplıkları içe aktarmanız gerekir. İşte gerekli ithalat yönergesi:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda, ortaya çıkan PDF dosyasını kaydetmek istediğiniz klasörün yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeler klasörünüzün gerçek yolu ile aşağıdaki kodda:

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
// Sayfanın paragraf koleksiyonuna metin ekleyin
page.Paragraphs.Add(text);
// Yeni TextFragment örneği oluştur
text = new TextFragment("link page number test to page 1");
// TextFragment yeni sayfaya eklenmelidir
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