---
title: Etiketli Metinle PDF Oluştur
linktitle: Etiketli Metinle PDF Oluştur
second_title: Aspose.PDF for .NET API Referansı
description: Bu kapsamlı adım adım eğitimde, Aspose.PDF for .NET kullanarak erişilebilir içeriklere sahip etiketli PDF'lerin nasıl oluşturulacağını öğrenin.
type: docs
weight: 50
url: /tr/net/programming-with-tagged-pdf/create-pdf-with-tagged-text/
---
## giriiş

Günümüzün dijital çağında, PDF belgeleri içerik paylaşmak ve görüntülemek için en popüler biçimlerden biri haline geldi. İster iş raporları, ister akademik makaleler veya kullanıcı kılavuzları olsun, PDF'ler her yerde! Ancak iyi bir PDF'yi harika bir PDF'den ayıran şey erişilebilirlik ve yapıdır. Doğru duydunuz! Etiketli PDF'ler, ekran okuyucuların ve yardımcı teknolojilerin içeriği anlamasını ve içinde gezinmesini kolaylaştırır. Ve tahmin edin ne oldu? Bu eğitimde, Aspose.PDF for .NET kullanarak etiketli bir PDF oluşturma sürecini adım adım anlatacağım! 

O halde en sevdiğiniz içeceğinizi alın, yerleşin ve etiketli PDF'lerin dünyasına dalalım!

## Ön koşullar

Başlamadan önce, yerinde olması gereken birkaç şey var:

1. Visual Studio - Makinenizde Visual Studio'nun yüklü olduğundan emin olun. .NET'i destekleyen herhangi bir sürümü kullanabilirsiniz.
2.  Aspose.PDF for .NET - Aspose.PDF for .NET'in en son sürümünü şu adresten indirin:[web sitesi](https://releases.aspose.com/pdf/net/)Ayrıca özelliklerini keşfetmek için ücretsiz deneme seçeneğini de tercih edebilirsiniz.
3. .NET Framework - Bu örnekler .NET için oluşturulacaktır. Makinenizde uyumlu bir sürümün yüklü olduğundan emin olun.
4. Temel C# Bilgisi - C# programlamaya aşinalık, kod yazarken işimize yarayacak!

Her şeyi aldınız mı? Harika! Kodlamaya başlayalım!

## Paketleri İçe Aktar

Artık ön koşullarımızı hallettiğimize göre, eğlenceli kısma geçelim: gerekli paketleri içe aktarmak. Aspose.PDF ile çalışmak için, kütüphaneyi projenize kesinlikle eklemeniz gerekir. 

### Yeni Bir Proje Oluştur

Öncelikle Visual Studio'yu başlatıp yeni bir C# projesi oluşturalım.

1. Visual Studio’yu açın.
2. "Yeni Proje Oluştur"a tıklayın.
3. "Konsol Uygulaması (.NET)" seçeneğini seçin ve "İleri"ye tıklayın.
4.  Projenize bir isim verin (örneğin,`TaggedPdfExample`) ve konumunu ayarlayın.
5. "Oluştur"a tıklayın.

### Aspose.PDF Referansını Ekle

Şimdi Aspose.PDF kütüphanesini ekleyelim:

1. Çözüm Gezgini’nde projenizin üzerine sağ tıklayın.
2. "NuGet Paketlerini Yönet" seçeneğini seçin.
3. "Aspose.PDF" dosyasını arayın ve en son sürümü yükleyin.

### Gerekli Ad Alanlarını İçe Aktar

 Ana program dosyanızın en üstünde (örneğin`Program.cs`), aşağıdaki ad alanlarını içe aktarın:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Artık her şeyi ayarladığımıza göre, kodu sindirilebilir parçalara bölelim ve adım adım etiketli bir PDF oluşturalım!

## Adım 1: Belge Dizinini Tanımlayın

Kodlamaya başlamadan önce PDF dosyamızı kaydedeceğimiz belge dizinini tanımlayalım:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Bunu yolunuza güncelleyin
```

 Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` PDF'nizi kaydetmek istediğiniz gerçek yol ile.

## Adım 2: Bir PDF Belgesi Oluşturun

Yeni bir PDF belge örneği oluşturalım. Bu, içeriğimizi ekleyeceğimiz boş bir tuval çizmek gibidir. 

```csharp
// PDF Belgesi Oluştur
Document document = new Document();
```

## Adım 3: Belge için Etiketli İçeriği Alın

