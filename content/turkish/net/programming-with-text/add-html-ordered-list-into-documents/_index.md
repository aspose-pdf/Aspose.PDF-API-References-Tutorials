---
title: Belgelere HTML Sıralı Listesi Ekleme
linktitle: Belgelere HTML Sıralı Liste Ekleme
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak bir belgeye HTML sıralı listenin nasıl eklendiğini öğrenin.
type: docs
weight: 30
url: /tr/net/programming-with-text/add-html-ordered-list-into-documents/
---
Bu eğitimde, bir belgeye HTML sıralı liste eklemek için Aspose.PDF for .NET kitaplığını nasıl kullanacağınızı öğreneceksiniz. Sağlanan kod, bu görevi gerçekleştirmek için gerekli adımları gösterir.

## Gereksinimler
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Makinenizde kurulu Visual Studio veya başka herhangi bir C# derleyicisi.
- Aspose.PDF for .NET kitaplığı. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet gibi bir paket yöneticisi kullanabilirsiniz.

## 1. Adım: Projeyi ayarlayın
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın
HTML sıralı listesini eklemek istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki kullanma yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3. Adım: Belge dizinini ve çıktı dosyası yolunu ayarlayın
 Kodda yazan satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belgelerinizin saklandığı dizinin yolu ile birlikte.

 Daha sonra yazan satırı bulun`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` ve değiştir`"AddHTMLOrderedListIntoDocuments_out.pdf"` Çıktı PDF dosyanız için istediğiniz adla.

## 4. Adım: Yeni bir Belge nesnesi oluşturun
 Yeni bir örnek oluştur`Document` Aşağıdaki kod satırını ekleyerek nesne:

```csharp
Document doc = new Document();
```

## 5. Adım: HTML içeriğiyle bir HtmlFragment nesnesi oluşturun
 Bir örneği oluşturun`HtmlFragment` belgeye eklemek istediğiniz HTML içeriğini içeren nesneyi seçin. Sağlanan kodda HTML içeriği değişkene atanır`t`. HTML içeriğini gerektiği gibi değiştirebilirsiniz.

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## 6. Adım: Belgeye bir sayfa ekleyin
 kullanarak belgeye yeni bir sayfa ekleyin.`Add` yöntemi`Pages`Toplamak. Verilen kodda yeni sayfa değişkene atanır.`page`.

```csharp
Page page = doc.Pages.Add();
```

## Adım 7: HtmlFragment'i sayfaya ekleyin
 Ekle`HtmlFragment` kullanarak sayfaya itiraz edin.`Add` yöntemi`Paragraphs` Toplamak.

```csharp
page.Paragraphs.Add(t);
```

## Adım 8: PDF belgesini kaydedin
 Ortaya çıkan PDF dosyasını kullanarak kaydedin.`Save` yöntemi`Document` nesne. 3. Adımda ayarladığınız çıktı dosyası yolunu belirtin.

```csharp
doc.Save(outFile);
```

### Aspose.PDF for .NET kullanarak Belgelere HTML Sıralı Liste Eklemek için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Çıkış belgesinin yolu.
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// Belge nesnesini somutlaştır
Document doc = new Document();
// İlgili HTML parçasıyla HtmlFragment nesnesini örneklendirin
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// Sayfa Koleksiyonuna Sayfa Ekle
Page page = doc.Pages.Add();
// Sayfanın içine HtmlFragment ekle
page.Paragraphs.Add(t);
// Ortaya çıkan PDF dosyasını kaydedin
doc.Save(outFile);
```

## Çözüm
Aspose.PDF for .NET'i kullanarak bir belgeye HTML sıralı listeyi başarıyla eklediniz. Ortaya çıkan PDF dosyası artık belirtilen çıktı dosyası yolunda bulunabilir.

HTML içeriğini özelleştirmeyi ve kodu özel gereksinimlerinize göre ayarlamayı unutmayın.

### SSS'ler

#### S: Bu eğitimin amacı nedir?

C: Bu eğitimin amacı, Aspose.PDF for .NET kütüphanesini kullanarak bir belgeye HTML sıralı liste ekleme sürecinde size rehberlik etmektir. Bu görevi başarmanıza yardımcı olacak adım adım talimatlar ve kod parçacıkları sağlar.

#### S: Bu eğitim için hangi ad alanlarını içe aktarmam gerekiyor?

C: Kod dosyanızın en üstüne aşağıdaki ad alanlarını içe aktarmanız gerekir:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### S: Belge dizinini ve çıktı dosyası yolunu nasıl belirlerim?

 A: Kodda satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile. Ayrıca satırı bulun`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` ve değiştir`"AddHTMLOrderedListIntoDocuments_out.pdf"` İstediğiniz çıktı PDF dosya adı ile.

#### S: Belgeye eklenen HTML içeriğini özelleştirebilir miyim?

 C: Kesinlikle! 5. Adımda, bir`HtmlFragment` adlı nesne`t` HTML içeriğini tutan. Gereksinimlerinize uyacak şekilde geri tıklamaların içindeki HTML içeriğini değiştirebilirsiniz.

#### S: HTML sıralı listesini belgedeki bir sayfaya nasıl eklerim?

 C: 7. Adımda şunu ekleyeceksiniz:`HtmlFragment` nesne (`t` ) kullanarak sayfaya`Add` yöntemi`Paragraphs`Toplamak. Bu, HTML sıralı listesini belgeye sorunsuz bir şekilde entegre edecektir.

#### S: Ortaya çıkan PDF belgesini nasıl kaydederim?

 C: HTML içeriğini ekleyip bir sayfada düzenledikten sonra, PDF belgesini kullanarak kaydedebilirsiniz.`Save` yöntemi`Document` nesne. Daha önce ayarladığınız doğru çıktı dosyası yolunu sağladığınızdan emin olun.

#### S: Referans olması açısından örnek kaynak kodunun bir özetini sunabilir misiniz?

C: Kesinlikle! Bu eğitimde sağlanan örnek kaynak kodunun özetlenmiş bir sürümünü burada bulabilirsiniz:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
Document doc = new Document();
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
Page page = doc.Pages.Add();
page.Paragraphs.Add(t);
doc.Save(outFile);
```

#### S: Bu eğitimden çıkarılacak önemli sonuç nedir?

C: Bu eğitimi takip ederek, HTML sıralı bir listeyi bir belgeye dahil etmek için Aspose.PDF for .NET kütüphanesinden nasıl yararlanacağınızı başarıyla öğrendiniz. Bu yeni keşfedilen bilgi, belge oluşturma ve işleme süreçlerinizi geliştirmek için uygulanabilir.