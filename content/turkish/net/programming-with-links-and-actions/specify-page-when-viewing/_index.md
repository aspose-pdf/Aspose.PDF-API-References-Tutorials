---
title: Görüntülerken Sayfayı Belirle
linktitle: Görüntülerken Sayfayı Belirle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF'de görüntülenecek sayfayı nasıl belirleyeceğinizi öğrenin. Bu basit kılavuzla kullanıcı gezinmesini geliştirin.
type: docs
weight: 110
url: /tr/net/programming-with-links-and-actions/specify-page-when-viewing/
---
## giriiş

Kullanıcıları bir belgeyi açtıklarında belirli sayfalara yönlendirerek PDF uygulamalarınızı geliştirmek mi istiyorsunuz? Doğru yerdesiniz! Bu kılavuzda, bir PDF açıldığında görüntülenmesi gereken sayfayı belirtmek için Aspose.PDF for .NET'i kullanmanın inceliklerine dalacağız. Bu işlevsellik, özellikle belgenizin kritik bölümlerine dikkat çekmeniz gerektiğinde kullanıcı deneyimini önemli ölçüde iyileştirebilir.

## Ön koşullar

Kodlamaya dalmadan önce, başlamak için ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım. İhtiyacınız olanlar şunlardır:

1. .NET'in Temel Bilgisi: .NET framework'üne aşinalık şarttır. C# ile rahatsanız ve nesne yönelimli programlama hakkında temel bir anlayışa sahipseniz, hazırsınız!

