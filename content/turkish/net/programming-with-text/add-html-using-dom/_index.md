---
title: DOM Kullanarak HTML Ekleme
linktitle: DOM Kullanarak HTML Ekleme
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET'te DOM kullanarak HTML içeriğini nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 40
url: /tr/net/programming-with-text/add-html-using-dom/
---
Bu eğitim, Aspose.PDF for .NET'te DOM (Belge Nesne Modeli) kullanarak HTML içeriği ekleme sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu gerekli adımları gösterir.

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
```

## 3. Adım: Belge dizinini ve çıktı dosyası yolunu ayarlayın
 Kodda yazan satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belgelerinizin saklandığı dizinin yolu ile birlikte.

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
 Bir örneği oluşturun`HtmlFragment` nesneyi oluşturun ve istenen HTML içeriğini sağlayın. Sağlanan kodda HTML içeriği değişkene atanır`titel`. HTML içeriğini gerektiği gibi değiştirebilirsiniz.

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

## Adım 7: Kenar boşluğu bilgilerini ayarlayın
Gerekirse HTML parçasının alt ve üst kenar boşluğunu ayarlayın. Verilen kodda alt kenar boşluğu 10, üst kenar boşluğu 200 olarak ayarlanmıştır.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 200;
```

## Adım 8: HtmlFragment'i sayfaya ekleyin
 Ekle`HtmlFragment` sayfanın paragraf koleksiyonuna itiraz edin.

```csharp
page.Paragraphs.Add(title);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

## 9. Adım: PDF belgesini kaydedin
 PDF belgesini kullanarak kaydedin.`Save` yöntemi`Document` nesne. 3. Adımda ayarladığınız çıktı dosyası yolunu belirtin.

```csharp
doc.Save(dataDir);
```

## 10. Adım: Başarı mesajını görüntüleyin
PDF dosyasının kaydedildiği yolla birlikte bir başarı mesajı görüntüleyin.

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET kullanarak DOM kullanarak HTML Ekleme için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge nesnesini somutlaştır
Document doc = new Document();
// PDF dosyasının sayfalar koleksiyonuna bir sayfa ekleyin
Page page = doc.Pages.Add();
// HTML içerikleriyle HtmlFragment örneğini oluşturma
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
// Alt kenar boşluğu bilgilerini ayarla
titel.Margin.Bottom = 10;
// Üst kenar boşluğu bilgilerini ayarla
titel.Margin.Top = 200;
// Sayfanın paragraf koleksiyonuna HTML Parçası ekleyin
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
// PDF dosyasını kaydet
doc.Save(dataDir);
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

## Çözüm
Aspose.PDF for .NET'te DOM kullanarak HTML içeriğini başarıyla eklediniz. Ortaya çıkan PDF dosyası artık belirtilen çıktı dosyası yolunda bulunabilir.

### SSS'ler

#### S: Bu eğitimin amacı nedir?

C: Bu eğitimin amacı Aspose.PDF for .NET'te Belge Nesne Modeli (DOM) kullanılarak bir PDF belgesine HTML içeriğinin nasıl ekleneceği konusunda adım adım bir kılavuz sağlamaktır. Süreci anlamanıza ve uygulamanıza yardımcı olacak C# kaynak kodu parçacıkları içerir.

#### S: Bu eğitim için hangi ad alanlarını içe aktarmam gerekiyor?

C: HTML içeriği eklemeyi planladığınız kod dosyasında, dosyanın başına aşağıdaki ad alanını içe aktarın:

```csharp
using Aspose.Pdf;
```

#### S: Belge dizinini ve çıktı dosyası yolunu nasıl belirlerim?

 A: Kodda satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

#### S: Bir Belge nesnesini nasıl oluşturabilirim?

 C: 4. Adımda yeni bir örnek oluşturun`Document` Aşağıdaki kod satırını ekleyerek nesne:

```csharp
Document doc = new Document();
```

#### S: Belgeye nasıl sayfa eklerim?

 C: 5. Adımda belgeye yeni bir sayfa ekleyeceksiniz.`Add` yöntemi`Pages` Toplamak:

```csharp
Page page = doc.Pages.Add();
```

#### S: DOM'u kullanarak HTML içeriğini nasıl ayarlayabilirim?

 C: 6. Adımda bir`HtmlFragment` nesnesini seçin ve ona istediğiniz HTML içeriğini atayın. HTML içeriği değişkene atanır`titel`:

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

#### S: HTML içeriğinin kenar boşluğunu ayarlayabilir miyim?

C: Evet, 7. Adımda HTML parçasının alt ve üst kenar boşluklarını gerektiği gibi ayarlayabilirsiniz:

```csharp
titel.Margin.Bottom = 10;
titel.Margin.Top = 200;
```

#### S: HTMLFragment'i PDF belgesine nasıl eklerim?

 C: 8. Adımda şunları ekleyeceksiniz:`HtmlFragment` nesne (`titel`) sayfanın paragraf koleksiyonuna:

```csharp
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

#### S: Ortaya çıkan PDF belgesini nasıl kaydederim?

 C: HTML içeriğini ekledikten ve kenar boşluklarını ayarladıktan sonra`Save` yöntemi`Document` PDF belgesini kaydetmek için nesne:

```csharp
doc.Save(dataDir);
```

#### S: Sürecin başarılı olup olmadığını doğrulamanın bir yolu var mı?

C: Elbette, 10. Adımda, PDF dosyasının kaydedildiği yolla birlikte bir başarı mesajı görüntülenir:

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

#### S: Bu eğitimden çıkarılacak önemli sonuç nedir?

C: Bu eğitimi takip ederek, bir PDF belgesine HTML içeriği eklemek için Aspose.PDF for .NET'teki Belge Nesne Modelini (DOM) nasıl kullanacağınızı başarıyla öğrendiniz. Bu bilgi, PDF oluşturma yeteneklerinizi geliştirmenize olanak sağlar.