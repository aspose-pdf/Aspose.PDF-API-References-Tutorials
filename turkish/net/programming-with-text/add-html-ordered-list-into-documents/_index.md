---
title: Belgelere HTML Sıralı Liste Ekleme
linktitle: Belgelere HTMLSıralı Liste Ekleme
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir belgeye HTML sıralı liste eklemeyi öğrenin.
type: docs
weight: 30
url: /tr/net/programming-with-text/add-html-ordered-list-into-documents/
---

Bu öğreticide, bir belgeye HTML sıralı liste eklemek için Aspose.PDF for .NET kitaplığının nasıl kullanılacağını öğreneceksiniz. Sağlanan kod, bu görevi gerçekleştirmek için gerekli adımları gösterir.

## Gereksinimler
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio veya makinenizde kurulu başka bir C# derleyicisi.
- Aspose.PDF for .NET kitaplığı. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet gibi bir paket yöneticisi kullanabilirsiniz.

## 1. Adım: Projeyi kurun
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın
HTML sıralı listesini eklemek istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki using yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3. Adım: Belge dizinini ve çıktı dosyası yolunu ayarlayın
 Kodda yazan satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belgelerinizin saklandığı dizinin yolu ile.

 Ardından, yazan satırı bulun`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` ve değiştir`"AddHTMLOrderedListIntoDocuments_out.pdf"` Çıktı PDF dosyanız için istediğiniz adla.

## 4. Adım: Yeni bir Belge nesnesi oluşturun
 Yeni bir örnek oluştur`Document` aşağıdaki kod satırını ekleyerek nesne:

```csharp
Document doc = new Document();
```

## Adım 5: HTML içeriğiyle bir HtmlFragment nesnesi oluşturun
Bir örneğini oluşturun`HtmlFragment` belgeye eklemek istediğiniz HTML içeriğine sahip nesne. Sağlanan kodda, HTML içeriği değişkene atanır.`t`. HTML içeriğini gerektiği gibi değiştirebilirsiniz.

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## 6. Adım: Belgeye bir sayfa ekleyin
 kullanarak belgeye yeni bir sayfa ekleyin.`Add` yöntemi`Pages` Toplamak. Sağlanan kodda, yeni sayfa değişkene atanır.`page`.

```csharp
Page page = doc.Pages.Add();
```

## 7. Adım: HtmlFragment'i sayfaya ekleyin
 Ekle`HtmlFragment` kullanarak sayfaya itiraz edin.`Add` yöntemi`Paragraphs` Toplamak.

```csharp
page.Paragraphs.Add(t);
```

## 8. Adım: PDF belgesini kaydedin
 Ortaya çıkan PDF dosyasını kullanarak kaydedin.`Save` yöntemi`Document` nesne. Adım 3'te ayarladığınız çıktı dosyası yolunu belirtin.

```csharp
doc.Save(outFile);
```

### Aspose.PDF for .NET kullanarak Belgelere HTMLSıralı Liste Ekleme için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Çıkış belgesinin yolu.
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// Belge nesnesini örneklendir
Document doc = new Document();
// Karşılık gelen HTML parçasıyla HtmlFragment nesnesini oluşturun
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// Sayfa Koleksiyonuna Sayfa Ekle
Page page = doc.Pages.Add();
// Sayfanın içine HtmlFragment ekleyin
page.Paragraphs.Add(t);
// Ortaya çıkan PDF dosyasını kaydet
doc.Save(outFile);
```

## Çözüm
Aspose.PDF for .NET kullanarak bir belgeye HTML sıralı listesini başarıyla eklediniz. Ortaya çıkan PDF dosyası artık belirtilen çıktı dosyası yolunda bulunabilir.

HTML içeriğini özelleştirmeyi ve kodu özel gereksinimlerinize göre ayarlamayı unutmayın.