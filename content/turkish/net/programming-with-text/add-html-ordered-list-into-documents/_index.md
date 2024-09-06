---
title: Belgelere HTML Sıralı Liste Ekleme
linktitle: Belgelere HTMLOrdered Liste Ekleme
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir belgeye HTML sıralı liste eklemeyi öğrenin.
type: docs
weight: 30
url: /tr/net/programming-with-text/add-html-ordered-list-into-documents/
---
Bu eğitimde, bir belgeye HTML sıralı liste eklemek için Aspose.PDF for .NET kitaplığını nasıl kullanacağınızı öğreneceksiniz. Sağlanan kod, bu görevi gerçekleştirmek için gerekli adımları göstermektedir.

## Gereksinimler
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Bilgisayarınızda Visual Studio veya herhangi bir C# derleyicisi yüklü olmalıdır.
- Aspose.PDF for .NET kütüphanesi. Resmi Aspose web sitesinden indirebilir veya NuGet gibi bir paket yöneticisi kullanarak kurabilirsiniz.

## Adım 1: Projeyi kurun
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. .NET için Aspose.PDF kitaplığına bir referans ekleyin.

## Adım 2: Gerekli ad alanlarını içe aktarın
HTML sıralı listesini eklemek istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki using yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Adım 3: Belge dizinini ve çıktı dosyası yolunu ayarlayın
 Kodda şu satırı bulun:`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` Belgelerinizin saklandığı dizinin yolunu içeren.

 Sonra, şunu söyleyen satırı bulun:`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` ve değiştir`"AddHTMLOrderedListIntoDocuments_out.pdf"` Çıktı PDF dosyanız için istediğiniz ismi yazın.

## Adım 4: Yeni bir Belge nesnesi oluşturun
 Yeni bir örnek oluştur`Document` Aşağıdaki kod satırını ekleyerek nesneyi oluşturun:

```csharp
Document doc = new Document();
```

## Adım 5: HTML içeriğiyle bir HtmlFragment nesnesi oluşturun
 Bir örnek oluştur`HtmlFragment` Belgeye eklemek istediğiniz HTML içeriğine sahip nesne. Sağlanan kodda, HTML içeriği değişkene atanır`t`HTML içeriğini ihtiyacınıza göre değiştirebilirsiniz.

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## Adım 6: Belgeye bir sayfa ekleyin
 Belgeye yeni bir sayfa eklemek için şunu kullanın:`Add` yöntemi`Pages`koleksiyon. Sağlanan kodda, yeni sayfa değişkene atanır`page`.

```csharp
Page page = doc.Pages.Add();
```

## Adım 7: HtmlFragment'ı sayfaya ekleyin
 Ekle`HtmlFragment` sayfaya nesneyi kullanarak`Add` yöntemi`Paragraphs` koleksiyon.

```csharp
page.Paragraphs.Add(t);
```

## Adım 8: PDF belgesini kaydedin
 Elde edilen PDF dosyasını kullanarak kaydedin`Save` yöntemi`Document` nesne. Adım 3'te ayarladığınız çıktı dosyası yolunu belirtin.

```csharp
doc.Save(outFile);
```

### .NET için Aspose.PDF kullanarak Belgelere HTMLOrdered Liste Eklemek için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Çıktı belgesinin yolu.
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// Belge nesnesini örnekle
Document doc = new Document();
// HtmlFragment nesnesini karşılık gelen HTML parçasıyla örnekleyin
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// Sayfalar Koleksiyonuna Sayfa Ekle
Page page = doc.Pages.Add();
// Sayfanın içine HtmlFragment ekleyin
page.Paragraphs.Add(t);
// Sonuç PDF dosyasını kaydedin
doc.Save(outFile);
```

## Çözüm
Aspose.PDF for .NET kullanarak bir belgeye HTML sıralı bir liste başarıyla eklediniz. Elde edilen PDF dosyası artık belirtilen çıktı dosyası yolunda bulunabilir.

HTML içeriğini özelleştirmeyi ve kodu özel gereksinimlerinize göre ayarlamayı unutmayın.

### SSS

#### S: Bu eğitimin amacı nedir?

A: Bu eğitim, Aspose.PDF for .NET kitaplığını kullanarak bir belgeye HTML sıralı liste ekleme sürecinde size rehberlik etmeyi amaçlamaktadır. Bu görevi başarmanıza yardımcı olmak için adım adım talimatlar ve kod parçacıkları sağlar.

#### S: Bu eğitim için hangi ad alanlarını içe aktarmam gerekiyor?

A: Kod dosyanızın en üstüne aşağıdaki ad alanlarını içe aktarmanız gerekir:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### S: Belge dizinini ve çıktı dosyası yolunu nasıl belirtirim?

 A: Kodda şu satırı bulun:`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belge dizininize giden gerçek yol ile. Ayrıca, şu satırı bulun`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` ve değiştir`"AddHTMLOrderedListIntoDocuments_out.pdf"` İstediğiniz çıktı PDF dosya adıyla.

#### S: Belgeye eklenen HTML içeriğini özelleştirebilir miyim?

 A: Kesinlikle! 5. Adımda bir`HtmlFragment` isimli nesne`t` HTML içeriğini tutan. Backtick'ler içindeki HTML içeriğini ihtiyaçlarınıza uyacak şekilde değiştirebilirsiniz.

#### S: Belgedeki bir sayfaya HTML sıralı listesini nasıl eklerim?

 A: 7. Adımda şunları ekleyeceksiniz:`HtmlFragment` nesne (`t` ) kullanarak sayfaya`Add` yöntemi`Paragraphs`koleksiyon. Bu, HTML sıralı listesini belgeye sorunsuz bir şekilde entegre edecektir.

#### S: Ortaya çıkan PDF belgesini nasıl kaydedebilirim?

 A: HTML içeriğini ekledikten ve bir sayfaya düzenledikten sonra, PDF belgesini şu şekilde kaydedebilirsiniz:`Save` yöntemi`Document` nesne. Daha önce ayarladığınız doğru çıktı dosyası yolunu sağladığınızdan emin olun.

#### S: Referans olması açısından örnek kaynak kodunun bir özetini verebilir misiniz?

A: Elbette! İşte bu eğitimde sağlanan örnek kaynak kodunun özetlenmiş bir versiyonu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
Document doc = new Document();
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
Page page = doc.Pages.Add();
page.Paragraphs.Add(t);
doc.Save(outFile);
```

#### S: Bu eğitimden çıkarılacak en önemli ders nedir?

A: Bu öğreticiyi takip ederek, bir HTML sıralı listesini bir belgeye dahil etmek için Aspose.PDF for .NET kitaplığından nasıl yararlanacağınızı başarıyla öğrendiniz. Bu yeni edinilen bilgi, belge oluşturma ve düzenleme süreçlerinizi geliştirmek için uygulanabilir.