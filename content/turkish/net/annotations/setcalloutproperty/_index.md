---
title: PDF Dosyasında Çağrı Özelliğini Ayarla
linktitle: PDF Dosyasında Çağrı Özelliğini Ayarla
second_title: Aspose.PDF for .NET API Referansı
description: Bu ayrıntılı, adım adım eğitimde Aspose.PDF for .NET kullanarak bir PDF dosyasında callout özelliğinin nasıl ayarlanacağını öğrenin.
type: docs
weight: 130
url: /tr/net/annotations/setcalloutproperty/
---
## giriiş

Profesyonel ve görsel olarak çekici PDF belgeleri oluşturmak genellikle belirli içeriklere dikkat çeken açıklamaların eklenmesini gerektirir. Bu açıklamalardan biri de çizgi romanlarda gördüğünüz konuşma balonlarına benzeyen açıklamadır. PDF'nizdeki metni netleştirmeye veya vurgulamaya yardımcı olurlar. .NET için Aspose.PDF, belgelerinize bu tür açıklamalar eklemeyi inanılmaz derecede kolaylaştırır ve bu eğitimde, bu güçlü kütüphaneyi kullanarak bir PDF dosyasında açıklama özelliğinin nasıl ayarlanacağını ele alacağız. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu kılavuzun sonunda PDF dosyalarında açıklamaların nasıl kullanılacağına dair net bir anlayışa sahip olacaksınız.

## Ön koşullar

Koda dalmadan önce, başlamak için ihtiyacınız olan temel bilgileri ele alalım.

