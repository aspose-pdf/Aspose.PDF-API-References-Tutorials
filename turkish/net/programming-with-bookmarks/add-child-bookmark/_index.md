---
title: PDF Dosyasına Alt Yer İmi Ekle
linktitle: PDF Dosyasına Alt Yer İmi Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile daha düzenli tarama için PDF dosyasına kolayca alt yer imi ekleyin.
type: docs
weight: 20
url: /tr/net/programming-with-bookmarks/add-child-bookmark/
---
PDF dosyasına alt yer imleri eklemek, daha yapılandırılmış bir organizasyona ve gezinmeye olanak tanır. Aspose.PDF for .NET ile aşağıdaki kaynak kodunu takip ederek kolayca bir alt yer imi ekleyebilirsiniz:

## 1. Adım: Gerekli kitaplıkları içe aktarın

Başlamadan önce, C# projeniz için gerekli kitaplıkları içe aktarmanız gerekir. İşte gerekli ithalat yönergesi:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## 2. Adım: Belgeler klasörünün yolunu ayarlayın

 Bu adımda, alt yer imi eklemek istediğiniz PDF dosyasını içeren klasörün yolunu belirtmeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"`belgeler klasörünüzün gerçek yolu ile aşağıdaki kodda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3. Adım: PDF belgesini açın

Şimdi aşağıdaki kodu kullanarak alt yer imi eklemek istediğimiz PDF belgesini açacağız:

```csharp
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
```

## 4. Adım: Üst yer imi nesnesi oluşturun

 Bu adımda, kullanarak bir üst yer imi nesnesi oluşturacağız.`OutlineItemCollection` class ve başlık, italik nitelik ve kalın nitelik gibi özelliklerini ayarlayın. İşte ilgili kod:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent bookmark";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## 5. Adım: Alt Yer İşareti Nesnesi Oluşturun

Bu adımda, kullanarak tekrar bir alt yer işareti nesnesi oluşturacağız.`OutlineItemCollection` sınıf ve özelliklerini ayarlayın. İşte ilgili kod:

```csharp
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Sub Bookmark";
pdfChildOutline. Italic = true;
pdfChildOutline. Bold = true;
```

## 6. Adım: Alt yer imini üst yer imine ekleyin

 Son olarak, oluşturulan alt yer işaretini ana yer işaretinin alt yer işareti koleksiyonuna`Add` üst nesnenin yöntemi. İşte ilgili kod:

```csharp
pdfOutline.Add(pdfChildOutline);
```

## 7. Adım: Ana yer imini belgenin yer imi koleksiyonuna ekleyin

 Son olarak, ana yer imini belgenin yer imi koleksiyonuna şunu kullanarak ekliyoruz:`Add` yöntemi`Outlines` mülk. İşte ilgili kod:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Aspose.PDF for .NET kullanarak Add Child Bookmark için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Belgeyi aç
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
// Bir üst yer imi nesnesi oluşturun
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;      
// Bir alt yer imi nesnesi oluşturun
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Child Outline";
pdfChildOutline.Italic = true;
pdfChildOutline.Bold = true;
// Üst yer imi koleksiyonuna alt yer imi ekle
pdfOutline.Add(pdfChildOutline);
// Belgenin anahat koleksiyonuna ana yer imi ekleyin.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddChildBookmark_out.pdf";
// Çıktıyı kaydet
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmark added successfully.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET ile bir alt yer imi eklemek için adım adım bir kılavuzunuz var. PDF belgelerinizdeki yer imlerinizi düzenlemek ve yapılandırmak için bu kodu kullanabilirsiniz.

Gelişmiş yer imi düzenleme özellikleri hakkında daha fazla bilgi için resmi Aspose.PDF belgelerine baktığınızdan emin olun.

### PDF dosyasına alt yer imi eklemek için SSS

#### S: Bir PDF dosyasındaki alt yer işaretleri nelerdir?

C: Alt yer işaretleri olarak da bilinen alt yer işaretleri, bir üst yer işareti altında hiyerarşik olarak yapılandırılmış bir PDF belgesindeki gezinme öğeleridir. Belge için daha düzenli ve ayrıntılı bir içindekiler tablosu oluşturmanın bir yolunu sağlarlar.

#### S: C# projem için gerekli kitaplıkları nasıl içeri aktarırım?

A: C# projeniz için gerekli kitaplıkları içe aktarmak için aşağıdaki içe aktarma yönergesini kullanabilirsiniz:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Bu kitaplıklar, PDF belgeleri ve etkileşimli özelliklerle çalışmak için gerekli sınıfları ve işlevleri sağlar.

#### S: Belgeler klasörünün yolunu nasıl belirtebilirim?

 A: Sağlanan kaynak kodunda değiştirmeniz gerekir`"YOUR DOCUMENT DIRECTORY"` çalışmak istediğiniz PDF dosyasını içeren klasörün gerçek yolu ile. Bu, kodun hedef PDF dosyasını doğru şekilde bulmasını sağlar.

#### S: Birden çok düzeyde alt yer imi oluşturabilir miyim?

C: Evet, öğreticide belirtilen süreci genişleterek birden çok düzeyde alt yer imi oluşturabilirsiniz. Alt yer imleri ile üst yer imleri oluşturarak ve bunları daha fazla iç içe yerleştirerek, karmaşık PDF belgeleri için yer imlerinin hiyerarşik bir yapısını oluşturabilirsiniz.

####  S: Amacı nedir?`OutlineItemCollection` class?

 C:`OutlineItemCollection` Aspose.PDF for .NET'teki class, temelde bir PDF belgesindeki yer imleri olan ana hatları oluşturmak ve yönetmek için kullanılır. Bu sınıf, yer işaretleri için başlık, yazı tipi stili ve eylemler gibi özellikleri ayarlamanıza olanak tanır.

#### S: Üst yer imine nasıl alt yer imi eklerim?

 C: Bir ana yer imine bir alt yer imi eklemek için yeni bir yer imi oluşturursunuz.`OutlineItemCollection` alt yer imi için nesneyi seçin ve özelliklerini ayarlayın. Ardından,`Add` üst yer iminin yöntemi`OutlineItemCollection` alt yer imini ebeveynin koleksiyonuna eklemek için.

#### S: Alt yer imlerinin görünümünü özelleştirebilir miyim?

C: Evet, ana yer imlerine benzer şekilde, başlık, yazı tipi stili ve diğer nitelikler gibi özellikleri ayarlayarak alt yer imlerinin görünümünü özelleştirebilirsiniz. Bu, görsel olarak ayırt edici ve bilgilendirici yer imleri oluşturmanıza olanak tanır.

#### S: Aspose.PDF for .NET diğer programlama dilleriyle uyumlu mu?

Y: Aspose.PDF for .NET, C# ve .NET ortamları için özel olarak tasarlanmıştır. Ancak Aspose, Java ve Android gibi diğer programlama dilleri için de benzer kütüphaneler sunar ve her biri kendi platformuna göre uyarlanır.

#### S: Alt yer imleri PDF gezinmesini nasıl geliştirir?

C: Alt yer imleri, daha yapılandırılmış ve düzenli bir içindekiler tablosu sağlayarak PDF gezinmesini geliştirir. Kullanıcılar, hiyerarşik yer imi yapısı aracılığıyla belgenin belirli bölümlerine hızlı bir şekilde erişebilir.