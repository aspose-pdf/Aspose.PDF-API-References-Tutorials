---
title: Java kullanarak PDF'ye Döndürülmüş Metin Ekleme
linktitle: Java kullanarak PDF'ye Döndürülmüş Metin Ekleme
second_title: Aspose.PDF Java PDF İşleme API'si
description: Java kullanarak bir PDF belgesine döndürülmüş metin eklemeyi öğrenin. PDF'lerinizi döndürülmüş metinle geliştirmek için kod örnekleriyle bu ayrıntılı adım adım kılavuzu izleyin.
type: docs
weight: 14
url: /tr/java/pdf-page-manipulation/add-rotated-text-in-pdf-using-java/
---

## giriiş

Bu kapsamlı eğitimde, Java kullanarak bir PDF belgesine döndürülmüş metin ekleme sürecini inceleyeceğiz. Diyagramları etiketlemeniz, filigran oluşturmanız veya PDF'lerinize özel efektler eklemeniz gerekip gerekmediğine bakılmaksızın, bu kılavuz sizi adımlarda yönlendirecektir. Süreci göstermek için güçlü bir PDF düzenleme kütüphanesi olan Java için Aspose.PDF'yi kullanacağız.

## Ön koşullar

Başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

1. Java Geliştirme Ortamı: Sisteminizde Java'nın yüklü olduğundan emin olun.

2.  Java için Aspose.PDF: Java projenize Aspose.PDF kütüphanesini indirin ve ekleyin. İndirme bağlantısını bulabilirsiniz[Burada](https://releases.aspose.com/pdf/java/).

## Adım 1: Yeni bir PDF Belgesi Oluşturun

Aspose.PDF kullanarak yeni bir PDF belgesi oluşturarak başlayalım. Bu belge, döndürülmüş metnimiz için tuval görevi görecek.

```java
// PDF belgesini başlat
com.aspose.pdf.Document pdfDocument = new com.aspose.pdf.Document();
```

## Adım 2: Bir Sayfa Ekleyin

Daha sonra, döndürülmüş metni eklemek istediğiniz sayfayı PDF belgesine ekleyin:

```java
//Belgeye yeni bir sayfa ekle
com.aspose.pdf.Page page = pdfDocument.getPages().add();
```

## Adım 3: Döndürülmüş Metni Tanımlayın

Şimdi eklemek ve döndürmek istediğiniz metni tanımlayalım. Metni, yazı tipini ve döndürme açısını ihtiyaçlarınıza göre özelleştirebilirsiniz:

```java
// Metin içeriğini tanımlayın
String text = "Rotated Text Example";

// Bir TextFragment nesnesi oluşturun
com.aspose.pdf.TextFragment textFragment = new com.aspose.pdf.TextFragment(text);

// Yazı tipi boyutunu ve stilini ayarlayın
textFragment.getTextState().setFontSize(12);
textFragment.getTextState().setFont(com.aspose.pdf.FontRepository.findFont("Arial"));

// Dönüş açısını tanımlayın (derece cinsinden)
textFragment.setTextRotation(45);
```

Bu örnekte, metni "Döndürülmüş Metin Örneği" olarak ayarladık, Arial yazı tipini seçtik, yazı tipi boyutunu 12 olarak ayarladık ve metni 45 derece döndürdük. Bu parametreleri özel gereksinimlerinize uyacak şekilde ayarlayın.

## Adım 4: Döndürülmüş Metni Konumlandırın

Döndürülmüş metni yerleştirmek istediğiniz sayfa konumunu belirtin:

```java
// Metnin konumunu ayarlayın
textFragment.setPosition(new com.aspose.pdf.Position(100, 200));
```

Burada metni sayfadaki (100, 200) koordinatlarına yerleştirdik. Metni tam olarak ihtiyacınız olan yere yerleştirmek için bu koordinatları değiştirin.

## Adım 5: Sayfaya Döndürülmüş Metin Ekleyin

Şimdi sayfaya döndürülmüş metni ekleyelim:

```java
// Sayfaya döndürülmüş metin ekleyin
page.getParagraphs().add(textFragment);
```

## Adım 6: PDF'yi kaydedin

Son olarak, döndürülmüş metinle PDF belgesini kaydedin:

```java
// PDF belgesini kaydedin
pdfDocument.save("output.pdf");
```

## Çözüm

Bu eğitimde, Java ve Java için Aspose.PDF kullanarak bir PDF belgesine döndürülmüş metin ekleme sürecini inceledik. Yeni bir PDF oluşturmayı, döndürülmüş metni özel stillerle tanımlamayı, sayfada konumlandırmayı ve değiştirilmiş PDF'yi kaydetmeyi öğrendiniz.

Döndürülmüş metin, diyagramları etiketlemek, filigran eklemek veya belgelerinize yaratıcı öğeler eklemek gibi çeşitli amaçlar için PDF'lerinize değerli bir katkı sağlayabilir.

Aspose.PDF for Java'nın yetenekleri sayesinde, döndürülmüş metni kolayca ekleyerek PDF belgelerinizi geliştirin.

---

## SSS (Sıkça Sorulan Sorular)

### 1. Aynı PDF'deki metni farklı açılardan döndürebilir miyim?
   Evet, aynı PDF belgesine farklı açılara sahip birden fazla döndürülmüş metin örneği ekleyebilirsiniz. Bu eğitimde açıklanan işlemi her bir döndürülmüş metin parçası için tekrarlamanız yeterlidir.

### 2. Döndürülmüş metnin rengini nasıl değiştirebilirim?
    Metin rengini değiştirmek için şunu kullanın:`textFragment.getTextState().setForegroundColor` yöntemini kullanın ve rengi RGB biçiminde belirtin. Örneğin, metin rengini kırmızıya ayarlamak için şunu kullanın:`textFragment.getTextState().setForegroundColor(com.aspose.pdf.Color.getRed());`.

### 3. Aspose.PDF for Java ücretsiz bir kütüphane midir?
   Java için Aspose.PDF güçlü bir ticari kütüphanedir, ancak test ve değerlendirme için ücretsiz bir deneme sürümü sunar. Projenizin gereksinimlerine bağlı olarak uygun bir lisanslama seçeneği seçebilirsiniz.

### 4. Dikey metin oluşturmak için metni 90 derece döndürebilir miyim?
   Evet, dikey metin oluşturmak için metni 90 derece döndürebilirsiniz. Sadece dönüş açısını 90 dereceye ayarlayın ve metin sayfada dikey olarak görünecektir.

### 5. Java'da PDF'lerle çalışmak için başka kütüphaneler var mı?
   Evet, iText ve PDFBox gibi çeşitli kütüphaneler Java'da PDF düzenleme için kullanılabilir. Her kütüphanenin kendine özgü özellikleri ve yetenekleri vardır, bu yüzden projenizin ihtiyaçlarına en uygun olanı seçin.