1.  Aspose.PDF for .NET: Aspose.PDF for .NET kütüphanesinin yüklü olduğundan emin olun. Buradan indirebilirsiniz[Burada](https://releases.aspose.com/pdf/net/).
2. IDE: Visual Studio benzeri bir geliştirme ortamı.
3. .NET Framework: Bilgisayarınızda .NET'in yüklü olduğundan emin olun.
4. Geçici Lisans: Aspose.PDF'nin tüm özelliklerini sınırlama olmaksızın denemek istiyorsanız, bir tane edinin[geçici lisans](https://purchase.aspose.com/temporary-license/).

## Paketleri İçe Aktar

Kod yazmaya başlamadan önce, PDF dosyaları ve açıklamalarla çalışmanıza olanak sağlayacak gerekli paketleri içe aktarmanız gerekir.

```csharp
using Aspose.Pdf.Annotations;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Bu içe aktarımlar, PDF belgelerini düzenlemek ve açıklama metni gibi ek açıklamalar oluşturmak için gerekli tüm sınıfları ve yöntemleri size sağlayacaktır.

## Adım 1: PDF Belgesini Başlatın

Yolculuğumuzun ilk adımı, açıklama notumuzu ekleyeceğimiz yeni bir PDF belgesi başlatmaktır. Bunu, öğeler eklemeye başlayabileceğiniz boş bir tuval oluşturmak olarak düşünün.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Yeni bir PDF belgesi başlatın
Document doc = new Document();
```
 Burada yeni bir şey yaratıyoruz`Document` PDF dosyamız olarak hizmet edecek nesne.`dataDir` değişkeni, işimiz bittikten sonra PDF dosyanızı kaydetmek istediğiniz dizine ayarlanır.

## Adım 2: Belgeye Yeni Bir Sayfa Ekleyin

Bir PDF belgesi birden fazla sayfaya sahip olabilir ve bu adımda belgemize yeni bir sayfa ekleyeceğiz. Bu sayfa, açıklama notumuzun yerleştirileceği yer olacaktır.

```csharp
//Belgeye yeni bir sayfa ekle
Page page = doc.Pages.Add();
```
 The`Pages.Add()`yeni bir sayfa eklemek için kullanılan yöntem`doc` nesne. Yeni sayfa şurada saklanır:`page` Daha sonra açıklama eklerken kullanacağımız değişken.

## Adım 3: Varsayılan Görünümü Tanımlayın

Açıklamalar, açıklama metni gibi, özelleştirebileceğiniz görsel bir görünüme sahiptir. Bu adımda, açıklama metninin nasıl görünmesi gerektiğini tanımlayacağız.

```csharp
// Açıklama için varsayılan görünümü tanımlayın
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```
 Biz bir tane yaratıyoruz`DefaultAppearance` metin rengini ve yazı tipi boyutunu tanımlayan nesne. Burada, metin kırmızı olacak ve yazı tipi boyutu 10 olarak ayarlanacak. Bu görünüm, açıklama açıklamasına uygulanacaktır.

## Adım 4: Serbest Metin Açıklamasını Oluşturun

Şimdi gerçek açıklamayı oluşturma zamanı. Serbest metin açıklaması, belirli metin ve stile sahip bir açıklama eklememize olanak tanır.

```csharp
// Bir çağrı ile FreeTextAnnotation oluşturun
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
```
 Biz bir tane yaratıyoruz`FreeTextAnnotation` sayfadaki konumunu tanımlayan belirli koordinatlara sahip nesne.`Intent` ayarlandı`FreeTextCallout` , bunun bir açıklama açıklaması olduğunu belirtir.`EndingStyle` ayarlandı`OpenArrow`açıklama satırının açık bir okla sonlanacağı anlamına gelir.

## Adım 5: Çağrı Çizgisi Noktalarını Tanımlayın

Bir açıklama notu, ilgi alanına işaret eden bir çizgiye sahiptir. Burada, bu çizgiyi oluşturan noktaları tanımlayacağız.

```csharp
// Çağrı satırı için noktaları tanımlayın
fta.Callout = new Point[]
{
    new Point(428.25, 651.75), 
    new Point(462.75, 681.375), 
    new Point(474, 681.375)
};
```
 The`Callout` mülk bir dizidir`Point` nesneler, her biri sayfadaki bir koordinatı temsil eder. Bu noktalar, çağrı satırının yolunu tanımlar ve ona klasik konuşma balonu görünümünü verir.

## Adım 6: Sayfaya Açıklama Ekleyin

Açıklamamızı oluşturup yapılandırdıktan sonraki adım, açıklamamızı sayfaya eklemektir.

```csharp
// Sayfaya açıklama ekle
page.Annotations.Add(fta);
```
 The`Annotations.Add()` yöntemi, daha önce oluşturduğumuz sayfaya açıklamayı yerleştirmek için kullanılır. Bu adım, açıklamayı PDF sayfasına etkili bir şekilde "çizer".

## Adım 7: Zengin Metin İçeriğini Ayarlayın

Açıklama açıklamaları zengin metin içerebilir ve balon içinde biçimlendirilmiş içeriklere olanak tanır. Biraz örnek metin ekleyelim.

```csharp
// Açıklama için zengin metni ayarlayın
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"><span style=\"font-size:9.0pt;font-family:Helvetica\">Bu bir örnektir</span></p></body>";
```
 The`RichText` özellik HTML içeriğiyle ayarlanır. Bu, yazı tipi boyutu, rengi ve stili gibi açıklama içinde ayrıntılı biçimlendirmeye olanak tanır.

## Adım 8: PDF Belgesini Kaydedin

Son olarak, her şeyi ayarladıktan sonra belgeyi kaydetmemiz gerekiyor. Bu adım, açıklama notuyla PDF'nin oluşturulmasını sonlandırır.

```csharp
// Belgeyi kaydet
doc.Save(dataDir + "SetCalloutProperty.pdf");
```
 The`Save()` method belgeyi belirtilen dizine "SetCalloutProperty.pdf" dosya adıyla kaydeder. Bu adım PDF oluşturma sürecimizi sonlandırır.

## Çözüm

İşte karşınızda! .NET için Aspose.PDF kullanarak bir açıklama notuyla bir PDF belgesi oluşturdunuz. Bu açıklama, belgenizin belirli bölümlerini vurgulamak veya açıklamak için inanılmaz derecede yararlı olabilir. Aspose.PDF, PDF düzenlemeyi basit ve esnek hale getiren güçlü bir API sunar. Açıklamalar ekliyor, belgeleri dönüştürüyor veya karmaşık PDF görevlerini yönetiyor olun, Aspose.PDF sizin için her şeyi yapar.

## SSS

### Açıklama metninin görünümünü daha fazla özelleştirebilir miyim?

Kesinlikle! Çizgi rengi, kalınlık ve metnin yazı tipi ailesi ve stili gibi çeşitli yönleri özelleştirebilirsiniz.

### Tek bir sayfaya birden fazla açıklama eklemek mümkün müdür?

Evet, her açıklama için adımları tekrarlayarak ihtiyacınız olduğu kadar açıklama ekleyebilirsiniz.

### Açıklamanın konumunu nasıl değiştirebilirim?

 Sadece koordinatları değiştirin`Rectangle` Ve`Callout` Açıklamayı yeniden konumlandırmak için özellikler.

### Aspose.PDF'i kullanarak başka türde açıklamalar ekleyebilir miyim?

Evet, Aspose.PDF vurgulamalar, damgalar ve dosya ekleri dahil olmak üzere çeşitli açıklama türlerini destekler.

### Zengin metin içeriği HTML ile mi sınırlı?

 The`RichText` özellik, biçimlendirilmiş metin ve temel biçimlendirme eklemenize olanak tanıyan HTML'nin bir alt kümesini destekler.