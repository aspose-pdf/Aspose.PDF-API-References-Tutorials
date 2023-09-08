---
title: DOM ve PDF Üzerine Yazma Kullanarak HTML Ekleme
linktitle: DOM Kullanarak HTML Ekleme ve Üzerine Yazma
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'te DOM ve PDF üzerine yazma kullanarak HTML içeriğini nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 50
url: /tr/net/programming-with-text/add-html-using-dom-and-overwrite/
---
Bu eğitim, Aspose.PDF for .NET'te DOM (Belge Nesne Modeli) kullanarak HTML içeriği ekleme sürecinde size rehberlik edecektir. Ayrıca HTML içeriğinin stillerinin üzerine nasıl yazılacağını da öğreneceksiniz. Sağlanan C# kaynak kodu gerekli adımları gösterir.

## Gereksinimler
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Makinenizde kurulu Visual Studio veya başka herhangi bir C# derleyicisi.
- Aspose.PDF for .NET kitaplığı. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet gibi bir paket yöneticisi kullanabilirsiniz.

## 1. Adım: Projeyi ayarlayın
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın
HTML içeriğini eklemek istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki kullanma yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3. Adım: Belge dizinini ve çıktı dosyası yolunu ayarlayın
 Kodda yazan satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belgelerinizin saklandığı dizinin yolu ile birlikte.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 4. Adım: Yeni bir Belge nesnesi oluşturun
 Yeni bir örnek oluştur`Document` Aşağıdaki kod satırını ekleyerek nesne:

```csharp
Document doc = new Document();
```

## 5. Adım: Belgeye bir sayfa ekleyin
 kullanarak belgeye yeni bir sayfa ekleyin.`Add` yöntemi`Pages`Toplamak. Verilen kodda yeni sayfa değişkene atanır.`page`.

```csharp
Page page = doc.Pages.Add();
```

## 6. Adım: HTML içeriğiyle bir HtmlFragment oluşturun
 Bir örneği oluşturun`HtmlFragment` nesneyi oluşturun ve istenen HTML içeriğini sağlayın. Sağlanan kodda HTML içeriği değişkene atanır`title`. HTML içeriğini gerektiği gibi değiştirebilirsiniz.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## 7. Adım: HTML içeriğinin stillerinin üzerine yazın
 HTML içeriğinin stillerinin üzerine yazmak için`TextState` özellikleri`HtmlFragment` nesne. Verilen kodda yazı tipi ailesi "Arial" olarak değiştirilmiş ve yazı tipi boyutu 20 olarak ayarlanmıştır.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## Adım 8: Kenar boşluğu bilgilerini ayarlayın
Gerekirse HTML parçasının alt ve üst kenar boşluklarını ayarlayın. Verilen kodda alt kenar boşluğu 10, üst kenar boşluğu 400 olarak ayarlanmıştır.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## 9. Adım: HtmlFragment'i sayfaya ekleyin
 Ekle`HtmlFragment` sayfanın paragraf koleksiyonuna itiraz edin.

```csharp
page.Paragraphs.Add(title);
```

## Adım 10: PDF belgesini kaydedin
 PDF belgesini kullanarak kaydedin.`Save` yöntemi`Document` nesne. 3. Adımda ayarladığınız çıktı dosyası yolunu belirtin.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### Aspose.PDF for .NET Kullanarak HTML Ekleme ve Üzerine Yazma için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge nesnesini somutlaştır
