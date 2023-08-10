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

### Damga notundan metin ayıklamak için SSS

#### S: Bir PDF belgesindeki damga ek açıklaması nedir ve neden ondan metin çıkarmam gerekiyor?

Y: Bir PDF belgesindeki damga ek açıklaması, filigran veya lastik damga gibi ek bilgiler sağlamak için kullanılabilen bir grafik öğedir. Bir damga notundan metin çıkarmak, bu notlardan notları, etiketleri veya diğer metin bilgilerini içerebilen metin tabanlı içeriği almak istediğinizde kullanışlıdır.

#### S: Sağlanan C# kaynak kodu, bir damga ek açıklamasından nasıl metin çıkarır?

 A: Sağlanan kaynak kodu, bir PDF belgesinin belirli bir sayfasındaki belirli bir damga notundan nasıl metin çıkarılacağını gösterir. Damga bilgi notunu almak için Aspose.PDF kütüphanesini kullanır, görünümünü ziyaret etmek için`TextAbsorber`ve ardından ayıklanan metni çıktıda görüntüler.

#### S: Benzer bir yaklaşım kullanarak farklı açıklama türlerinden metin çıkarabilir miyim?

C: Evet, metin ek açıklamaları veya açılır ek açıklamalar gibi diğer açıklama türlerinden metin çıkarmak için benzer bir yaklaşım kullanabilirsiniz. Metni çıkarmak istediğiniz belirli ek açıklama türünü hedeflemek için kodu değiştirmeniz gerekir.

####  S: Amacı nedir?`TextAbsorber` class in the code?

 C:`TextAbsorber` class, damga ek açıklamaları da dahil olmak üzere bir PDF belgesinin farklı bölümlerinden metin çıkarmak için kullanılır. PDF'nin belirtilen alanında veya öğesinde bulunan metin içeriğini "emer" veya yakalar.

#### S: İçinden metin çıkarmak istediğim belirli damga ek açıklamasını nasıl belirleyebilirim?

 A: Sağlanan kodda, damga notu şu adrese erişilerek tanımlanır:`Annotations` belirli bir sayfanın toplanması ve istenen açıklamayı almak için dizini kullanma. Hedef açıklamayı belirlemek için dizini ayarlayabilir veya başka ölçütler kullanabilirsiniz.

#### S: Aynı sayfadaki birden fazla damga notundan metin çıkarabilir miyim?

 C: Evet, kodda döngü oluşturmak için değiştirebilirsiniz.`Annotations`bir sayfanın toplanması, damga ek açıklamalarını filtreleyin ve her birinden metin çıkarın.

#### S: Damga şerhinin metin içeriği yoksa ne olur? Kod çalışmaya devam edecek mi?

A: Kod çalışmaya devam edecek, ancak damga notunun görünümü herhangi bir metin içeriği içermiyorsa, ayıklayacak ve boş bir dize gösterecektir.

#### S: Ayıklanan metni çıktıda görüntülemek yerine bir dosyaya nasıl kaydedebilirim?

 Y: Ayıklanan metni konsolda görüntülemek yerine bir dosyaya kaydetmek için kodu değiştirebilirsiniz. Basitçe değiştirin`Console.WriteLine` metni bir dosyaya yazmak için kod içeren ifade.

#### S: Ayıklanan metni daha sonraki işlemlerde veya analizlerde nasıl kullanabilirim?

A: Sağlanan yöntemi kullanarak metni çıkardıktan sonra, onu bir değişkende saklayabilir, değiştirebilir, analiz edebilir veya gerektiğinde uygulamanızın diğer bölümlerine entegre edebilirsiniz.