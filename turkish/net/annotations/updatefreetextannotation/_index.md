---
title: Serbest Metin Açıklamasını Güncelle
linktitle: Serbest Metin Açıklamasını Güncelle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET'in ücretsiz metin açıklaması özelliğini C# kaynak kodunu kullanarak nasıl güncelleyeceğinizi öğrenin.
type: docs
weight: 160
url: /tr/net/annotations/updatefreetextannotation/
---
Bu yazıda, Aspose.PDF for .NET'in Serbest Metin Ek Açıklamasını Güncelle özelliğinin aşağıdaki C# kaynak kodunu açıklamak için adım adım bir kılavuz sağlayacağız. Yeni başlayanların bile anlayabilmesi için her bir kod satırını inceleyeceğiz ve ne işe yaradığını açıklayacağız.

Şimdi yukarıdaki kodun her bir satırını adım adım açıklayalım:

## 1. Adım: Belge dizinini ayarlama

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Bu satırda güncellemek istediğimiz PDF belgesinin bulunduğu dizine giden yolu ayarlıyoruz.

## 2. Adım: PDF belgesini açma

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

Burada Aspose.PDF'leri kullanarak PDF belgesini açıyoruz.`Document` sınıfı ve giriş PDF dosyasının yolunu belirtme.

## 3. Adım: Serbest metin açıklamasının yazı tipi boyutunu ve rengini güncelleme

```csharp
(doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.FontSize = 18;
(doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.Color = System.Drawing.Color.Green;
```

 Bu adımda, PDF belgesinin ikinci sayfasındaki ilk serbest metin notunun yazı tipi boyutunu ve rengini güncelliyoruz. Bunu şu adrese erişerek yapıyoruz:`TextStyle` mülkiyeti`FreeTextAnnotation` nesne ve onun ayarlanması`FontSize` Ve`Color` özellikleri sırasıyla 18 ve Yeşil olarak ayarlayın.

## 4. Adım: İstisnaları Ele Alma

```csharp
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

 bu bir standart`try-catch` kod yürütülürken oluşabilecek istisnaları yakalayan ve hata mesajını konsola yazdıran blok.

### Aspose.PDF for .NET kullanarak Serbest Metin Ek Açıklamasını Güncellemek için örnek kaynak kodu

Kodun açıklamasına geçmeden önce kodun kendisine bir göz atalım. Bu kod örneği, Aspose.PDF for .NET kullanılarak bir PDF belgesindeki serbest metin açıklamasının özelliklerinin nasıl güncelleneceğini gösterir.

```csharp
try
{
    // Belgeler dizininin yolu.
    string dataDir = "YOUR DOCUMENT DIRECTORY";

    // Belgeyi aç
    Document doc1 = new Document(dataDir + "input.pdf");

    // Ek açıklamanın yazı tipi boyutunu ve rengini ayarlayın:
    (doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.FontSize = 18;
    (doc1.Pages[1].Annotations[0] as FreeTextAnnotation).TextStyle.Color = System.Drawing.Color.Green;
                
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

## Çözüm

Bu makalede, Aspose.PDF for .NET'in Serbest Metin Ek Açıklamasını Güncelle özelliğinin C# kaynak kodunu açıklayan adım adım bir kılavuz sağladık. Bu adımları izleyerek, Aspose.PDF for .NET kullanarak PDF belgelerinizdeki serbest metin notlarının yazı tipi boyutunu ve rengini kolayca güncelleyebilirsiniz.