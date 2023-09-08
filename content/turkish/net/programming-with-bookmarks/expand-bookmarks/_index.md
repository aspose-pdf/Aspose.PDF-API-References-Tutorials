---
title: PDF Dosyasındaki Yer İmlerini Genişlet
linktitle: PDF Dosyasındaki Yer İmlerini Genişlet
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile gelişmiş gezinme için PDF dosyasındaki yer işaretlerini kolayca genişletin.
type: docs
weight: 50
url: /tr/net/programming-with-bookmarks/expand-bookmarks/
---
PDF dosyasındaki yer işaretlerini genişletmek, varsayılan olarak tüm açık yer işaretlerini görüntüler. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu izleyerek yer işaretlerini kolayca genişletebilirsiniz:

## 1. Adım: Gerekli kitaplıkları içe aktarın

Başlamadan önce C# projeniz için gerekli kütüphaneleri içe aktarmanız gerekir. Gerekli ithalat direktifi aşağıdadır:

```csharp
using Aspose.Pdf;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda, yer işaretlerini genişletmek istediğiniz PDF dosyasının bulunduğu klasörün yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"`belgeler klasörünüzün gerçek yolunu içeren aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3. Adım: PDF belgesini açın

Şimdi yer işaretlerini genişletmek istediğimiz PDF belgesini aşağıdaki kodu kullanarak açacağız:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Adım 4: Sayfa Görüntüleme Modunu Ayarlayın

Bu adımda, sayfa görüntüleme modunu varsayılan olarak yer imlerini gösterecek şekilde ayarlayacağız. biz kullanıyoruz`PageMode` mülkiyeti`doc` İstenilen sayfa modunu ayarlamak için nesne. İşte ilgili kod:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

## 5. Adım: Yer imlerine göz atın ve onları genişletin

 Şimdi belgenin yer imleri koleksiyonundaki her bir yer imi öğesi arasında geçiş yapacağız ve her öğenin açık durumunu şu şekilde ayarlayacağız:`true` bunları varsayılan olarak genişletmek için. İşte ilgili kod:

```csharp
foreach(OutlineItemCollection item in doc.Outlines)
{
     item. Open = true;
}
```

## 6. Adım: Güncellenen dosyayı kaydedin

 Son olarak, güncellenen PDF dosyasını kullanarak kaydediyoruz.`Save` yöntemi`doc` nesne. İşte ilgili kod:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

### Aspose.PDF for .NET kullanarak Yer İmlerini Genişletme için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document doc = new Document(dataDir + "input.pdf");
// Sayfa görüntüleme modunu ayarlayın; örneğin küçük resimleri göster, tam ekran göster, ek panelini göster
doc.PageMode = PageMode.UseOutlines;
// PDF dosyasının ana hatlar koleksiyonundaki her bir Ouline öğesi arasında geçiş yapın
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

Tebrikler! Artık Aspose.PDF for .NET ile yer imleri geliştirmeye yönelik adım adım bir kılavuza sahipsiniz. PDF belgelerinizdeki tüm varsayılan yer işaretlerini göstermek için bu kodu kullanabilirsiniz.

Gelişmiş yer imi düzenleme özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine göz atmayı unutmayın.

### PDF dosyasındaki yer işaretlerini genişletmeye ilişkin SSS

#### S: PDF dosyasındaki yer işaretleri nedir?

C: Bir PDF dosyasındaki yer imleri, kullanıcıların belge içindeki belirli bölümlere veya sayfalara hızlı bir şekilde atlamasına olanak tanıyan gezinme yardımcılarıdır. Bir belgenin farklı bölümlerine erişmenin kolay bir yolunu sağlarlar.

#### S: Bir PDF dosyasındaki yer işaretlerini neden genişletmek isteyeyim?

C: Yer işaretlerini genişletmek, tüm yer işaretlerini varsayılan olarak genişletilmiş durumda görüntüleyerek kullanıcı deneyimini iyileştirebilir. Bu, kullanıcılara belgenin yapısına ilişkin net bir genel bakış sunar ve farklı bölümlere kolayca gitmelerine olanak tanır.

#### S: C# projem için gerekli kitaplıkları nasıl içeri aktarabilirim?

C: C# projeniz için gerekli kitaplığı içe aktarmak için aşağıdaki içe aktarma yönergesini kullanın:

```csharp
using Aspose.Pdf;
```

Bu yönerge Aspose.PDF for .NET tarafından sağlanan sınıfları ve yöntemleri kullanmanızı sağlar.

#### S: Belgeler klasörünün yolunu nasıl belirlerim?

 C: Sağlanan kaynak kodunda değiştirin`"YOUR DOCUMENT DIRECTORY"` çalışmak istediğiniz PDF dosyasını içeren klasörün gerçek yolunu belirtin. Bu, kodun hedef PDF dosyasını bulabilmesini sağlar.

#### S: Yer işaretlerini genişletmek için bir PDF belgesini nasıl açarım?

C: Yer imlerini genişletmek amacıyla bir PDF belgesi açmak için aşağıdaki kodu kullanın:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Yer değiştirmek`"input.pdf"` gerçek dosya adı ile.

#### S: Sayfa görüntüleme modunu varsayılan olarak yer imlerini gösterecek şekilde nasıl ayarlarım?

C: Sayfa görüntüleme modunu varsayılan olarak yer imlerini gösterecek şekilde ayarlamak için`PageMode` mülkiyeti`doc` nesne:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

#### S: PDF belgesindeki tüm yer işaretlerini nasıl genişletirim?

 C: Tüm yer imlerini genişletmek için, belgenin ana hatlar koleksiyonundaki her bir yer imi öğesi arasında dolaşın ve`Open` mülkiyet`true`:

```csharp
foreach (OutlineItemCollection item in doc.Outlines)
{
    item.Open = true;
}
```

#### S: Bir yer iminde iç içe geçmiş alt yer imleri varsa ne olur?

C: Bir yer iminde yuvalanmış alt yer imleri varsa, ana yer imini genişletmek aynı zamanda alt yer imlerini de genişleterek belgenin yapısına ilişkin kapsamlı bir görünüm sağlar.

#### S: Yer imlerini genişlettikten sonra güncellenen PDF dosyasını nasıl kaydedebilirim?

C: Yer imlerini genişlettikten sonra güncellenen PDF dosyasını kaydetmek için aşağıdaki kodu kullanın:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

#### S: Genişletilmiş yer imlerinin görünümünü özelleştirebilir miyim?

C: Bu eğitim varsayılan olarak yer imlerini genişletmeye odaklansa da, Aspose.PDF'in diğer özelliklerini ve özelliklerini kullanarak yer imlerinin görünümünü özelleştirebilirsiniz.