2.  .NET için Aspose.PDF: Projenizde Aspose.PDF kütüphanesinin yüklü olması gerekir. Henüz yüklemediyseniz, indirebilirsiniz[Burada](https://releases.aspose.com/pdf/net/).

3. Visual Studio: Bu eğitim, IDE'niz olarak Visual Studio kullandığınızı varsayar. Bilgisayarınıza kurulu olduğundan emin olun.

4. PDF Dosyası: Üzerinde çalışacağınız mevcut bir PDF dosyasına ihtiyacınız olacak. Eğer yoksa, bir örnek belge oluşturabilir veya seçtiğiniz herhangi bir PDF'yi kullanabilirsiniz.

Tüm ön koşullar sağlandıktan sonra kolları sıvayıp kodlamaya başlayabiliriz!

## Paketleri İçe Aktar

Artık her şey ayarlandığına göre, gerekli paketleri projemize aktaralım. Şu adımları izleyin:

### Visual Studio'yu Başlat

Visual Studio'yu açın ve yeni bir proje oluşturun veya PDF sayfa görüntüleme işlevini uygulamak istediğiniz mevcut bir projeyi yükleyin.

### Referans Aspose.PDF

Aspose.PDF kütüphanesini kullanmak için, ona bir referans eklemeniz gerekir:

1. Çözüm Gezgini’nde projenizin üzerine sağ tıklayın.
2. 'NuGet Paketlerini Yönet' seçeneğini seçin.
3.  Arama`Aspose.PDF` ve paketi kurun.

### Ad Alanlarını İçe Aktar

Kod dosyanızın en üstüne aşağıdaki using yönergesini ekleyin:

```csharp
using System;
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

Artık PDF sayfa gezinme mantığınızı oluşturmaya başlamaya hazırsınız!

Görevimizi yönetilebilir adımlara bölelim. Bir PDF belgesi açan, görüntülendiğinde görüntülenecek belirli bir sayfayı belirten ve güncellenen belgeyi kaydeden bir kod yazacağız. 

## Adım 1: Belge Dizinini Ayarlayın

Öncelikle belgelerinizin yolunu ayarlamanız gerekiyor:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Dizininizle değiştirin
```

 Bu satır esasen yol haritanızdır. Kodunuza PDF dosyasını nerede bulacağını söylüyorsunuz. Değiştirdiğinizden emin olun`YOUR DOCUMENT DIRECTORY` makinenizdeki gerçek yol ile.

## Adım 2: PDF Dosyasını Yükleyin

Daha sonra PDF dosyasını uygulamanıza yükleyeceksiniz:

```csharp
// PDF dosyasını yükle
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

 Burada olan şey, yeni bir örnek oluşturmanızdır`Document`PDF dosyanızın yolunu belirtirken nesneyi seçin. Bunu, masaya koyduğunuz kitabı açmak gibi düşünebilirsiniz.

## Adım 3: İstenilen Sayfaya Erişim

Şimdi belge açıldığında görüntülenmesini istediğiniz sayfaya erişelim:

```csharp
// Belgenin ikinci sayfasının örneğini al
Page page2 = doc.Pages[2]; // Unutmayın, dizinleme 1'den başlar
```

Burada, belgenizin ikinci sayfasına erişiyoruz. Bu bağlamda sayfa numaralandırmasının 1'den başladığını belirtmekte fayda var, bu nedenle 2. sayfayı düşünüyorsanız, 2'lik bir dizin kullanmanız gerekir.

## Adım 4: Yakınlaştırma Faktörünü Ayarlayın

Görüntülenecek sayfanın yakınlaştırma seviyesini ayarlayabilirsiniz:

```csharp
// Hedef sayfanın yakınlaştırma faktörünü ayarlamak için değişkeni oluşturun
double zoom = 1; // 1, %100 yakınlaştırma anlamına gelir
```

Yakınlaştırma faktörü ayarlamak, kullanıcının sayfayı açar açmaz ne kadarını göreceğini belirlemeye yardımcı olur. 1 değeri, sayfanın %100 yakınlaştırmada görüntüleneceği anlamına gelir; bu genellikle iyi bir varsayılan değerdir.

## Adım 5: GoToAction Örneğini Oluşturun

Navigasyon özelliklerini harekete geçirelim:

```csharp
// GoToAction örneği oluştur
GoToAction action = new GoToAction(doc.Pages[2]); 
```

 Bu adımda, bir örnek oluşturuyorsunuz`GoToAction` Bu, esasen PDF'deki belirli bir noktaya (bu durumda ikinci sayfaya) gitme eylemini temsil eder.

## Adım 6: Hedefi Tanımlayın

Şimdi, eylemin nereye varacağını tanımlamanız gerekiyor:

```csharp
// 2. sayfaya git
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

Bu satır GoToAction için bir GPS hedefi ayarlamak gibidir. Sayfanın en üstünde (yükseklik) ve belirtilen yakınlaştırma seviyesinde 2. sayfaya gitmesini söylüyorsunuz.

## Adım 7: Açık Eylemi Ayarlayın

Belge açıldığında bu eylemin gerçekleştiğinden emin olalım:

```csharp
// Belge açma eylemini ayarla
doc.OpenAction = action;
```

Bununla, PDF'niz açıldığında, az önce tanımladığımız gezinme eyleminin etkinleştirildiğini beyan etmiş olursunuz. Bu, sanki belgenizin ön kapısına hoş geldiniz paspasını yerleştirmişsiniz gibi olur.

## Adım 8: Güncellenen Belgeyi Kaydedin

Son olarak yaptığımız değişikliklerle belgeyi kaydedelim:

```csharp
// Güncellenen belgeyi kaydet
doc.Save(dataDir + "goto2page_out.pdf");
```

Bu adım işinizi sonlandırır! Adında yeni bir PDF dosyanız olacak`goto2page_out.pdf` belirttiğiniz sayfaya doğrudan açılan.

Böylece kodlama kısmı tamamlanmış oldu! Aspose.PDF'yi bir PDF açıldığında belirli bir sayfayı gösterecek şekilde başarıyla programladınız. 

## Çözüm

Bu kılavuzda, .NET için Aspose.PDF kullanarak bir PDF dosyasında bir sayfanın nasıl belirleneceğini anlamak için adım adım bir yaklaşım benimsedik. Bu işlevsellik yalnızca kullanıcılarınız için gezinmeyi iyileştirmekle kalmaz, aynı zamanda belgelerinizdeki önemli içeriklerle etkileşimlerini de kolaylaştırır. Bu tür özellikleri benimseyerek, PDF uygulamalarınızı farklı kılabilecek daha kullanıcı dostu bir deneyim oluşturursunuz.

## SSS

### Aspose.PDF for .NET nedir?
Aspose.PDF for .NET, geliştiricilerin .NET uygulamaları içerisinde PDF belgeleri oluşturmalarına, değiştirmelerine ve yönetmelerine olanak tanıyan bir kütüphanedir.

### Birden fazla sayfanın görüntülenmesini belirleyebilir miyim?
Hayır, belgeyi yalnızca belirtilen bir sayfada açılacak şekilde ayarlayabilirsiniz. Ancak, farklı başlangıç sayfaları için farklı belgeler oluşturabilirsiniz.

### Ya bir sayfayı farklı bir yakınlaştırma düzeyinde görüntülemek istersem?
 Yakınlaştırma seviyesini ayarlayarak değiştirebilirsiniz.`zoom` Belgeyi kaydetmeden önce değişken.

### Aspose.PDF kullanımına dair daha fazla örneği nerede bulabilirim?
 Kontrol edebilirsiniz[belgeleme](https://reference.aspose.com/pdf/net/) Daha fazla örnek ve işlevsellik için.

### Aspose.PDF for .NET için ücretsiz deneme sürümü mevcut mu?
 Evet! Aspose.PDF'in ücretsiz deneme sürümünü indirebilirsiniz[Burada](https://releases.aspose.com/).