---
title: PDF Dosyasında Görünmez Açıklama
linktitle: PDF Dosyasında Görünmez Açıklama
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF dosyasına görünmez bir açıklama eklemeyi öğrenin. Bu güçlü özelliği ustalıkla kullanmak için adım adım kılavuzumuzu izleyin.
type: docs
weight: 100
url: /tr/net/annotations/invisibleannotation/
---
## giriiş

PDF dosyalarınıza görünmez ama etkili notlar eklemek istediniz mi? İster yazdırma amaçlı notlar eklemek isteyin, ister belgelerinizde gizli bir mesaj bırakmak isteyin, görünmez notlar inanılmaz derecede faydalı olabilir. Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF dosyasında görünmez bir not oluşturma sürecinde size rehberlik edeceğiz. Bu güçlü .NET kitaplığı, PDF belgelerini kolaylıkla düzenlemenizi sağlar ve bu kılavuzun sonunda, PDF dosyalarınıza görünmez notlar ekleme sanatında bir profesyonel gibi ustalaşmış olacaksınız!

## Ön koşullar

Adımlara geçmeden önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

- .NET için Aspose.PDF: Aspose.PDF kütüphanesinin yüklü olduğundan emin olun. Buradan indirebilirsiniz[Burada](https://releases.aspose.com/pdf/net/).
- .NET Geliştirme Ortamı: Visual Studio veya tercih ettiğiniz herhangi bir .NET geliştirme ortamının yüklü olması gerekir.
- Temel C# Bilgisi: C# sözdizimi ve programlamanın anlaşılması esastır.
-  Geçerli Bir Lisans veya Ücretsiz Deneme: Lisansınız yoksa, geçici bir lisans alabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/) veya ücretsiz deneme sürümünü kullanın.

## Paketleri İçe Aktar

Başlamak için gerekli ad alanlarını içe aktarmanız gerekir. Bu ad alanları, .NET için Aspose.PDF'de PDF belgeleriyle çalışmak için gereken sınıflara ve yöntemlere erişmenizi sağlayacaktır.

```csharp
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
using System;
```

Artık ön koşulları tamamladığımıza göre, PDF belgesine görünmez bir açıklama ekleme sürecini yönetilebilir adımlara bölelim.

## Adım 1: Belge Dizinini Ayarlayın

Öncelikle, giriş PDF dosyanızın bulunduğu belge dizininize giden yolu belirtmeniz gerekir. Bu yol, PDF belgesini programa yüklemek için kullanılacaktır.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
 
 The`dataDir`değişkeni PDF dosyalarınızın saklandığı dizine giden yolu tutar. Değiştirdiğinizden emin olun`"YOUR DOCUMENT DIRECTORY"` makinenizdeki gerçek yol ile.

## Adım 2: PDF Belgesini Yükleyin

Sonra, PDF belgesini programımıza yükleyeceğiz. Bu belge, görünmez açıklamayı ekleyeceğimiz belgedir.

```csharp
// Belgeyi aç
Document doc = new Document(dataDir + "input.pdf");
```
 
 Burada şunu kullanıyoruz:`Document` adlı PDF dosyasını açmak için Aspose.PDF kitaplığından sınıf`input.pdf`Bu dosyanın önceki adımda belirttiğiniz dizinde bulunduğundan emin olun.

## Adım 3: Görünmez Açıklamayı Oluşturun

 Şimdi heyecan verici kısma geliyoruz: görünmez açıklamayı oluşturmak.`FreeTextAnnotation` PDF belgesinin ilk sayfasına serbest metin açıklaması eklemek için kullanılan sınıf.

```csharp
FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
annotation.Contents = "ABCDEFG";
annotation.Characteristics.Border = System.Drawing.Color.Red;
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);
```

