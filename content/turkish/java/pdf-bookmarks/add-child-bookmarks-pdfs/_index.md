---
title: PDF'lere Çocuk Yer İmleri Ekleme
linktitle: PDF'lere Çocuk Yer İmleri Ekleme
second_title: Aspose.PDF Java PDF İşleme API'si
description: Aspose.PDF for Java'yı kullanarak PDF belgelerini alt yer imleriyle nasıl geliştireceğinizi öğrenin. Gelişmiş gezinme ve organizasyon için kod örnekleri içeren adım adım kılavuz.
type: docs
weight: 11
url: /tr/java/pdf-bookmarks/add-child-bookmarks-pdfs/
---

## PDF'lere Alt Yer İmleri Eklemeye Giriş

Bu makalede Aspose.PDF for Java kullanarak PDF belgelerine alt yer imlerinin nasıl ekleneceğini inceleyeceğiz. Alt yer imleri, bir PDF belgesinin içeriğini düzenlemenin ve gezinmenin kullanışlı bir yoludur; kullanıcıların belge içindeki belirli bölümleri veya konuları bulmasını kolaylaştırır.

## Önkoşullar

Uygulamaya geçmeden önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Sisteminizde kurulu Java geliştirme ortamı.
-  Java kütüphanesi için Aspose.PDF. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/pdf/java/).

## Ortamın Ayarlanması

1. Sağlanan bağlantıdan Aspose.PDF for Java kütüphanesini indirin.
2. Kütüphaneyi Java projenize ekleyin.

Şimdi yeni bir PDF belgesi oluşturup ona adım adım alt yer imleri ekleyerek başlayalım.

## Yeni Bir PDF Belgesi Oluşturma

Başlamak için bir PDF belgesini başlatmamız ve ona sayfalar eklememiz gerekiyor. Başlamak için kod parçacığını burada bulabilirsiniz:

```java
// Bir PDF belgesini başlat
Document pdfDocument = new Document();

// PDF'ye sayfa ekleme
pdfDocument.getPages().add();
pdfDocument.getPages().add();
```

Bu örnekte yeni bir PDF belgesi oluşturduk ve ona iki sayfa ekledik.

## Ana Yer İmlerini Ekleme

Ana yer imleri, PDF belgenizdeki ana bölümler veya kategoriler görevi görür. Bazı ana yer imleri oluşturalım:

```java
// Ebeveyn yer imleri oluşturun
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);
```

"Ebeveyn Yer İmi 1" ve "Ebeveyn Yer İmi 2" olmak üzere iki ana yer imi ekledik.

## Çocuk Yer İmleri Ekleme

Şimdi daha önce oluşturduğumuz ana yer imlerine alt yer imlerini ekleme zamanı geldi. Alt yer imleri, her bir ana yer imindeki belirli konuları veya alt bölümleri temsil eder. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```java
// Alt yer imlerini Ana Yer İşareti 1'e ekleyin
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//Ana Yer İmi 2'ye alt yer imleri ekleyin
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);
```

Hem "Ebeveyn Yer İmi 1"e hem de "Ebeveyn Yer İmi 2"ye alt yer imleri ekledik.

## Yer İşareti Görünümünü Özelleştirme

Yer imlerinin görünümünü, metinlerini ve stillerini değiştirerek özelleştirebilirsiniz. Ayrıca, daha iyi görsel temsil için yer imlerine simgeler ekleyebilirsiniz. İşte bunun nasıl yapılacağına dair bir örnek:

```java
// Yer işareti görünümünü özelleştirin
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());
```

Bu örnekte, ana yer imini italik yaptık, alt yer iminin metin rengini yeşil olarak değiştirdik ve alt yer imine italik bir simge ekledik.

## Olayları Ele Alma

Yer imleri ayrıca kendileriyle ilişkili eylemlere de sahip olabilir. Örneğin, kullanıcı bir yer işaretini tıkladığında tetiklenen eylemler ekleyebilirsiniz. Yer işareti tıklama olaylarını şu şekilde yönetebilirsiniz:

```java
// Yer işaretine eylem ekleme
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);
```

Bu kodda, alt yer imine, tıklandığında kullanıcıyı PDF'nin ikinci sayfasına götürecek bir "Git" eylemi ekledik.

## PDF'yi kaydetme

Gerekli tüm yer işaretlerini ekledikten ve görünümlerini ve eylemlerini özelleştirdikten sonra, değiştirilen PDF belgesini kaydedebilirsiniz:

```java
// PDF belgesini kaydedin
pdfDocument.save("output.pdf");
```

Alt yer işaretlerini içeren PDF belgeniz artık hazır.

## Kaynak Kodunu Tamamlayın

Aspose.PDF for Java kullanarak bir PDF belgesine alt yer imleri eklemek için tam kaynak kodunu burada bulabilirsiniz:

```java
// Bir PDF belgesini başlat
Document pdfDocument = new Document();

// PDF'ye sayfa ekleme
pdfDocument.getPages().add();
pdfDocument.getPages().add();

// Ebeveyn yer imleri oluşturun
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);

// Alt yer imlerini Ana Yer İşareti 1'e ekleyin
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//Ana Yer İmi 2'ye alt yer imleri ekleyin
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);

// Yer işareti görünümünü özelleştirin
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());

// Yer işaretine eylem ekleme
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);

// PDF belgesini kaydedin
pdfDocument.save("output.pdf");
```

## Çözüm

Aspose.PDF for Java kullanarak PDF'lere alt yer imleri eklemek, belgelerinizin gezinmesini ve organizasyonunu geliştiren güçlü bir özelliktir. Bu makalede özetlenen adımları izleyerek, üst ve alt yer işaretleriyle iyi yapılandırılmış PDF'ler oluşturabilir, görünümlerini özelleştirebilir ve hatta kullanıcı deneyimini geliştirmek için eylemler ekleyebilirsiniz.

## SSS'ler

### Aspose.PDF for Java'yı nasıl indirebilirim?

 Aspose.PDF for Java'yı web sitesinden indirebilirsiniz.[Burada](https://releases.aspose.com/pdf/java/).

### Alt yer imleri tüm PDF görüntüleyicilerde destekleniyor mu?

Evet, alt yer imleri çoğu modern PDF görüntüleyicide desteklenir ve PDF belgelerinde gezinmek için gelişmiş bir kullanıcı deneyimi sağlar.

### Yer imlerinin görünümünü daha da özelleştirebilir miyim?

Evet, metin stillerini, renkleri ve simgeleri belgenizin tasarımına uyacak şekilde ayarlayarak yer imlerinin görünümünü özelleştirebilirsiniz.

### Yer imlerine başka hangi eylemleri ekleyebilirim?

"Git" eylemlerinin yanı sıra, web bağlantılarını açmak için "URI" eylemleri veya bir yer işareti tıklandığında özel komut dosyalarını yürütmek için "JavaScript" eylemleri gibi eylemler ekleyebilirsiniz.

### Aspose.PDF for Java ticari projeler için uygun mudur?

Evet, Aspose.PDF for Java, hem kişisel hem de ticari projeler için uygundur ve PDF manipülasyonu ve oluşturulması için çok çeşitli özellikler sunar.