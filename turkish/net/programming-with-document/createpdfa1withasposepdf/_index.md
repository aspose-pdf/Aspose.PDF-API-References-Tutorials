---
title: Aspose Pdf ile PDF A1 Oluşturun
linktitle: Aspose Pdf ile PDF A1 Oluşturun
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF A1 belgesi oluşturmayı öğrenin. C# kaynak koduyla adım adım kılavuz. PDF'leri verimli bir şekilde optimize edin.
type: docs
weight: 90
url: /tr/net/programming-with-document/createpdfa1withasposepdf/
---

Bu adım adım kılavuzda, bir PDF A1 belgesi oluşturmak için Aspose.PDF for .NET'in nasıl kullanılacağını açıklayacağız. Bu görevi gerçekleştirmek için size gerekli C# kaynak kodunu ve talimatları sağlayacağız.

## 1. Adım: Değişkenleri tanımlayın ve ad alanlarını içe aktarın

 İlk olarak, değişkeni tanımlayın`dataDir` belgelerinizin saklandığı dizini temsil etmek için. Bu, çıktı dosyası yolunu belirtmek için kullanılacaktır.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ardından, yeni bir örneğini oluşturun`Document` Aspose.PDF'den sınıf.

```csharp
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

## 2. Adım: PDF'ye içerik ekleyin

Bu adımda, PDF belgesine bir sayfa ekleyeceğiz ve "Merhaba Dünya!" metnini içeren bir metin parçası ekleyeceğiz.

```csharp
pdf1.Pages.Add().Paragraphs.Add(new TextFragment("Hello World!"));
```

## 3. Adım: PDF'yi bir bellek akışına kaydedin

PDF'yi PDF/A1 formatına dönüştürmek için onu bir bellek akışına kaydetmemiz gerekiyor.

```csharp
MemoryStream ms = new MemoryStream();
pdf1.Save(ms);
```

## 4. Adım: PDF'yi PDF/A1 biçimine dönüştürün

 Şimdi, PDF'yi kullanarak PDF/A1 formatına dönüştüreceğiz.`Convert` yöntemi`Document` sınıf. Çıkış akışı olarak yeni bir bellek akışı geçiriyoruz ve`PdfFormat.PDF_A_1A` biçim.

```csharp
pdf1.Convert(new MemoryStream(), PdfFormat.PDF_A_1A, ConvertErrorAction.Delete);
```

## 5. Adım: Dönüştürülen PDF'yi kaydedin

Son olarak, dönüştürülen PDF'yi belirtilen dizine kaydedin.

```csharp
pdf1.Save(dataDir + "CreatePdfA1_out.pdf");
```

### Aspose.PDF for .NET kullanarak PDF A1 Oluşturma için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// pdf belgesine bir sayfa ekleyin
pdf1.Pages.Add().Paragraphs.Add(new TextFragment("Hello World!"));
MemoryStream ms = new MemoryStream();
// belgeyi kaydet
pdf1.Save(ms);
pdf1.Convert(new MemoryStream(), PdfFormat.PDF_A_1A, ConvertErrorAction.Delete);
pdf1.Save(dataDir + "CreatePdfA1_out.pdf");
```

Bu adımları izleyerek ve sağlanan kaynak kodunu kullanarak, Aspose.PDF for .NET kullanarak bir PDF A1 belgesi oluşturabilirsiniz.

Çıktı dosyasını kaydetmek istediğiniz uygun dizin yolu ile "BELGE DİZİNİNİZİ" ayarlamayı unutmayın.


