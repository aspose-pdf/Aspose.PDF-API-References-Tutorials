---
title: PDF Dosyasını Yakınlaştır'ı Devral
linktitle: PDF Dosyasını Yakınlaştır'ı Devral
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile PDF dosyasındaki yer imi yakınlaştırmasını kolayca devralın.
type: docs
weight: 90
url: /tr/net/programming-with-bookmarks/inherit-zoom/
---
PDF dosyasındaki yakınlaştırmayı devralma, yer imleri için varsayılan bir yakınlaştırma düzeyi belirtmenize olanak tanır. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu izleyerek yakınlaştırmayı kolayca devralabilirsiniz:

## 1. Adım: Gerekli kitaplıkları içe aktarın

Başlamadan önce C# projeniz için gerekli kütüphaneleri içe aktarmanız gerekir. Gerekli ithalat direktifi aşağıdadır:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda yakınlaştırmayı devralmak istediğiniz PDF dosyasını içeren klasörün yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"`belgeler klasörünüzün gerçek yolunu içeren aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3. Adım: PDF belgesini açın

Şimdi yakınlaştırmayı devralmak istediğimiz PDF belgesini aşağıdaki kodu kullanarak açacağız:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 4. Adım: Yer İmleri Koleksiyonunu Alın

 Bu adımda, belgenin yer imlerinin veya yer işaretlerinin koleksiyonunu kullanarak alacağız.`Outlines` mülkiyeti`doc` nesne. İşte ilgili kod:

```csharp
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
```

## Adım 5: Yakınlaştırma Düzeyini Ayarlayın

 Şimdi bir yakınlaştırma düzeyi oluşturarak ayarlayacağız.`XYZExplicitDestination` belirtilen x, y ve z koordinatlarına sahip nesne. Burada koordinatları (100, 100, 0) 2 yakınlaştırmayla kullanıyoruz. İlgili kod:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

## Adım 6: Yer İmlerine Yakınlaştırma Düzeyi Ekleme

 Bu adımda şunu ekliyoruz`XYZExplicitDestination` yer imlerine bir eylem olarak nesne`item` Toplamak. İşte ilgili kod:

```csharp
item. Action = new GoToAction(dest);
```

## 7. Adım: Güncellenen yer işaretlerini belgeye ekleyin

 Son olarak, güncellenen yer imlerini belgenin yer imleri koleksiyonuna şunu kullanarak ekliyoruz:`Add` yöntemi`doc.Outlines` nesne. İşte ilgili kod:

```csharp
doc. Outlines. Add(item);
```

## 8. Adım: Güncellenen dosyayı kaydedin

 Şimdi güncellenen PDF dosyasını kullanarak kaydedelim.`Save` yöntemi`doc` nesne. İşte ilgili kod:

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
// PDF dosyasının ana hatlarını/yer imleri koleksiyonunu alın
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
// Yakınlaştırma düzeyini 0 olarak ayarla
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
// PDF koleksiyonunun ana hatlarını oluşturmak için XYZExplicitDestination'ı eylem olarak ekleyin
item.Action = new GoToAction(dest);
// PDF dosyasının ana hatlar koleksiyonuna öğe ekle
doc.Outlines.Add(item);
dataDir = dataDir + "InheritZoom_out.pdf";
// Çıktıyı kaydet
doc.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET ile Zoom'u Devralmak için adım adım bir kılavuza sahipsiniz. PDF belgelerinizdeki yer imleri için varsayılan yakınlaştırma düzeyini belirlemek amacıyla bu kodu kullanabilirsiniz.

Gelişmiş yer imi düzenleme özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine göz atmayı unutmayın.

### PDF dosyasındaki yakınlaştırmanın devralınması ile ilgili SSS

#### S: PDF dosyasında yakınlaştırmayı devralma nedir?

C: Yakınlaştırmayı devralma, bir PDF belgesindeki yer imleri için varsayılan yakınlaştırma düzeyini belirtme yeteneğini ifade eder. Bu, kullanıcılar yer imleriyle etkileşime girdiğinde tutarlı ve kullanıcı dostu gezinmeye olanak tanır.

#### S: Yer imlerinin yakınlaştırma düzeylerini neden devralmak isteyeyim?

C: Yakınlaştırma düzeylerini devralmak, kullanıcıların bir PDF belgesindeki yer imleri arasında gezinirken tutarlı bir görüntüleme deneyimi yaşamasını sağlar. Bir belgenin farklı bölümleri için belirli bir görünüm sağlamak istediğinizde özellikle yararlı olabilir.

#### S: C# projem için gerekli kitaplıkları nasıl içeri aktarabilirim?

C: C# projeniz için gerekli kitaplıkları içe aktarmak için aşağıdaki içe aktarma yönergelerini ekleyin:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Bu yönergeler, PDF belgeleri ve yer imleriyle çalışmak için gereken sınıflara ve yöntemlere erişmenizi sağlar.

#### S: Belgeler klasörünün yolunu nasıl belirlerim?

 C: Sağlanan kaynak kodunda değiştirin`"YOUR DOCUMENT DIRECTORY"` yakınlaştırma düzeylerini devralmak istediğiniz PDF dosyasını içeren klasörün gerçek yolunu belirtin.

#### S: Yakınlaştırma düzeylerini devralmak için bir PDF belgesini nasıl açarım?

C: Yakınlaştırma düzeylerini devralmak üzere bir PDF belgesi açmak için aşağıdaki kodu kullanın:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Yer değiştirmek`"input.pdf"` gerçek dosya adı ile.

#### S: Yer imlerinin yakınlaştırma düzeyini nasıl ayarlarım?

 C: Yakınlaştırma düzeyini ayarlamak için bir`XYZExplicitDestination` İstenilen koordinatlara ve yakınlaştırma faktörüne sahip nesne. İşte bir örnek:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

Bu, yakınlaştırma düzeyini koordinatlarda (100, 100) 2'ye ayarlar.

#### S: Yakınlaştırma düzeyini yer imlerine nasıl eklerim?

 C: Ekle`XYZExplicitDestination` yer imleri koleksiyonuna bir eylem olarak nesne:

```csharp
item.Action = new GoToAction(dest);
```

 Nerede`item` bir`OutlineItemCollection` bir yer imini temsil ediyor.

#### S: Güncellenen PDF dosyasını nasıl kaydederim?

 C: Güncellenen PDF dosyasını kullanarak kaydedin.`Save` yöntemi`doc` nesne:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

#### S: Farklı yer imleri için yakınlaştırma düzeylerini özelleştirebilir miyim?

 C: Evet, birden fazla yer işareti oluşturarak farklı yer imleri için yakınlaştırma düzeylerini özelleştirebilirsiniz.`XYZExplicitDestination` farklı koordinatlara ve yakınlaştırma faktörlerine sahip nesneler.

#### S: Yakınlaştırma devralmasını uygulayabileceğim yer işareti sayısında bir sınır var mı?

C: Yakınlaştırma devralmasını uygulayabileceğiniz yer imlerinin sayısı konusunda genellikle kesin bir sınır yoktur. Ancak, aşırı sayıda yer imine sahip çok büyük belgeler, etkin bellek yönetimi gerektirebilir.

#### S: Yakınlaştırma devralmasının uygulandığını nasıl doğrulayabilirim?

C: Belirtilen yakınlaştırma düzeylerinin yer imleri tarafından devralındığını doğrulamak için oluşturulan PDF dosyasını açın.