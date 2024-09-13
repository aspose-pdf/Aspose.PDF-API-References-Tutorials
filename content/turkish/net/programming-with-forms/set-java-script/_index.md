---
title: Java Script'i Ayarla
linktitle: Java Script'i Ayarla
second_title: Aspose.PDF for .NET API Referansı
description: .NET için Aspose.PDF'nin gücünü açığa çıkarın. Adım adım kılavuzumuzla form alanlarında JavaScript'i nasıl kuracağınızı öğrenin.
type: docs
weight: 270
url: /tr/net/programming-with-forms/set-java-script/
---
## giriiş

Dinamik ve etkileşimli PDF'ler oluşturmak, özellikle bir belge içinde formlar ve alanlar entegre edildiğinde kullanıcı deneyimini önemli ölçüde iyileştirebilir. Bunu mümkün kılan güçlü bir kütüphane .NET için Aspose.PDF'dir. Bu makalede, Aspose.PDF kullanarak form alanları için JavaScript'i ayarlamaya derinlemesine dalacağız ve PDF'lerinizin yalnızca iyi görünmesini değil, aynı zamanda güzel bir şekilde çalışmasını sağlayacağız.

## Ön koşullar

Kodlamaya başlamadan önce, sorunsuz bir şekilde takip edebilmeniz için ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:

- Visual Studio (veya herhangi bir .NET IDE): Yüklediğinizden ve doğru şekilde ayarladığınızdan emin olun.
  
-  Aspose.PDF Kütüphanesi: Bu kütüphanenin en son sürümünü isteyeceksiniz. İndirebilirsiniz[Burada](https://releases.aspose.com/pdf/net/).

- Temel C# Bilgisi: C# programlamaya aşinalık, kod parçacıklarını daha iyi anlamanıza yardımcı olacaktır.

-  PDF Dosyaları: Test için hazır bir PDF dosyanız olmalı. Örneğimizde, şu adlı bir dosya kullanacağız:`SetJavaScript.pdf`.

- Belge Dizininiz: Belge dosyalarınızın nerede saklandığını bilin. Bu yola kodumuzda referans vereceğiz.

Bu ön koşullar hazır olduğunda, hangi araçları kullanacağız? Aspose.PDF'in neler yapabileceğini inceleyelim.

## Paketleri İçe Aktar

Başlamak için, C# projenize gerekli ad alanlarını eklemeniz gerekir. Ana C# dosyanızı açın ve aşağıdaki içe aktarma ifadelerini ekleyin:

```csharp
using System;
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

Bu ad alanları, Aspose.PDF kitaplığındaki PDF ve formla ilgili işlevlere erişim sağlar.

PDF'nizi etkileşimli hale getirmeye hazır mısınız? Kodlama şapkanızı alın ve bunu adım adım inceleyelim!

## Adım 1: Belge Yolunu Tanımlayın

Öncelikle PDF dosyamızın konumunu belirtmemiz gerekiyor. Bu, takip eden her şey için ortamı hazırlar. İşte bunu nasıl yapacağınız:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` PDF dosyanızın bulunduğu gerçek yol ile. Bunu bir hazine haritası için koordinatları ayarlamak olarak düşünün—'X'in yeri işaretlediği yeri bilmeniz gerekir!

## Adım 2: PDF Belgesini Yükleyin

Dizini tanımladıktan sonra PDF dosyamızı yükleyeceğiz. 

```csharp
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Bu satır belirttiğiniz PDF dosyasını açar ve düzenlemeye hazırlar. 

## Adım 3: Form Alanına Erişim

Daha sonra JavaScript'imizi uygulayacağımız form alanına erişmek istiyoruz. 

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

 Burada, PDF'nizde adında bir metin kutusu olduğunu varsayıyoruz`textbox1`Eğer bu isimde bir alanınız yoksa, ya adını değiştirebilir ya da kodu buna göre ayarlayabilirsiniz. 

## Adım 4: JavaScript Eylemlerini Ayarlayın

Şimdi, metin kutumuza biraz işlevsellik ekleyelim! Belirli olaylarda tetiklenecek JavaScript eylemleri ayarlayacağız. 

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

İşte olanlar:
- OnModifyCharacter: Bu JavaScript işlevi, bir karakter değiştirildiğinde alanın nasıl davranması gerektiğini belirtir. Bu durumda, ayırıcı olmadan sayıdan sonra iki ondalık noktaya izin verir.
- OnFormat: Kullanıcı sayıyı biçimlendirdiğinde aynı kurala uyulmasını sağlar.

Bu eylemleri ayarlayarak, aslında metin kutumuza bir kişilik kazandırıyoruz; ona bir dans hareketi öğretiyoruz!

## Adım 5: Alan Değerini Başlatın

Şimdi metin kutumuza bir başlangıç değeri atayarak bir başlangıç noktası verelim. 

```csharp
field.Value = "123";
```

Bu satır, metin kutusunda önceden doldurulmuş değeri "123" olarak ayarlar. Bu, bir performans için sahneyi hazırlamak gibidir.

## Adım 6: Değiştirilen PDF'yi Kaydedin

Son olarak tüm bu değişiklikleri yaptıktan sonra belgemizi kaydetmemiz gerekiyor.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
doc.Save(dataDir);
```

 Bu, orijinal dosyayı değişikliklerinizle günceller ve kaydeder`Restricted_out.pdf`Bunu PDF'imizin kaderini mühürlemek olarak düşünün; bir kez kaydedildiğinde, dünyaya açılmaya hazırdır!

## Adım 7: Başarıyı Onaylayın

Son olarak her şeyin yolunda gidip gitmediğini kontrol edelim. 

```csharp
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

Bu mesajı çalıştırmak, harika bir performansın ardından seyircilerden alkış almak gibi, operasyonun başarıyla tamamlandığına dair sizi rahatlatacaktır.

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF'deki form alanları için JavaScript'i başarıyla ayarladınız. Bu eğitim size yalnızca kullanıcı etkileşimini geliştirmek için araçlar sağlamakla kalmadı, aynı zamanda belgelerinizi bir profesyonel gibi kişiselleştirmenize de olanak tanıdı. İster faturalardaki, anketlerdeki veya diğer etkileşimli PDF'lerdeki formlarla çalışın, olasılıklar gerçekten sonsuzdur.

### SSS

### Aspose.PDF for .NET nedir?  
Aspose.PDF, .NET uygulamaları içerisinde PDF dosyaları oluşturmak, düzenlemek ve işlemek için tasarlanmış, güçlü PDF işlevleri sağlayan bir kütüphanedir.

### Aspose.PDF'i kullanmak için lisansa ihtiyacım var mı?  
 Ücretsiz deneme mevcut olsa da, sınırlama olmaksızın tam kullanım için bir lisans gereklidir. Bir lisans satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).

### Diğer form alanlarına JavaScript ayarlayabilir miyim?  
Kesinlikle! Aspose.PDF, onay kutuları, radyo düğmeleri ve açılır listeler gibi çeşitli form alanlarında JavaScript eylemlerine izin verir.

### Aspose.PDF sorunları için nasıl destek alabilirim?  
 Desteklerine şu adreslerden ulaşabilirsiniz:[forum](https://forum.aspose.com/c/pdf/10) Herhangi bir soru veya sorun için.

### Aspose.PDF'yi satın almadan test etmenin bir yolu var mı?  
Evet! Aspose bir[ücretsiz deneme](https://releases.aspose.com/) Satın alma işlemine başlamadan önce kütüphanenin özelliklerini test etmek.