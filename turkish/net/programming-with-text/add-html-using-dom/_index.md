---
title: DOM Kullanarak HTML Ekleme
linktitle: DOM Kullanarak HTML Ekleme
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET'te DOM kullanarak HTML içeriği eklemeyi öğrenin.
type: docs
weight: 40
url: /tr/net/programming-with-text/add-html-using-dom/
---

Bu eğitim, Aspose.PDF for .NET'te DOM (Belge Nesne Modeli) kullanarak HTML içeriği ekleme sürecinde size rehberlik edecektir. Sağlanan C# kaynak kodu, gerekli adımları gösterir.

## Gereksinimler
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio veya makinenizde kurulu başka bir C# derleyicisi.
- Aspose.PDF for .NET kitaplığı. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet gibi bir paket yöneticisi kullanabilirsiniz.

## 1. Adım: Projeyi kurun
1. Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun.
2. Aspose.PDF for .NET kitaplığına bir referans ekleyin.

## 2. Adım: Gerekli ad alanlarını içe aktarın
HTML içeriğini eklemek istediğiniz kod dosyasında, dosyanın en üstüne aşağıdaki using yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
```

## 3. Adım: Belge dizinini ve çıktı dosyası yolunu ayarlayın
 Kodda yazan satırı bulun`string dataDir = "YOUR DOCUMENT DIRECTORY";` ve değiştir`"YOUR DOCUMENT DIRECTORY"` belgelerinizin saklandığı dizinin yolu ile.

## 4. Adım: Yeni bir Belge nesnesi oluşturun
 Yeni bir örnek oluştur`Document` aşağıdaki kod satırını ekleyerek nesne:

```csharp
Document doc = new Document();
```

## 5. Adım: Belgeye bir sayfa ekleyin
 kullanarak belgeye yeni bir sayfa ekleyin.`Add` yöntemi`Pages` Toplamak. Sağlanan kodda, yeni sayfa değişkene atanır.`page`.

```csharp
Page page = doc.Pages.Add();
```

## 6. Adım: HTML içeriğiyle bir HtmlFragment oluşturun
 Bir örneğini oluşturun`HtmlFragment` nesne ve istenen HTML içeriğini sağlayın. Sağlanan kodda, HTML içeriği değişkene atanır.`titel`. HTML içeriğini gerektiği gibi değiştirebilirsiniz.

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

## 7. Adım: Kenar boşluğu bilgilerini ayarlayın
Gerekirse HTML parçasının alt ve üst kenar boşluğunu ayarlayın. Sağlanan kodda, alt kenar boşluğu 10 ve üst kenar boşluğu 200 olarak ayarlanmıştır.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 200;
```

## Adım 8: HtmlFragment'i sayfaya ekleyin
 Ekle`HtmlFragment` sayfanın paragraflar koleksiyonuna itiraz.

```csharp
page.Paragraphs.Add(title);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

## 9. Adım: PDF belgesini kaydedin
 kullanarak PDF belgesini kaydedin.`Save` yöntemi`Document` nesne. Adım 3'te ayarladığınız çıktı dosyası yolunu belirtin.

```csharp
doc.Save(dataDir);
```

## 10. Adım: Başarı mesajını görüntüleyin
PDF dosyasının kaydedildiği yolla birlikte bir başarı mesajı görüntüleyin.

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

### Aspose.PDF for .NET kullanarak DOM Kullanarak HTML Ekleme için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belge nesnesini örneklendir
Document doc = new Document();
// PDF dosyasının sayfalar koleksiyonuna bir sayfa ekleyin
Page page = doc.Pages.Add();
// HtmlFragment'i HTML içerikleriyle örnekleyin
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