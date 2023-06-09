---
title: Damga Notundan Metni Çıkarın
linktitle: Damga Notundan Metni Çıkarın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerinizdeki bir damga notundan kolayca nasıl metin çıkaracağınızı öğrenin.
type: docs
weight: 80
url: /tr/net/programming-with-stamps-and-watermarks/extract-text-from-stamp-annotation/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesindeki damga notundan nasıl metin çıkaracağınızı adım adım anlatacağız. PDF belgesinin belirli bir sayfasındaki belirli bir damga notundan metni çıkarmak için sağlanan C# kaynak kodunu nasıl kullanacağınızı göstereceğiz.

## 1. Adım: Ortamı ayarlama

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Yüklü bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kitaplığı indirildi ve projenizde referans verildi.

## 2. Adım: PDF belgesini yükleme

İlk adım, mevcut PDF belgesini projenize yüklemektir. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// belgeyi yükle
Document doc = new Document(dataDir + "test.pdf");
```

"BELGELER DİZİNİNİZİ", PDF belgenizin bulunduğu dizinin gerçek yolu ile değiştirdiğinizden emin olun.

## 3. Adım: Damga notundan metni çıkarın

Artık PDF belgesini yüklediğinize göre, belirli damga notundan metni çıkarabilirsiniz. İşte nasıl:

```csharp
// Arabellek ek açıklamasını al
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;

// Bir metin emici oluşturun
TextAbsorber ta = new TextAbsorber();

// Ek açıklamanın görünümünü ziyaret edin
XForm ap = annot. Appearance["N"];
ta.Visit(ap);

// Ayıklanan metni göster
Console.WriteLine(ta.Text);
```

Yukarıdaki kod, PDF belgesinin belirtilen sayfasından damga ek açıklamasını alır ve ardından ek açıklamanın görünümünden metni çıkarmak için bir metin emici kullanır. Ayıklanan metin daha sonra çıktıda görüntülenir.

### Aspose.PDF for .NET kullanarak Stamp Annotation'dan Metin Çıkarma için örnek kaynak kodu 
```csharp

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "test.pdf");
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;
TextAbsorber ta = new TextAbsorber();
XForm ap = annot.Appearance["N"];
ta.Visit(ap);
Console.WriteLine(ta.Text);

```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesindeki damga notundan nasıl metin çıkaracağınızı öğrendiniz. Artık bu yöntemi, PDF belgelerinizdeki diğer açıklamalardan metin çıkarmak için kullanabilirsiniz.
