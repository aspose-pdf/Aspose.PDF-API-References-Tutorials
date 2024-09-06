---
title: Damga Açıklamasından Metin Çıkar
linktitle: Damga Açıklamasından Metin Çıkar
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF belgelerinizdeki damga ek açıklamalarından metni kolayca nasıl çıkaracağınızı öğrenin.
type: docs
weight: 80
url: /tr/net/programming-with-stamps-and-watermarks/extract-text-from-stamp-annotation/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesindeki damga açıklamasından metni nasıl çıkaracağınızı adım adım göstereceğiz. Sağlanan C# kaynak kodunu kullanarak PDF belgesinin belirli bir sayfasındaki belirli bir damga açıklamasından metni nasıl çıkaracağınızı göstereceğiz.

## Adım 1: Ortamı kurma

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Kurulu bir .NET geliştirme ortamı.
- .NET için Aspose.PDF kütüphanesi indirildi ve projenizde referans olarak kullanıldı.

## Adım 2: PDF belgesini yükleme

İlk adım, mevcut PDF belgesini projenize yüklemektir. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi yükle
Document doc = new Document(dataDir + "test.pdf");
```

"BELGELERİNİZ DİZİNİ" ifadesini PDF belgenizin bulunduğu dizinin gerçek yoluyla değiştirdiğinizden emin olun.

## Adım 3: Damga açıklamasından metni çıkarın

Artık PDF belgesini yüklediğinize göre, metni belirli damga açıklamasından çıkarabilirsiniz. İşte nasıl:

```csharp
// Arabellek açıklamasını al
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;

// Bir metin emici oluşturun
TextAbsorber ta = new TextAbsorber();

// Açıklamanın görünümünü ziyaret edin
XForm ap = annot. Appearance["N"];
ta.Visit(ap);

// Çıkarılan metni görüntüle
Console.WriteLine(ta.Text);
```

Yukarıdaki kod, damga açıklamasını PDF belgesinin belirtilen sayfasından alır ve ardından metni açıklamanın görünümünden çıkarmak için bir metin emici kullanır. Çıkarılan metin daha sonra çıktıda görüntülenir.

### .NET için Aspose.PDF kullanarak Damga Açıklamasından Metin Çıkarma için örnek kaynak kodu 
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

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesindeki damga açıklamasından metin çıkarmayı öğrendiniz. Artık bu yöntemi kullanarak PDF belgelerinizdeki diğer açıklamalardan metin çıkarabilirsiniz.

### Damga açıklamasından metin çıkarma hakkında SSS

#### S: PDF belgesinde damga açıklaması nedir ve neden bundan metin çıkarmam gerekir?

A: PDF belgesindeki damga açıklaması, filigran veya lastik damga gibi ek bilgiler sağlamak için kullanılabilen grafiksel bir öğedir. Notlar, etiketler veya diğer metinsel bilgileri içerebilen bu açıklamalardan metin tabanlı içerik almak istediğinizde, damga açıklamasından metin çıkarmak yararlıdır.

#### S: Sağlanan C# kaynak kodu bir damga açıklamasından metni nasıl çıkarır?

 A: Sağlanan kaynak kodu, bir PDF belgesinin belirli bir sayfasındaki belirli bir damga açıklamasından metnin nasıl çıkarılacağını gösterir. Damga açıklamasını almak için Aspose.PDF kitaplığını kullanır, bir`TextAbsorber`ve ardından çıkarılan metni çıktıda görüntüler.

#### S: Benzer bir yaklaşım kullanarak farklı türdeki açıklamalardan metin çıkarabilir miyim?

C: Evet, metin açıklamaları veya açılır açıklamalar gibi diğer açıklama türlerinden metin çıkarmak için benzer bir yaklaşım kullanabilirsiniz. Metni çıkarmak istediğiniz belirli açıklama türünü hedeflemek için kodu değiştirmeniz gerekir.

####  S: Amacı nedir?`TextAbsorber` class in the code?

 A:`TextAbsorber` sınıf, damga açıklamaları da dahil olmak üzere bir PDF belgesinin farklı bölümlerinden metin çıkarmak için kullanılır. PDF'nin belirtilen alanında veya öğesinde bulunan metin içeriğini "emer" veya yakalar.

#### S: Metni çıkarmak istediğim belirli damga açıklamasını nasıl belirlerim?

 A: Sağlanan kodda, damga açıklaması, şuraya erişilerek tanımlanır:`Annotations` Belirli bir sayfanın toplanması ve istenen açıklamayı almak için dizini kullanma. Hedef açıklamayı tanımlamak için dizini ayarlayabilir veya başka ölçütler kullanabilirsiniz.

#### S: Aynı sayfadaki birden fazla damga ek açıklamasından metin çıkarabilir miyim?

 A: Evet, kodu döngüye alacak şekilde değiştirebilirsiniz`Annotations`Bir sayfanın koleksiyonunu oluşturun, damga açıklamalarını filtreleyin ve her birinden metin çıkarın.

#### S: Damga açıklamasının metinsel içeriği yoksa ne olur? Kod yine de çalışır mı?

A: Kod yine çalışacak, ancak damga açıklamasının görünümünde herhangi bir metinsel içerik bulunmuyorsa boş bir dize çıkarılacak ve görüntülenecektir.

#### S: Çıkarılan metni çıktıda görüntülemek yerine bir dosyaya nasıl kaydedebilirim?

 A: Çıkarılan metni konsolda görüntülemek yerine bir dosyaya kaydetmek için kodu değiştirebilirsiniz. Basitçe şunu değiştirin:`Console.WriteLine` Metni bir dosyaya yazmak için kod içeren ifade.

#### S: Çıkarılan metni daha ileri işleme veya analizde nasıl kullanabilirim?

A: Sağlanan yöntemi kullanarak metni çıkardıktan sonra, onu bir değişkende saklayabilir, işleyebilir, analiz edebilir veya ihtiyacınız olduğunda uygulamanızın diğer bölümlerine entegre edebilirsiniz.