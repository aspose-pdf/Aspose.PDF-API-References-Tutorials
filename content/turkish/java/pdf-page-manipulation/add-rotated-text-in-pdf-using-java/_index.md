---
title: Java kullanarak PDF'ye Döndürülmüş Metin Ekleme
linktitle: Java kullanarak PDF'ye Döndürülmüş Metin Ekleme
second_title: Aspose.PDF Java PDF İşleme API'si
description: Java kullanarak bir PDF belgesine döndürülmüş metni nasıl ekleyeceğinizi öğrenin. PDF'lerinizi döndürülmüş metinle geliştirmek için kod örnekleri içeren bu ayrıntılı adım adım kılavuzu izleyin.
type: docs
weight: 14
url: /tr/java/pdf-page-manipulation/add-rotated-text-in-pdf-using-java/
---

## giriiş

Bu kapsamlı eğitimde, Java kullanarak bir PDF belgesine döndürülmüş metin ekleme sürecini derinlemesine inceleyeceğiz. Diyagramları etiketlemeniz, filigran oluşturmanız veya PDF'lerinize özel efektler eklemeniz gerekiyorsa, bu kılavuz size adımlarda yol gösterecektir. Süreci göstermek için, PDF işlemeye yönelik güçlü bir kütüphane olan Aspose.PDF for Java'yı kullanacağız.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1. Java Geliştirme Ortamı: Sisteminizde Java'nın kurulu olduğundan emin olun.

2.  Aspose.PDF for Java: Aspose.PDF kütüphanesini indirin ve Java projenize ekleyin. İndirme linkini bulabilirsiniz[Burada](https://releases.aspose.com/pdf/java/).

## 1. Adım: Yeni Bir PDF Belgesi Oluşturun

Aspose.PDF kullanarak yeni bir PDF belgesi oluşturarak başlayalım. Bu belge döndürülen metnimiz için tuval görevi görecek.

```java
// PDF belgesini başlat
com.aspose.pdf.Document pdfDocument = new com.aspose.pdf.Document();
```

## 2. Adım: Sayfa Ekle

Ardından, PDF belgesine döndürülen metni eklemek istediğiniz sayfayı ekleyin:

```java
//Belgeye yeni bir sayfa ekleme
com.aspose.pdf.Page page = pdfDocument.getPages().add();
```

## 3. Adım: Döndürülmüş Metni Tanımlayın

Şimdi eklemek ve döndürmek istediğiniz metni tanımlayalım. Metni, yazı tipini ve döndürme açısını gereksinimlerinize göre özelleştirebilirsiniz:

```java
// Metin içeriğini tanımlayın
String text = "Rotated Text Example";

// TextFragment nesnesi oluşturma
com.aspose.pdf.TextFragment textFragment = new com.aspose.pdf.TextFragment(text);

// Yazı tipi boyutunu ve stilini ayarlama
textFragment.getTextState().setFontSize(12);
textFragment.getTextState().setFont(com.aspose.pdf.FontRepository.findFont("Arial"));

// Dönme açısını tanımlayın (derece cinsinden)
textFragment.setTextRotation(45);
```

Bu örnekte metni "Döndürülmüş Metin Örneği" olarak ayarladık, Arial yazı tipini seçtik, yazı tipi boyutunu 12 olarak ayarladık ve metni 45 derece döndürdük. Bu parametreleri özel gereksinimlerinize uyacak şekilde ayarlayın.

## Adım 4: Döndürülmüş Metni Konumlandırın

Sayfada döndürülen metni yerleştirmek istediğiniz konumu belirtin:

```java
// Metnin konumunu ayarlayın
textFragment.setPosition(new com.aspose.pdf.Position(100, 200));
```

Burada metni sayfadaki koordinatlara (100, 200) konumlandırdık. Metni tam olarak ihtiyacınız olan yere yerleştirmek için bu koordinatları değiştirin.

## Adım 5: Sayfaya Döndürülmüş Metin Ekleme

Şimdi döndürülen metni sayfaya ekleyin:

```java
// Döndürülmüş metni sayfaya ekleme
page.getParagraphs().add(textFragment);
```

## Adım 6: PDF'yi kaydedin

Son olarak, PDF belgesini döndürülmüş metinle kaydedin:

```java
// PDF belgesini kaydedin
pdfDocument.save("output.pdf");
```

## Çözüm

Bu eğitimde, Java ve Aspose.PDF for Java kullanarak bir PDF belgesine döndürülmüş metin ekleme sürecini inceledik. Yeni bir PDF oluşturmayı, döndürülmüş metni özel stillerle tanımlamayı, sayfada konumlandırmayı ve değiştirilen PDF'yi kaydetmeyi öğrendiniz.

Döndürülmüş metin, diyagramları etiketlemek, filigran eklemek veya belgelerinize yaratıcı öğeler eklemek gibi çeşitli amaçlarla PDF'lerinize değerli bir katkı olabilir.

Aspose.PDF for Java'nın yetenekleri sayesinde, döndürülmüş metinleri kolaylıkla ekleyerek PDF belgelerinizi geliştirin.

---

## SSS (Sık Sorulan Sorular)

### 1. Aynı PDF'de metni farklı açılardan döndürebilir miyim?
   Evet, aynı PDF belgesine farklı açılara sahip birden fazla döndürülmüş metin örneği ekleyebilirsiniz. Döndürülmüş her metin parçası için bu eğitimde açıklanan işlemi tekrarlamanız yeterlidir.

### 2. Döndürülmüş metnin rengini nasıl değiştirebilirim?
    Metin rengini değiştirmek için`textFragment.getTextState().setForegroundColor` yöntemini seçin ve rengi RGB formatında belirtin. Örneğin, metin rengini kırmızıya ayarlamak için şunu kullanın:`textFragment.getTextState().setForegroundColor(com.aspose.pdf.Color.getRed());`.

### 3. Aspose.PDF for Java ücretsiz bir kütüphane midir?
   Aspose.PDF for Java güçlü bir ticari kütüphanedir, ancak test ve değerlendirme için ücretsiz deneme sürümü de sunar. Projenizin gereksinimlerine bağlı olarak uygun bir lisanslama seçeneği belirleyebilirsiniz.

### 4. Dikey metin oluşturmak için metni 90 derece döndürebilir miyim?
   Evet, dikey metin oluşturmak için metni 90 derece döndürebilirsiniz. Döndürme açısını 90 dereceye ayarlamanız yeterlidir; metin sayfada dikey olarak görünecektir.

### 5. Java'da PDF'lerle çalışmak için başka kütüphaneler var mı?
   Evet, Java'da PDF işleme için iText ve PDFBox gibi çeşitli kitaplıklar mevcuttur. Her kitaplığın kendine özgü özellikleri ve yetenekleri vardır; bu nedenle projenizin ihtiyaçlarına en uygun olanı seçin.