-  Yeni bir şey yaratıyoruz`FreeTextAnnotation` ve sayfayı belirtin (`doc.Pages[1]` ) eklenmesi gereken yer.`Rectangle` sınıf, açıklamanın sayfada yerleştirileceği alanı tanımlar.
-  The`DefaultAppearance` sınıf, açıklama için yazı tipini, yazı tipi boyutunu ve rengini ayarlamak için kullanılır. Bu örnekte, "Helvetica" yazı tipini, 16 boyutunu ve kırmızı rengi seçtik.
-  The`Contents`mülk, açıklamanın metnini tutar, burada ayarlanmıştır`"ABCDEFG"`.
-  The`Characteristics.Border` özellik, açıklamanın kenarlık rengini tanımlar, yine kırmızı olarak ayarlanır.
-  The`Flags` mülk şunları içerir`AnnotationFlags.Print` belge yazdırıldığında açıklamanın görünür olmasını sağlamak ve`AnnotationFlags.NoView` normal görüntüleme sırasında görünmez hale getirmek için.
-  Son olarak, PDF belgesinin ilk sayfasına açıklamayı şu şekilde ekliyoruz:`Annotations.Add` Yöntem.

## Adım 4: Güncellenen PDF Belgesini Kaydedin

Açıklama başarıyla eklendikten sonraki adım güncellenen PDF belgesini kaydetmektir.

```csharp
dataDir = dataDir + "InvisibleAnnotation_out.pdf";
// Çıktı dosyasını kaydet
doc.Save(dataDir);
```

 Biz değiştiriyoruz`dataDir` çıktı dosya adını belirtmek için değişken,`"InvisibleAnnotation_out.pdf"` .`Save` yöntem daha sonra güncellenen PDF belgesini görünmez açıklama ile belirtilen dizine kaydeder.

## Adım 5: İşlemin Tamamlandığını Onaylayın

Son olarak, sürecin başarıyla tamamlandığının onayını sağlamak her zaman iyi bir uygulamadır. Bu amaçla basit bir konsol çıktısı ekleyeceğiz.

```csharp
Console.WriteLine("\nAnnotation invisible successfully.\nFile saved at " + dataDir);
```

Bu satır konsola bir onay mesajı çıktısı verir, görünmez açıklamanın başarıyla eklendiğini bildirir ve kaydedilen dosyanın konumunu gösterir.

## Çözüm

Ve işte oldu! Aspose.PDF for .NET kullanarak bir PDF dosyasına görünmez bir açıklama eklemeyi başardınız. Bu eğitim, ortamınızı kurmaktan son belgeyi kaydetmeye kadar her adımda size yol gösterdi. Gizli mesajlar veya yazdırma amaçlı açıklamalar ekliyor olun, görünmez açıklamalar Aspose.PDF for .NET kullanarak kolayca uygulayabileceğiniz güçlü bir özelliktir. İyi kodlamalar!

## SSS

### Açıklamayı tekrar görünür hale getirebilir miyim?  
 Evet, kaldırarak`AnnotationFlags.NoView` bayrağını kullanarak, açıklamayı normal görüntüleme sırasında görünür hale getirebilirsiniz.

### Aspose.PDF kullanarak başka hangi tür açıklamaları ekleyebilirim?  
Aspose.PDF, metin, bağlantı, vurgulama ve damga açıklamaları da dahil olmak üzere çeşitli açıklamaları destekler.

### Eklenen açıklamayı daha sonra değiştirmek mümkün müdür?  
Evet, bir açıklamanın özelliklerini, açıklama belgeye eklendikten sonra bile değiştirebilirsiniz.

### Aynı belgeye birden fazla açıklama nasıl ekleyebilirim?  
Eklemek istediğiniz her açıklama için açıklama oluşturma sürecini tekrarlayın. Her açıklama aynı veya farklı sayfalara eklenebilir.

### PDF belgemin birden fazla sayfası varsa ne olur?  
 Açıklamayı oluştururken sayfa numarasını değiştirerek belirtebilirsiniz.`doc.Pages[1]` istenilen sayfa indeksine.