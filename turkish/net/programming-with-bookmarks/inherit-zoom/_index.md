---
title: PDF Dosyasında Yakınlaştırmayı Devral
linktitle: PDF Dosyasında Yakınlaştırmayı Devral
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile PDF dosyasındaki yer imi yakınlaştırmasını kolayca devralın.
type: docs
weight: 90
url: /tr/net/programming-with-bookmarks/inherit-zoom/
---
PDF dosyasındaki yakınlaştırma devralma, yer imleri için varsayılan bir yakınlaştırma düzeyi belirtmenize olanak tanır. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu takip ederek zoom'u kolayca devralabilirsiniz:

## 1. Adım: Gerekli kitaplıkları içe aktarın

Başlamadan önce, C# projeniz için gerekli kitaplıkları içe aktarmanız gerekir. İşte gerekli ithalat yönergesi:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda, yakınlaştırmayı devralmak istediğiniz PDF dosyasını içeren klasörün yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"`belgeler klasörünüzün gerçek yolu ile aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3. Adım: PDF belgesini açın

Şimdi, aşağıdaki kodu kullanarak yakınlaştırmayı devralmak istediğimiz PDF belgesini açacağız:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 4. Adım: Yer İmleri Koleksiyonunu Alın

 Bu adımda, kullanarak belgenin yer imlerinin veya yer işaretlerinin koleksiyonunu alacağız.`Outlines` mülkiyeti`doc` nesne. İşte ilgili kod:

```csharp
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
```

## 5. Adım: Yakınlaştırma Düzeyini Ayarlayın

 Şimdi bir tane oluşturarak yakınlaştırma seviyesini ayarlayacağız.`XYZExplicitDestination` belirtilen x, y ve z koordinatlarına sahip nesne. Burada koordinatları (100, 100, 0) 2 yakınlaştırma ile kullanıyoruz. İşte ilgili kod:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

## 6. Adım: Yer İşaretlerine Yakınlaştırma Düzeyi Ekleyin

 Bu adımda, ekliyoruz`XYZExplicitDestination` yer imlerine bir eylem olarak nesne`item` Toplamak. İşte ilgili kod:

```csharp
item. Action = new GoToAction(dest);
```

## 7. Adım: Güncellenen yer imlerini belgeye ekleyin

 Son olarak, güncellenmiş yer imlerini kullanarak belgenin yer imleri koleksiyonuna ekliyoruz.`Add` yöntemi`doc.Outlines` nesne. İşte ilgili kod:

```csharp
doc. Outlines. Add(item);
```

## 8. Adım: Güncellenen dosyayı kaydedin

 Şimdi güncellenmiş PDF dosyasını kullanarak kaydedelim.`Save` yöntemi`doc` nesne. İşte ilgili kod:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Inherit Zoom için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document doc = new Document(dataDir + "input.pdf");
// PDF dosyasının ana hatlarını/yer imlerini alın
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
// Yakınlaştırma seviyesini 0 olarak ayarla
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
// PDF koleksiyonunun ana hatlarını çizmek için XYZExplicitDestination'ı eylem olarak ekleyin
item.Action = new GoToAction(dest);
// PDF dosyasının ana hatları koleksiyonuna öğe ekleyin
doc.Outlines.Add(item);
dataDir = dataDir + "InheritZoom_out.pdf";
// Çıktıyı kaydet
doc.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET ile Zoom'u Devralmak için adım adım bir kılavuzunuz var. PDF belgelerinizdeki yer imleri için varsayılan bir yakınlaştırma düzeyi belirtmek üzere bu kodu kullanabilirsiniz.

Gelişmiş yer imi düzenleme özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine baktığınızdan emin olun.

### PDF dosyasında yakınlaştırmayı devralmayla ilgili SSS

#### S: Bir PDF dosyasındaki yakınlaştırma mirası nedir?

Y: Yakınlaştırma devralma, bir PDF belgesindeki yer imleri için varsayılan bir yakınlaştırma düzeyi belirleme becerisini ifade eder. Bu, kullanıcılar yer imleriyle etkileşim kurduğunda tutarlı ve kullanıcı dostu gezinme sağlar.

#### S: Neden yer işaretleri için yakınlaştırma düzeylerini devralmak isteyeyim?

Y: Yakınlaştırma düzeylerinin devralınması, kullanıcıların bir PDF belgesindeki yer imleri arasında gezinirken tutarlı bir görüntüleme deneyimi yaşamasını sağlar. Bir belgenin farklı bölümleri için belirli bir görünüm sağlamak istediğinizde özellikle yararlı olabilir.

#### S: C# projem için gerekli kitaplıkları nasıl içeri aktarırım?

A: C# projeniz için gerekli kitaplıkları içe aktarmak için aşağıdaki içe aktarma yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Bu yönergeler, PDF belgeleri ve yer imleriyle çalışmak için gereken sınıflara ve yöntemlere erişmenizi sağlar.

#### S: Belgeler klasörünün yolunu nasıl belirtebilirim?

 A: Sağlanan kaynak kodunda değiştirin`"YOUR DOCUMENT DIRECTORY"` Yakınlaştırma düzeylerini devralmak istediğiniz PDF dosyasını içeren klasörün gerçek yolu ile.

#### S: Yakınlaştırma düzeylerini devralmak için bir PDF belgesini nasıl açarım?

C: Yakınlaştırma düzeylerini devralmak üzere bir PDF belgesi açmak için aşağıdaki kodu kullanın:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Yer değiştirmek`"input.pdf"` gerçek dosya adı ile.

#### S: Yer imleri için yakınlaştırma seviyesini nasıl ayarlarım?

 A: Yakınlaştırma seviyesini ayarlamak için bir`XYZExplicitDestination` istenen koordinatlara ve yakınlaştırma faktörüne sahip nesne. İşte bir örnek:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

Bu, yakınlaştırma seviyesini koordinatlarda (100, 100) 2'ye ayarlar.

#### S: Yakınlaştırma düzeyini yer imlerine nasıl eklerim?

 C: Ekle`XYZExplicitDestination` yer imleri koleksiyonuna bir eylem olarak nesne:

```csharp
item.Action = new GoToAction(dest);
```

 Nerede`item` bir`OutlineItemCollection` bir yer imini temsil ediyor.

#### S: Güncellenmiş PDF dosyasını nasıl kaydedebilirim?

 A: Güncellenmiş PDF dosyasını kullanarak kaydedin.`Save` yöntemi`doc` nesne:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

#### S: Farklı yer işaretleri için yakınlaştırma düzeylerini özelleştirebilir miyim?

 C: Evet, birden çok yer işareti oluşturarak farklı yer işaretleri için yakınlaştırma düzeylerini özelleştirebilirsiniz.`XYZExplicitDestination` farklı koordinatlara ve yakınlaştırma faktörlerine sahip nesneler.

#### S: Zoom mirasını uygulayabileceğim yer imlerinin sayısında bir sınır var mı?

Y: Yakınlaştırma devralmayı uygulayabileceğiniz yer imlerinin sayısında genellikle katı bir sınır yoktur. Ancak, aşırı sayıda yer imine sahip çok büyük belgeler, etkin bellek yönetimi gerektirebilir.

#### S: Yakınlaştırma devralmasının uygulandığını nasıl doğrulayabilirim?

C: Belirtilen yakınlaştırma düzeylerinin yer imleri tarafından devralındığını doğrulamak için oluşturulan PDF dosyasını açın.