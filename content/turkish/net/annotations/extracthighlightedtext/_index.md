---
title: PDF Dosyasındaki Vurgulanan Metni Çıkar
linktitle: PDF Dosyasındaki Vurgulanan Metni Çıkar
second_title: Aspose.PDF for .NET API Referansı
description: Bu eğitimle Aspose.PDF for .NET kullanarak bir PDF dosyasından vurgulanan metni etkili bir şekilde nasıl çıkaracağınızı öğrenin. Veri analizi ve içerik incelemesi için mükemmeldir.
type: docs
weight: 60
url: /tr/net/annotations/extracthighlightedtext/
---
## giriiş

PDF dosyalarıyla çalışırken, vurgulanan metni çıkarmak, ister veri analizi, ister içerik incelemesi veya sadece notlarınızı düzenlemek için olsun, önemli bir görev olabilir. Aspose.PDF for .NET kullanıyorsanız, bu işlem basit ve etkilidir. Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesinden vurgulanan metni nasıl çıkaracağınızı göstereceğiz. Ön koşullardan adım adım kılavuza kadar her şeyi ele alacağız ve sonunda kapsamlı bir anlayışa sahip olmanızı sağlayacağız.

## Ön koşullar

Koda dalmadan önce, yerinde olması gereken birkaç şey var:

-  .NET Kütüphanesi için Aspose.PDF: Aspose.PDF kütüphanesinin yüklü olduğundan emin olun. Değilse, şuradan indirebilirsiniz:[yayın sayfası](https://releases.aspose.com/pdf/net/).
- Geliştirme Ortamı: Visual Studio gibi çalışan bir geliştirme ortamı kurmuş olmanız gerekir.
- Temel C# Bilgisi: C# programlama dili ve nesne yönelimli programlamaya aşinalık şarttır.
-  Geçerli Bir Aspose Lisansı: Ücretsiz bir denemeyle başlayabilmenize rağmen, bir Aspose Lisansı edinmeyi düşünün.[geçici lisans](https://purchase.aspose.com/temporary-license/) veya bir tane satın almak[Burada](https://purchase.aspose.com/buy) sınırsız kullanım için.

## Paketleri İçe Aktar

Başlamak için, C# projenize gerekli ad alanlarını içe aktarmanız gerekir. Bu, .NET için Aspose.PDF tarafından sağlanan sınıflara ve yöntemlere erişim için önemlidir.

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Şimdi, Aspose.PDF for .NET kullanarak bir PDF dosyasından vurgulanan metni çıkarma sürecini parçalara ayıralım. Her adım, temel kavramları ve uygulamayı anlamanıza yardımcı olmak için ayrıntılı olarak açıklanmıştır.

## Adım 1: Proje Dizininizi Ayarlayın

İlk önce, PDF dosyanızın bulunduğu proje dizinini ayarlamanız gerekir. Sihir burada gerçekleşir.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"`PDF dosyasının bulunduğu dizinin gerçek yolu ile. Bu dizin, uygulamanın işleme için PDF'yi getireceği yerdir.

## Adım 2: PDF Belgesini Yükleyin

 Sonra, vurgulanan metni çıkarmak istediğiniz PDF belgesini yüklemeniz gerekir. Bu, şu şekilde yapılır:`Document` Sınıf Aspose.PDF tarafından sağlanmıştır.

```csharp
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

 The`Document` sınıf, PDF dosyasının yoluyla örneklendirilir. Burada,`"ExtractHighlightedText.pdf"` vurgulanan metni içeren PDF dosyasının adıdır. Bu dosyanın belirtilen dizinde bulunduğundan emin olun.

## Adım 3: Açıklamalar Koleksiyonuna Erişim

PDF belgesi yüklendikten sonraki adım, belgenin ilk sayfasındaki açıklamalara erişmektir. Açıklamalar, PDF'lerde vurgulamalar, yorumlar ve daha fazlası gibi ek bilgiler eklemek için kullanılır.

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
```

 The`Annotations` mülkiyeti`Page` nesne, PDF'in belirli bir sayfasındaki tüm açıklamalara erişim sağlar. Burada, ilk sayfadaki her açıklama arasında döngü oluşturuyoruz.

## Adım 4: Vurgulanan Metin Açıklamaları için Filtre

Artık tüm açıklamalara erişebildiğimize göre, yalnızca vurgulanan metin açıklamalarını filtrelememiz gerekiyor. Bu, her açıklamanın türünü kontrol ederek gerçekleştirilir.

```csharp
if (annotation is TextMarkupAnnotation)
{
    TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
```

 The`TextMarkupAnnotation` sınıf, vurgulamalar da dahil olmak üzere metin işaretleme açıklamalarını temsil etmek için kullanılır.`is` anahtar kelime, açıklamanın türünde olup olmadığını kontrol eder`TextMarkupAnnotation` ve eğer öyleyse, açıklamayı şu şekilde yayınlar:`TextMarkupAnnotation`.

## Adım 5: Vurgulanan Metni Çıkarın

Vurgulanan açıklama belirlendikten sonraki adım, vurgulanan açıklamayla ilişkili metni çıkarmaktır.

```csharp
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
foreach (TextFragment tf in collection)
{
    Console.WriteLine(tf.Text);
}
```

 The`GetMarkedTextFragments()` yöntem bir koleksiyon döndürür`TextFragment` nesneler, her biri vurgulanan metnin bir bölümünü temsil eder. Bu koleksiyonda döngü yaparız ve her parçanın metnini konsola yazdırırız.

## Çözüm

Aspose.PDF for .NET kullanarak bir PDF'den vurgulanan metni çıkarmak, özellikle büyük belgelerle uğraşıyorsanız iş akışınızı kolaylaştırabilecek güçlü bir özelliktir. Bu eğitimde özetlenen adımları izleyerek, bu işlevi kendi projelerinizde kolayca uygulayabilirsiniz. Notlarınızı düzenliyor, raporlar hazırlıyor veya veri analizi yapıyor olun, bu yöntem vurgulanan metni çıkarmak ve kullanmak için kusursuz bir çözüm sunar.

## SSS

### Bu yöntemi kullanarak başka türde açıklamalar çıkarabilir miyim?  
 Evet, diğer türdeki açıklamaları değiştirerek çıkarabilirsiniz.`if` farklı açıklama türlerini kontrol etmek için koşul, örneğin`TextAnnotation`, `StampAnnotation`, vesaire.

### PDF'in tüm sayfalarından vurgulanan metni çıkarmak mümkün müdür?  
Kesinlikle! PDF belgesinin her sayfasında dolaşabilir ve her sayfadan vurgulanan metni toplamak için aynı çıkarma mantığını uygulayabilirsiniz.

### Aspose.PDF for .NET'i kullanmak için lisansa ihtiyacım var mı?  
 Ücretsiz denemeyle başlayabilmenize rağmen, bir tane edinmeniz önerilir[geçici lisans](https://purchase.aspose.com/temporary-license/)veya tüm özelliklere sınırsız erişim için tam lisans satın alın.

### Çıkarılan metni konsola yazdırmak yerine bir dosyaya kaydedebilir miyim?  
Evet, çıkarılan metni bir metin dosyasına veya istediğiniz başka bir biçime kaydetmek için kodu kolayca değiştirebilirsiniz.

### Aspose.PDF .NET dışında başka platformları da destekliyor mu?  
Evet, Aspose.PDF Java ve diğer platformları da destekler ve farklı ortamlarda benzer işlevler sunar.