Sonra, belgemizin etiketli içeriğini almamız gerekiyor. Etiketli içeriği, onu erişilebilir kılan temel yapı olarak düşünün. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
// TaggedPdf ile çalışmak için İçerik Alın
ITaggedContent taggedContent = document.TaggedContent;
```

## Adım 4: Belge için Başlık ve Dil Belirleyin

Şimdi, belgemizin başlığını ve dilini ayarlayalım. Bu erişilebilirlik için çok önemli!

```csharp
// Belge için Başlık ve Dil Ayarla
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
```

## Adım 5: Metin Bloğu Düzeyinde Yapı Elemanları Oluşturun

İçeriğimizi burada oluşturacağız. Başlıklar ve paragraflar yapacağız, tıpkı yapı taşları gibi!

### Adım 5.1: Bir Başlık Öğesi Oluşturun

Başlamak için bir başlık öğesi oluşturalım:

```csharp
// Metin Bloğu Düzeyinde Yapı Elemanları Oluşturun
HeaderElement headerElement = taggedContent.CreateHeaderElement();
headerElement.ActualText = "Heading 1";
```

### Adım 5.2: Paragraf Öğelerini Oluşturun

Sonra birkaç paragraf ekleyelim. Ben sizin için birkaç tane ekleyeceğim ama siz bunu ihtiyaçlarınıza göre özelleştirebilirsiniz!

```csharp
ParagraphElement paragraphElement1 = taggedContent.CreateParagraphElement();
paragraphElement1.ActualText = "test1";

ParagraphElement paragraphElement2 = taggedContent.CreateParagraphElement();
paragraphElement2.ActualText = "test 2";

ParagraphElement paragraphElement3 = taggedContent.CreateParagraphElement();
paragraphElement3.ActualText = "test 3";

ParagraphElement paragraphElement4 = taggedContent.CreateParagraphElement();
paragraphElement4.ActualText = "test 4";

ParagraphElement paragraphElement5 = taggedContent.CreateParagraphElement();
paragraphElement5.ActualText = "test 5";

ParagraphElement paragraphElement6 = taggedContent.CreateParagraphElement();
paragraphElement6.ActualText = "test 6";

ParagraphElement paragraphElement7 = taggedContent.CreateParagraphElement();
paragraphElement7.ActualText = "test 7";
```

## Adım 6: PDF Belgesini Kaydedin

Son olarak, bu şaheseri kaydedelim! Etiketli PDF'inizi şu şekilde kaydedebilirsiniz:

```csharp
// PDF Belgesini Kaydet
document.Save(dataDir + "PDFwithTaggedText.pdf");
```

Etiketli bir PDF oluşturdunuz! 

## Çözüm

Aspose.PDF for .NET ile etiketli bir PDF oluşturmak, bir kez alıştığınızda çocuk oyuncağıdır! Belgelerinizi yalnızca kullanıcı dostu değil, aynı zamanda daha geniş bir kitleye erişilebilir hale getirir. Özellikle içerik erişilebilirliğinin önemli olduğu sektörlerdeyseniz, anlamsal yapıyı vurgulamak kesinlikle işe yarayacaktır. 

## SSS

### Etiketli PDF nedir?  
Etiketli PDF, ekran okuyucuların ve yardımcı teknolojilerin içerikte etkili bir şekilde gezinmesini kolaylaştıran yapılandırılmış veriler içerir.

### Aspose.PDF'i kullanmak için satın almam gerekiyor mu?  
 Ücretsiz denemeyle başlayabilmenize rağmen, uzun süreli kullanım için bir lisans gerekecektir. Daha fazla bilgi edinebilirsiniz[Burada](https://purchase.aspose.com/buy).

### PDF'imdeki yapı elemanlarını özelleştirebilir miyim?  
Kesinlikle! Çeşitli unsurları manipüle edebilir ve gereksinimlerinize göre karmaşık yapılar oluşturabilirsiniz.

### Aspose.PDF tüm .NET uygulamalarıyla uyumlu mudur?  
Evet, Aspose.PDF .NET Framework, .NET Core ve daha fazlası dahil olmak üzere çeşitli .NET platformlarında çalışacak şekilde tasarlanmıştır.

### Aspose.PDF için desteği nerede bulabilirim?  
 Ziyaret edebilirsiniz[Aspose Destek Forumu](https://forum.aspose.com/c/pdf/10) Herhangi bir sorunuz veya karşılaştığınız sorun için.