Document doc = new Document();
// PDF dosyasının sayfalar koleksiyonuna bir sayfa ekleyin
Page page = doc.Pages.Add();
// HTML içerikleriyle HtmlFragment örneğini oluşturma
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//'Verdana'daki yazı tipi ailesi 'Arial' olarak sıfırlanacak
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// Alt kenar boşluğu bilgilerini ayarla
title.Margin.Bottom = 10;
// Üst kenar boşluğu bilgilerini ayarla
title.Margin.Top = 400;
// Sayfanın paragraf koleksiyonuna HTML Parçası ekleyin
page.Paragraphs.Add(title);
// PDF dosyasını kaydet
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// PDF dosyasını kaydet
doc.Save(dataDir);
```

## Çözüm
Aspose.PDF for .NET'te DOM kullanarak HTML içeriğini başarıyla eklediniz ve HTML içeriğinin stillerinin üzerine yazdınız. Ortaya çıkan PDF dosyası artık belirtilen çıktı dosyası yolunda bulunabilir.

### SSS'ler

#### S: Bu eğitimin odak noktası nedir?

C: Bu eğitim, Aspose.PDF for .NET'teki Belge Nesne Modeli'ni (DOM) kullanarak bir PDF belgesine HTML içeriği ekleme sürecinde size yol göstermek için tasarlanmıştır. Ek olarak, HTML içeriğinin stillerinin üzerine nasıl yazılacağını da öğreneceksiniz, böylece görünümünü özelleştirebileceksiniz. Öğretici, gerekli adımları göstermek için C# kaynak kodu parçacıkları sağlar.

#### S: Bu eğitim için hangi ad alanlarını içe aktarmam gerekiyor?

C: HTML içeriği eklemeyi planladığınız kod dosyasında, dosyanın başına aşağıdaki ad alanlarını içe aktarın:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### S: Belge dizinini ve çıktı dosyası yolunu nasıl belirlerim?

 A: Kodda satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

#### S: Bir Belge nesnesini nasıl oluşturabilirim?

 C: 4. Adımda yeni bir örnek oluşturacaksınız.`Document` aşağıdaki kod satırını kullanarak nesne:

```csharp
Document doc = new Document();
```

#### S: Belgeye nasıl sayfa eklerim?

 C: 5. Adımda belgeye yeni bir sayfa ekleyeceksiniz.`Add` yöntemi`Pages` Toplamak:

```csharp
Page page = doc.Pages.Add();
```

#### S: DOM'u kullanarak HTML içeriğini nasıl ayarlayabilirim?

 C: 6. Adımda bir`HtmlFragment` nesnesini seçin ve ona istediğiniz HTML içeriğini atayın. HTML içeriği değişkene atanır`title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### S: HTML içeriğinin stillerinin üzerine nasıl yazabilirim?

 C: 7. Adımda, HTML içeriğini değiştirerek stillerin üzerine yazacaksınız.`TextState` özellikleri`HtmlFragment` nesne. Örneğin yazı tipi ailesini "Arial" olarak değiştirebilir ve yazı tipi boyutunu 20 olarak ayarlayabilirsiniz:

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### S: HTML içeriğinin kenar boşluğunu ayarlayabilir miyim?

C: Evet, 8. Adımda HTML parçasının alt ve üst kenar boşluklarını gerektiği gibi ayarlayabilirsiniz:

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### S: HtmlFragment'i PDF belgesine nasıl eklerim?

 C: 9. Adımda şunu ekleyeceksiniz:`HtmlFragment` nesne (`title`) sayfanın paragraf koleksiyonuna:

```csharp
page.Paragraphs.Add(title);
```

#### S: Ortaya çıkan PDF belgesini nasıl kaydederim?

 C: HTML içeriğini ekledikten ve stillerini özelleştirdikten sonra`Save` yöntemi`Document` PDF belgesini kaydetmek için nesne:

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### S: Bu eğitimden çıkarılacak önemli sonuç nedir?

C: Bu eğitimi takip ederek Aspose.PDF for .NET'te Belge Nesne Modeli (DOM) kullanarak HTML içeriğini nasıl dahil edeceğinizi başarıyla öğrendiniz. Ek olarak, ortaya çıkan PDF belgesindeki HTML içeriğinin görünümünü uyarlamak için stillerin üzerine yazma yeteneğini de kazandınız.