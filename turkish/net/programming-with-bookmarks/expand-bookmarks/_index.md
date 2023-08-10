---
title: PDF Dosyasındaki Yer İmlerini Genişletin
linktitle: PDF Dosyasındaki Yer İmlerini Genişletin
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile gelişmiş gezinme için PDF dosyasındaki yer imlerini kolayca genişletin.
type: docs
weight: 50
url: /tr/net/programming-with-bookmarks/expand-bookmarks/
---
PDF dosyasındaki yer imlerini genişletmek, tüm açık yer imlerini varsayılan olarak görüntüler. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu izleyerek yer imlerini kolayca genişletebilirsiniz:

## 1. Adım: Gerekli kitaplıkları içe aktarın

Başlamadan önce, C# projeniz için gerekli kitaplıkları içe aktarmanız gerekir. İşte gerekli ithalat yönergesi:

```csharp
using Aspose.Pdf;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda, yer imlerini genişletmek istediğiniz PDF dosyasını içeren klasörün yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"`belgeler klasörünüzün gerçek yolu ile aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3. Adım: PDF belgesini açın

Şimdi yer imlerini genişletmek istediğimiz PDF belgesini aşağıdaki kodu kullanarak açacağız:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 4. Adım: Sayfa Görüntüleme Modunu Ayarlayın

Bu adımda, sayfa görüntüleme modunu varsayılan olarak yer imlerini gösterecek şekilde ayarlayacağız. biz kullanıyoruz`PageMode` mülkiyeti`doc` İstenen sayfa modunu ayarlamak için nesne. İşte ilgili kod:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

## 5. Adım: Yer imlerine göz atın ve genişletin

 Şimdi, belgenin yer işaretleri koleksiyonundaki her bir yer işareti öğesi arasında dolaşacağız ve her öğenin açık durumunu şu şekilde ayarlayacağız:`true` varsayılan olarak genişletmek için. İşte ilgili kod:

```csharp
foreach(OutlineItemCollection item in doc.Outlines)
{
     item. Open = true;
}
```

## 6. Adım: Güncellenen dosyayı kaydedin

 Son olarak, güncellenmiş PDF dosyasını kullanarak kaydediyoruz.`Save` yöntemi`doc` nesne. İşte ilgili kod:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

### Aspose.PDF for .NET kullanan Expand Bookmarks için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document doc = new Document(dataDir + "input.pdf");
// Sayfa görüntüleme modunu ayarlayın, yani küçük resimleri göster, tam ekran, ek panelini göster
doc.PageMode = PageMode.UseOutlines;
// PDF dosyasının ana hatlar koleksiyonundaki her bir Ouline öğesinde gezinin
foreach (OutlineItemCollection item in doc.Outlines)
{
	// Anahat öğesi için açık durumu ayarla
	item.Open = true;
}
dataDir = dataDir + "ExpandBookmarks_out.pdf";
// Çıktıyı kaydet
doc.Save(dataDir);
Console.WriteLine("\nBookmarks expanded successfully.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET ile yer imleri geliştirmek için adım adım bir kılavuza sahipsiniz. PDF belgelerinizdeki tüm varsayılan yer imlerini göstermek için bu kodu kullanabilirsiniz.

Gelişmiş yer imi düzenleme özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine baktığınızdan emin olun.

### PDF dosyasındaki yer imlerini genişletmeyle ilgili SSS

#### S: Bir PDF dosyasındaki yer imleri nedir?

Y: Bir PDF dosyasındaki yer imleri, kullanıcıların belge içindeki belirli bölümlere veya sayfalara hızlı bir şekilde atlamalarına olanak tanıyan gezinme yardımcılarıdır. Bir belgenin farklı bölümlerine erişmek için uygun bir yol sağlarlar.

#### S: Neden bir PDF dosyasındaki yer imlerini genişletmek isteyeyim?

Y: Genişleyen yer imleri, tüm yer imlerini varsayılan olarak genişletilmiş bir durumda görüntüleyerek kullanıcı deneyimini iyileştirebilir. Bu, kullanıcılara belgenin yapısı hakkında net bir genel bakış sağlar ve farklı bölümlere kolayca gitmelerini sağlar.

#### S: C# projem için gerekli kitaplıkları nasıl içeri aktarırım?

A: C# projeniz için gerekli kitaplığı içe aktarmak için aşağıdaki içe aktarma yönergesini kullanın:

```csharp
using Aspose.Pdf;
```

Bu yönerge, Aspose.PDF for .NET tarafından sağlanan sınıfları ve yöntemleri kullanmanızı sağlar.

#### S: Belgeler klasörünün yolunu nasıl belirtebilirim?

 A: Sağlanan kaynak kodunda değiştirin`"YOUR DOCUMENT DIRECTORY"` çalışmak istediğiniz PDF dosyasını içeren klasörün gerçek yolu ile birlikte. Bu, kodun hedef PDF dosyasını bulabilmesini sağlar.

#### S: Yer imlerini genişletmek için bir PDF belgesini nasıl açarım?

C: Genişleyen yer imleri için bir PDF belgesi açmak üzere aşağıdaki kodu kullanın:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Yer değiştirmek`"input.pdf"` gerçek dosya adı ile.

#### S: Sayfa görüntüleme modunu yer imlerini varsayılan olarak gösterecek şekilde nasıl ayarlarım?

A: Sayfa görüntüleme modunu yer imlerini varsayılan olarak gösterecek şekilde ayarlamak için`PageMode` mülkiyeti`doc` nesne:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

#### S: PDF belgesindeki tüm yer imlerini nasıl genişletirim?

 Y: Tüm yer imlerini genişletmek için, belgenin ana hatlar koleksiyonundaki her bir yer imi öğesini dolaşın ve`Open` mülkiyet`true`:

```csharp
foreach (OutlineItemCollection item in doc.Outlines)
{
    item.Open = true;
}
```

#### S: Bir yer iminde iç içe alt yer imleri varsa ne olur?

C: Bir yer iminin iç içe alt yer imleri varsa, üst yer iminin genişletilmesi, alt yer imlerini de genişleterek belge yapısının kapsamlı bir görünümünü sağlar.

#### S: Yer imlerini genişlettikten sonra güncellenmiş PDF dosyasını nasıl kaydedebilirim?

C: Yer imlerini genişlettikten sonra güncellenmiş PDF dosyasını kaydetmek için aşağıdaki kodu kullanın:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

#### S: Genişletilmiş yer imlerinin görünümünü özelleştirebilir miyim?

Y: Bu eğitim, varsayılan olarak yer imlerini genişletmeye odaklanırken, Aspose.PDF'nin diğer özelliklerini ve özelliklerini kullanarak yer imlerinin görünümünü özelleştirebilirsiniz.