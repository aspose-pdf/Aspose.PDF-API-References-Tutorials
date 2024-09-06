---
title: PDF'lere Çocuk Yer İşaretleri Ekle
linktitle: PDF'lere Çocuk Yer İşaretleri Ekle
second_title: Aspose.PDF Java PDF İşleme API'si
description: Java için Aspose.PDF kullanarak PDF belgelerini alt yer imleriyle nasıl geliştireceğinizi öğrenin. Gelişmiş gezinme ve organizasyon için kod örnekleriyle adım adım kılavuz.
type: docs
weight: 11
url: /tr/java/pdf-bookmarks/add-child-bookmarks-pdfs/
---

## PDF'lere Çocuk Yer İşaretleri Eklemeye Giriş

Bu makalede, Java için Aspose.PDF kullanarak PDF belgelerine alt yer imlerinin nasıl ekleneceğini inceleyeceğiz. Alt yer imleri, bir PDF belgesinin içeriğini düzenlemenin ve içinde gezinmenin kullanışlı bir yoludur ve kullanıcıların belge içindeki belirli bölümleri veya konuları bulmasını kolaylaştırır.

## Ön koşullar

Uygulamaya geçmeden önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

- Sisteminizde yüklü Java geliştirme ortamı.
-  Java kütüphanesi için Aspose.PDF. Buradan indirebilirsiniz[Burada](https://releases.aspose.com/pdf/java/).

## Ortamın Kurulması

1. Verilen bağlantıdan Aspose.PDF for Java kütüphanesini indirin.
2. Kütüphaneyi Java projenize ekleyin.

Şimdi yeni bir PDF belgesi oluşturup, ona adım adım alt yer imleri ekleyerek başlayalım.

## Yeni Bir PDF Belgesi Oluşturma

Başlamak için bir PDF belgesi başlatmamız ve ona sayfalar eklememiz gerekiyor. Başlamak için kod parçacığı şu şekilde:

```java
// Bir PDF belgesini başlat
Document pdfDocument = new Document();

// PDF'ye sayfa ekle
pdfDocument.getPages().add();
pdfDocument.getPages().add();
```

Bu örnekte yeni bir PDF belgesi oluşturduk ve buna iki sayfa ekledik.

## Ebeveyn Yer İşaretleri Ekleme

Üst yer imleri PDF belgenizdeki ana bölümler veya kategoriler olarak hizmet eder. Bazı üst yer imleri oluşturalım:

```java
// Ana yer imleri oluştur
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);
```

İki adet üst yer imi ekledik: "Üst Yer İmi 1" ve "Üst Yer İmi 2."

## Çocuk Yer İşaretleri Ekleme

Şimdi, daha önce oluşturduğumuz ana yer imlerine alt yer imleri ekleme zamanı. Alt yer imleri, her ana yer imi içindeki belirli konuları veya alt bölümleri temsil eder. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```java
// Ana Yer İmi 1'e çocuk yer imleri ekle
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//Çocuk yer imlerini Ana Yer İmi 2'ye ekle
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);
```

Hem "Üst Yer İmi 1"e hem de "Üst Yer İmi 2"ye alt yer imleri ekledik.

## Yer İşareti Görünümünü Özelleştirme

Yer imlerinin görünümünü, metinlerini ve stillerini değiştirerek özelleştirebilirsiniz. Ayrıca, daha iyi görsel temsil için yer imlerine simgeler ekleyebilirsiniz. İşte bunu nasıl yapacağınıza dair bir örnek:

```java
// Yer imi görünümünü özelleştir
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());
```

Bu örnekte, üst yer imini italik yaptık, alt yer iminin metin rengini yeşil olarak değiştirdik ve alt yer imine italik bir simge ekledik.

## Olayların Yönetimi

Yer imleri ayrıca bunlarla ilişkili eylemlere de sahip olabilir. Örneğin, bir kullanıcı bir yer imine tıkladığında tetiklenen eylemler ekleyebilirsiniz. Yer imi tıklama olaylarını şu şekilde işleyebilirsiniz:

```java
// Bir yer imine bir eylem ekleyin
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);
```

Bu kodda, tıklandığında kullanıcıyı PDF'nin ikinci sayfasına götürecek bir "Git" eylemini bir alt yer imine ekledik.

## PDF'yi kaydetme

Gerekli tüm yer imlerini ekledikten ve görünümlerini ve eylemlerini özelleştirdikten sonra, değiştirilmiş PDF belgesini kaydedebilirsiniz:

```java
// PDF belgesini kaydedin
pdfDocument.save("output.pdf");
```

Çocuk yer imleri içeren PDF belgeniz artık hazır.

## Tam Kaynak Kodu

İşte Java için Aspose.PDF'yi kullanarak bir PDF belgesine alt yer imleri eklemeye yönelik eksiksiz kaynak kodu:

```java
// Bir PDF belgesini başlat
Document pdfDocument = new Document();

// PDF'ye sayfa ekle
pdfDocument.getPages().add();
pdfDocument.getPages().add();

// Ana yer imleri oluştur
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);

// Ana Yer İmi 1'e çocuk yer imleri ekle
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//Çocuk yer imlerini Ana Yer İmi 2'ye ekle
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);

// Yer imi görünümünü özelleştir
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());

// Bir yer imine bir eylem ekleyin
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);

// PDF belgesini kaydedin
pdfDocument.save("output.pdf");
```

## Çözüm

Aspose.PDF for Java kullanarak PDF'lere alt yer imleri eklemek, belgelerinizin gezinmesini ve organizasyonunu geliştiren güçlü bir özelliktir. Bu makalede özetlenen adımları izleyerek, ana ve alt yer imleriyle iyi yapılandırılmış PDF'ler oluşturabilir, görünümlerini özelleştirebilir ve hatta kullanıcı deneyimini geliştirmek için eylemler ekleyebilirsiniz.

## SSS

### Java için Aspose.PDF'yi nasıl indirebilirim?

 Java için Aspose.PDF'yi web sitesinden indirebilirsiniz[Burada](https://releases.aspose.com/pdf/java/).

### Tüm PDF görüntüleyicilerinde çocuk yer imleri destekleniyor mu?

Evet, çocuk yer imleri çoğu modern PDF görüntüleyicisinde desteklenir ve PDF belgelerinde gezinmek için gelişmiş bir kullanıcı deneyimi sağlar.

### Yer imlerinin görünümünü daha fazla özelleştirebilir miyim?

Evet, metin stillerini, renkleri ve simgeleri belgenizin tasarımına uyacak şekilde ayarlayarak yer imlerinin görünümünü özelleştirebilirsiniz.

### Yer imlerine başka hangi eylemleri ekleyebilirim?

"GoTo" eylemlerinin yanı sıra, web bağlantılarını açmak için "URI" eylemleri veya bir yer işaretine tıklandığında özel komut dosyalarını çalıştırmak için "JavaScript" eylemleri gibi eylemler ekleyebilirsiniz.

### Aspose.PDF for Java ticari projeler için uygun mudur?

Evet, Aspose.PDF for Java hem kişisel hem de ticari projeler için uygundur ve PDF düzenleme ve oluşturma için geniş bir özellik yelpazesi sunar.