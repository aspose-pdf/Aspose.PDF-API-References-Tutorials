---
title: Java kullanarak PDF Dosyasına Metin Damgası Ekleme
linktitle: Java kullanarak PDF Dosyasına Metin Damgası Ekleme
second_title: Aspose.PDF Java PDF İşleme API'si
description: Aspose.PDF for Java ile Java kullanarak PDF dosyalarına nasıl metin damgası ekleyeceğinizi öğrenin. PDF belgelerinizi zahmetsizce özelleştirin.
type: docs
weight: 10
url: /tr/java/pdf-form-fields/adding-text-stamp-in-pdf-file-using-java/
---

## Java Kullanarak PDF Dosyasına Metin Damgası Eklemeye Giriş

Dijital belge dünyasında PDF dosyaları önemli bir rol oynamaktadır. Bilgi paylaşımı ve içeriğin bütünlüğünü korumak için yaygın olarak kullanılırlar. Çoğu durumda, PDF dosyasına damga, filigran veya açıklama gibi ek bilgilerin eklenmesi zorunlu hale gelir. Bu yazıda Aspose.PDF for Java'nın yardımıyla Java programlamayı kullanarak bir PDF dosyasına nasıl metin damgası ekleneceğini inceleyeceğiz.

## Önkoşullar

Kodlama kısmına geçmeden önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

- Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
- Java için Entegre Geliştirme Ortamı (IDE) (Eclipse, IntelliJ IDEA, vb.).
-  Java kütüphanesi için Aspose.PDF. İndirebilirsin[Burada](https://releases.aspose.com/pdf/java/).

## Java Projenizi Kurma

1. Tercih ettiğiniz IDE'de yeni bir Java projesi oluşturun.
2. Aspose.PDF for Java kütüphanesini projenizin derleme yoluna ekleyin.

## PDF Belgesi Oluşturma

Aspose.PDF for Java'yı kullanarak yeni bir PDF belgesi oluşturarak başlayalım.

```java
import com.aspose.pdf.Document;

public class Main {
    public static void main(String[] args) {
        // Yeni bir PDF belgesi oluştur
        Document pdfDocument = new Document();
        
        // Belgeye sayfa ekleme
        pdfDocument.getPages().add();
        
        // Belgeyi kaydet
        pdfDocument.save("output.pdf");
    }
}
```

Bu kod parçasında Aspose.PDF kütüphanesinden gerekli sınıfları içe aktarıyoruz, yeni bir PDF belgesi oluşturuyoruz, ona bir sayfa ekliyoruz ve bunu "output.pdf" adıyla kaydediyoruz.

## Metin Damgası Ekleme

Şimdi PDF belgemize metin damgası eklemeye devam edelim. Belgeyi taslak filigran veya gizli etiket gibi önemli bilgilerle işaretlemek için metin damgası kullanılabilir.

```java
import com.aspose.pdf.*;
import com.aspose.pdf.facades.*;

public class Main {
    public static void main(String[] args) {
        // Yeni bir PDF belgesi oluştur
        Document pdfDocument = new Document();
        
        // Belgeye sayfa ekleme
        pdfDocument.getPages().add();
        
        // TextStamp nesnesi oluşturma
        TextStamp textStamp = new TextStamp("Confidential");
        textStamp.getTextState().setFont(FontRepository.findFont("Arial"));
        textStamp.getTextState().setFontSize(18);
        textStamp.getTextState().setForegroundColor(Color.getRed());
        
        // Metin damgasını sayfaya ekleyin
        pdfDocument.getPages().get_Item(1).addStamp(textStamp);
        
        // Belgeyi kaydet
        pdfDocument.save("stamped_document.pdf");
    }
}
```

 Bu kodda öncelikle bir tane oluşturuyoruz.`TextStamp` "Gizli" metnini içeren nesne. Yazı tipini, yazı tipi boyutunu ve ön plan rengini özelleştiriyoruz. Daha sonra metin damgasını PDF belgemizin ilk sayfasına ekliyoruz. Son olarak belgeyi "damgalı_document.pdf" olarak kaydediyoruz.

## Çözüm

Bu makalede, Java ve Aspose.PDF for Java kullanarak bir PDF dosyasına nasıl metin damgası ekleyeceğimizi öğrendik. Bu, belgeleri etiketlemek, taslak olarak işaretlemek veya önemli açıklamalar eklemek gibi çeşitli amaçlar için yararlı olabilir. Aspose.PDF for Java, PDF dosyalarını programlı olarak işlemek için güçlü ve esnek bir yol sunarak, içerikleri üzerinde tam kontrol sahibi olmanızı sağlar.

Artık PDF belgelerinizi Java'daki metin damgalarıyla geliştirecek bilgi ve araçlara sahipsiniz. Özel ihtiyaçlarınızı karşılayan damgalar oluşturmak için farklı metin, yazı tipleri ve renklerle denemeler yapın.

## SSS'ler

### PDF'deki metin damgasının konumunu nasıl değiştiririm?

 PDF'deki metin damgasının konumunu değiştirmek için,`XIndent` Ve`YIndent` özellikler. Bu özellikler damganın sayfadaki yatay ve dikey konumunu belirler.

```java
textStamp.setXIndent(100);
textStamp.setYIndent(200);
```

### Metne ek olarak özel görselleri damga olarak ekleyebilir miyim?

 Evet, Aspose.PDF for Java'yı kullanarak metne ek olarak damga olarak özel görseller ekleyebilirsiniz. Bir oluşturabilirsiniz`ImageStamp`ve resim dosyanızla özelleştirin.

### Aspose.PDF for Java'nın kullanımı ücretsiz midir?

Aspose.PDF for Java ticari bir kütüphanedir ve üretim ortamında kullanım için geçerli bir lisans gerektirir. Ancak deneme modunda ücretsiz olarak deneyebilirsiniz.

### PDF'deki metin damgasını nasıl döndürebilirim?

 PDF'deki metin damgasını döndürmek için`setRotate` yöntemi`TextStamp` sınıf. Örneğin damgayı 45 derece döndürmek için:

```java
textStamp.setRotation(45);
```

### Aspose.PDF for Java ile ilgili daha fazla belge ve örneği nerede bulabilirim?

 Aspose.PDF for Java ile ilgili kapsamlı belgeleri ve örnekleri dokümantasyon web sitesinde bulabilirsiniz:[Java Belgelendirmesi için Aspose.PDF](https://reference.aspose.com/pdf/java/).