---
title: Damga Açıklamasından Metin Çıkarma
linktitle: Damga Açıklamasından Metin Çıkarma
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile PDF belgelerinizdeki damga açıklamasından kolayca metin çıkarmayı öğrenin.
type: docs
weight: 80
url: /tr/net/programming-with-stamps-and-watermarks/extract-text-from-stamp-annotation/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesindeki damga açıklamasından nasıl metin çıkarılacağı konusunda size adım adım yol göstereceğiz. PDF belgesinin belirli bir sayfasındaki belirli bir damga açıklamasından metni çıkarmak için sağlanan C# kaynak kodunu nasıl kullanacağınızı size göstereceğiz.

## 1. Adım: Ortamı ayarlama

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Kurulu bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kütüphanesini indirip projenizde referans olarak kullanabilirsiniz.

## Adım 2: PDF belgesini yükleme

İlk adım mevcut PDF belgesini projenize yüklemektir. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi yükleyin
Document doc = new Document(dataDir + "test.pdf");
```

"BELGELERİNİZ DİZİNİ"ni, PDF belgenizin bulunduğu dizine giden gerçek yolla değiştirdiğinizden emin olun.

## 3. Adım: Damga açıklamasından metni çıkarın

Artık PDF belgesini yüklediğinize göre, metni belirli damga açıklamasından çıkarabilirsiniz. İşte nasıl:

```csharp
// Tampon açıklamasını al
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;

// Metin emici oluşturma
TextAbsorber ta = new TextAbsorber();

// Ek açıklamanın görünümünü ziyaret edin
XForm ap = annot. Appearance["N"];
ta.Visit(ap);

// Çıkarılan metni görüntüle
Console.WriteLine(ta.Text);
```

Yukarıdaki kod, damga ek açıklamasını PDF belgesinin belirtilen sayfasından alır ve ardından metni ek açıklamanın görünümünden çıkarmak için bir metin emici kullanır. Çıkarılan metin daha sonra çıktıda görüntülenir.

### Aspose.PDF for .NET kullanarak Damga Açıklamasından Metin Çıkarma için örnek kaynak kodu 
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

Tebrikler! Aspose.PDF for .NET'i kullanarak bir PDF belgesindeki damga açıklamasından metni nasıl çıkaracağınızı öğrendiniz. Artık bu yöntemi PDF belgelerinizdeki diğer açıklamalardan metin çıkarmak için kullanabilirsiniz.

### Damga açıklamasından metin çıkarmak için SSS'ler

#### S: PDF belgesindeki damga açıklaması nedir ve neden bu belgeden metin çıkarmam gerekiyor?

C: PDF belgesindeki damga açıklaması, filigran veya lastik damga gibi ek bilgiler sağlamak için kullanılabilen grafiksel bir öğedir. Damga ek açıklamasından metin çıkarmak, bu ek açıklamalardan notlar, etiketler veya diğer metin bilgileri içerebilen metin tabanlı içerik almak istediğinizde kullanışlıdır.

#### S: Sağlanan C# kaynak kodu, damga ek açıklamasından metni nasıl çıkarır?

 C: Sağlanan kaynak kodu, bir PDF belgesinin belirli bir sayfasındaki belirli bir damga açıklamasından metnin nasıl çıkarılacağını gösterir. Damga açıklamasını almak, görünümünü ziyaret etmek için Aspose.PDF kütüphanesini kullanır.`TextAbsorber`ve ardından çıkarılan metni çıktıda görüntüler.

#### S: Benzer bir yaklaşım kullanarak farklı türdeki ek açıklamalardan metin çıkarabilir miyim?

C: Evet, metin ek açıklamaları veya açılır pencere ek açıklamaları gibi diğer ek açıklama türlerinden metin çıkarmak için benzer bir yaklaşım kullanabilirsiniz. Metni çıkarmak istediğiniz belirli ek açıklama türünü hedeflemek için kodu değiştirmeniz gerekir.

####  Soru: Programın amacı nedir?`TextAbsorber` class in the code?

 C:`TextAbsorber` sınıfı, damga açıklamaları da dahil olmak üzere bir PDF belgesinin farklı bölümlerinden metin çıkarmak için kullanılır. PDF'nin belirtilen alanında veya öğesinde bulunan metin içeriğini "emer" veya yakalar.

#### S: Metni çıkarmak istediğim belirli damga açıklamasını nasıl tanımlarım?

 C: Sağlanan kodda damga açıklaması,`Annotations` Belirli bir sayfanın toplanması ve istenen ek açıklamayı almak için dizini kullanma. Hedef açıklamayı tanımlamak için dizini ayarlayabilir veya diğer kriterleri kullanabilirsiniz.

#### S: Aynı sayfadaki birden fazla damga açıklamasından metin çıkarabilir miyim?

 C: Evet, kodda döngü oluşturacak şekilde değişiklik yapabilirsiniz.`Annotations`bir sayfanın koleksiyonunu oluşturun, damga açıklamalarını filtreleyin ve her birinden metin çıkarın.

#### S: Damga açıklamasının metin içeriği yoksa ne olur? Kod hala çalışacak mı?

C: Kod çalışmaya devam edecek ancak damga ek açıklamasının görünümü herhangi bir metin içeriği içermiyorsa boş bir dize çıkaracak ve görüntüleyecektir.

#### S: Çıkarılan metni çıktıda görüntülemek yerine bir dosyaya nasıl kaydedebilirim?

 C: Çıkarılan metni konsolda görüntülemek yerine bir dosyaya kaydetmek için kodu değiştirebilirsiniz. Basitçe değiştirin`Console.WriteLine` Metni bir dosyaya yazmak için kod içeren ifade.

#### S: Çıkarılan metni daha sonraki işlemlerde veya analizlerde nasıl kullanabilirim?

C: Sağlanan yöntemi kullanarak metni çıkardıktan sonra, onu bir değişkende saklayabilir, değiştirebilir, analiz edebilir veya gerektiği şekilde uygulamanızın diğer bölümlerine entegre edebilirsiniz.