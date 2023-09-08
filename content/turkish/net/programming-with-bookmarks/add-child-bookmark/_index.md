---
title: PDF Dosyasına Çocuk Yer İşareti Ekle
linktitle: PDF Dosyasına Çocuk Yer İşareti Ekle
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET ile daha düzenli gezinmek için PDF dosyasına kolayca alt yer imi ekleyin.
type: docs
weight: 20
url: /tr/net/programming-with-bookmarks/add-child-bookmark/
---
PDF dosyasına alt yer imleri eklemek, daha yapılandırılmış organizasyona ve gezinmeye olanak tanır. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu izleyerek kolayca alt yer imi ekleyebilirsiniz:

## 1. Adım: Gerekli kitaplıkları içe aktarın

Başlamadan önce C# projeniz için gerekli kütüphaneleri içe aktarmanız gerekir. Gerekli ithalat direktifi aşağıdadır:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda, alt yer imi eklemek istediğiniz PDF dosyasının bulunduğu klasörün yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"`belgeler klasörünüzün gerçek yolunu içeren aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3. Adım: PDF belgesini açın

Şimdi alt yer imi eklemek istediğimiz PDF belgesini aşağıdaki kodu kullanarak açacağız:

```csharp
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
```

## 4. Adım: Ana yer imi nesnesini oluşturun

 Bu adımda, ana yer imi nesnesini kullanarak bir ana yer imi nesnesi oluşturacağız.`OutlineItemCollection` sınıfını seçin ve başlık, italik nitelik ve kalın nitelik gibi özelliklerini ayarlayın. İşte ilgili kod:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent bookmark";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## Adım 5: Alt Yer İşareti Nesnesi Oluşturun

Bu adımda, yine kullanarak bir alt yer imi nesnesi oluşturacağız.`OutlineItemCollection` sınıfını seçin ve özelliklerini ayarlayın. İşte ilgili kod:

```csharp
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Sub Bookmark";
pdfChildOutline. Italic = true;
pdfChildOutline. Bold = true;
```

## 6. Adım: Alt yer imini ana yer imine ekleyin

 Son olarak, oluşturulan alt yer imini ana yer iminin alt yer imi koleksiyonuna şunu kullanarak ekliyoruz:`Add` ana nesnenin yöntemi. İşte ilgili kod:

```csharp
pdfOutline.Add(pdfChildOutline);
```

## 7. Adım: Ana yer işaretini belgenin yer işareti koleksiyonuna ekleyin

 Son olarak, ana yer imini belgenin yer imi koleksiyonuna şunu kullanarak ekliyoruz:`Add` yöntemi`Outlines` mülk. İşte ilgili kod:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Aspose.PDF for .NET kullanarak Çocuk Yer İmi Ekleme için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
// Ana yer imi nesnesi oluşturma
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;      
// Alt yer imi nesnesi oluşturma
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Child Outline";
pdfChildOutline.Italic = true;
pdfChildOutline.Bold = true;
// Ana yer iminin koleksiyonuna alt yer imini ekleyin
pdfOutline.Add(pdfChildOutline);
// Belgenin anahat koleksiyonuna ana yer işaretini ekleyin.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddChildBookmark_out.pdf";
// Çıktıyı kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmark added successfully.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET ile alt yer imi eklemek için adım adım bir kılavuza sahipsiniz. PDF belgelerinizdeki yer işaretlerinizi düzenlemek ve yapılandırmak için bu kodu kullanabilirsiniz.

Gelişmiş yer imi düzenleme özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine göz atmayı unutmayın.

### PDF dosyasına alt yer imi eklemeyle ilgili SSS

#### S: PDF dosyasındaki alt yer imleri nedir?

C: Alt yer imleri olarak da bilinen alt yer imleri, bir PDF belgesi içindeki ana yer iminin altında hiyerarşik olarak yapılandırılmış gezinme öğeleridir. Belge için daha düzenli ve ayrıntılı bir içindekiler tablosu oluşturmanın bir yolunu sağlarlar.

#### S: C# projem için gerekli kitaplıkları nasıl içeri aktarabilirim?

C: C# projeniz için gerekli kitaplıkları içe aktarmak için aşağıdaki içe aktarma yönergesini kullanabilirsiniz:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Bu kitaplıklar, PDF belgeleriyle ve etkileşimli özelliklerle çalışmak için gerekli sınıfları ve işlevleri sağlar.

#### S: Belgeler klasörünün yolunu nasıl belirlerim?

 C: Sağlanan kaynak kodunda değiştirmeniz gerekir`"YOUR DOCUMENT DIRECTORY"` çalışmak istediğiniz PDF dosyasını içeren klasörün gerçek yolunu belirtin. Bu, kodun hedef PDF dosyasını doğru şekilde bulmasını sağlar.

#### S: Birden fazla düzeyde alt yer işareti oluşturabilir miyim?

C: Evet, eğitimde özetlenen süreci genişleterek birden fazla düzeyde alt yer imi oluşturabilirsiniz. Alt yer imleriyle ana yer imleri oluşturup bunları daha fazla iç içe yerleştirerek, karmaşık PDF belgeleri için yer imlerinin hiyerarşik bir yapısını oluşturabilirsiniz.

####  Soru: Programın amacı nedir?`OutlineItemCollection` class?

 C:`OutlineItemCollection` Aspose.PDF for .NET'teki sınıf, aslında bir PDF belgesindeki yer imleri olan taslakları oluşturmak ve yönetmek için kullanılır. Bu sınıf, yer imleri için başlık, yazı tipi stili ve eylemler gibi özellikleri ayarlamanıza olanak tanır.

#### S: Ana yer imine nasıl alt yer imi eklerim?

 C: Ana yer imine alt yer imi eklemek için yeni bir yer işareti oluşturursunuz.`OutlineItemCollection` alt yer işaretinin nesnesini seçin ve özelliklerini ayarlayın. Daha sonra,`Add` ana yer iminin yöntemi`OutlineItemCollection` alt yer imini ebeveynin koleksiyonuna eklemek için.

#### S: Alt yer imlerinin görünümünü özelleştirebilir miyim?

C: Evet, ana yer imlerine benzer şekilde, başlık, yazı tipi stili ve diğer nitelikler gibi özellikleri ayarlayarak alt yer imlerinin görünümünü özelleştirebilirsiniz. Bu, görsel olarak ayırt edici ve bilgilendirici yer imleri oluşturmanıza olanak tanır.

#### S: Aspose.PDF for .NET diğer programlama dilleriyle uyumlu mudur?

C: Aspose.PDF for .NET, özellikle C# ve .NET ortamları için tasarlanmıştır. Ancak Aspose, Java ve Android gibi diğer programlama dilleri için her biri kendi platformuna göre uyarlanmış benzer kütüphaneler sunmaktadır.

#### S: Alt yer imleri PDF'de gezinmeyi nasıl geliştirir?

C: Alt yer imleri, daha yapılandırılmış ve organize bir içindekiler tablosu sağlayarak PDF'de gezinmeyi geliştirir. Kullanıcılar, hiyerarşik yer imi yapısı sayesinde belgenin belirli bölümlerine hızlı bir şekilde erişebilir.