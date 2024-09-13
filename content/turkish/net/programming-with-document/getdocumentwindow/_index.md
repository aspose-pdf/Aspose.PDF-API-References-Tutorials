---
title: Belge Al Penceresi
linktitle: Belge Al Penceresi
second_title: Aspose.PDF for .NET API Referansı
description: .NET için Aspose.PDF'nin GetDocumentWindow özelliğinin bir PDF belgesinin pencere özellikleri hakkında bilgi almak için nasıl kullanılacağını öğrenin.
type: docs
weight: 170
url: /tr/net/programming-with-document/getdocumentwindow/
---
# giriiş

PDF'lerle mi çalışıyorsunuz ve açıldığında nasıl göründükleri üzerinde daha fazla kontrole mi ihtiyacınız var? İster menü çubuğunu gizlemek ister pencereyi ilk sayfaya uyacak şekilde yeniden boyutlandırmak olsun, Aspose.PDF for .NET, bir PDF'nin bir görüntüleyicide açıldığında nasıl davranacağını özelleştirmek için ihtiyacınız olan tüm araçları sunar. Bu eğitimde, Aspose.PDF for .NET'te belge penceresi ayarlarının nasıl alınacağını ve değiştirileceğini açıklayacağız.


# Ön koşullar

Eğitime başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

- Geliştirme ortamınıza .NET için Aspose.PDF yüklendi.
  - [.NET için Aspose.PDF'yi indirin](https://releases.aspose.com/pdf/net/)
-  Aspose.PDF için geçerli bir lisans veya bir tane alabilirsiniz[ücretsiz deneme](https://releases.aspose.com/) veya[geçici lisans](https://purchase.aspose.com/temporary-license/).
- .NET ve C# hakkında temel bilgi.
- Visual Studio veya başka uygun bir IDE.

# Paketleri İçe Aktar

Herhangi bir kod yazmaya başlamadan önce, gerekli paketleri içe aktarmanız gerekir. Projenizi açın ve C# dosyanızın en üstüne aşağıdaki ad alanını ekleyin:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Bu, Aspose.PDF for .NET kullanarak PDF belgelerini düzenlemek için gereken tüm sınıflara ve yöntemlere erişmenizi sağlayacaktır.

 Şimdi farklı belge penceresi ayarlarını alma sürecini parçalara ayıralım. Bu örnek için, adlı bir örnek PDF dosyası kullanacağız.`GetDocumentWindow.pdf`.

## Adım 1: Belge Dizin Yolunu Ayarlayın

İlk önce, PDF dosyamızın yolunu tanımlamamız gerekiyor. Yürütme sırasında herhangi bir hatadan kaçınmak için doğru dosya yoluna sahip olmanız çok önemlidir.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Burada, değiştirin`"YOUR DOCUMENT DIRECTORY"` PDF dosyanızın bulunduğu gerçek dizinle. Bu, PDF belgenizi yükleyeceğiniz çalışma dizininizdir.

## Adım 2: PDF Belgesini açın

Artık dosya yolu ayarlandığına göre, bir sonraki adım PDF belgesini Aspose.PDF kullanarak açmaktır. Bu, belgeyi belleğe yükleyecek ve özelliklerini almanıza olanak tanıyacaktır.

```csharp
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

Bu basit kod satırıyla PDF dosyanızı başarıyla yüklediniz.`pdfDocument` Artık tüm özelliklerine erişmenizi sağlayacak nesne.

## Adım 3: Pencere Orta Durumunu Alın

 Sonra, belge penceresinin açıldığında ortalanıp ortalanmayacağını kontrol edelim. Bunun için varsayılan değer şudur:`false`.

```csharp
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
```

 Çıktı ise`true`, belgenin penceresi ekranın ortasında açılacaktır. Aksi takdirde, varsayılan konumunda açılacaktır.

## Adım 4: Metin Yönünü Kontrol Edin

Bir PDF'nin görünümünün bir diğer önemli yönü, metnin soldan sağa (L2R) mı yoksa sağdan sola (R2L) mı okunacağını belirleyen metin yönüdür. Bu bilgiyi aşağıdaki kodu kullanarak alabilirsiniz:

```csharp
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
```

 Çıktı şu şekilde olacaktır:`L2R` soldan sağa metin için ve`R2L` sağdan sola metin için. Bu ayar özellikle Arapça veya İbranice gibi dillerdeki belgeler için kullanışlıdır.

## Adım 5: Belge Başlığını Pencerede Görüntüle

Sonraki özellik, belge başlığının mı yoksa dosya adının mı pencerenin başlık çubuğunda gösterileceğini kontrol etmenizi sağlar. Varsayılan olarak bu,`false`, dosya adının gösterileceği anlamına gelir.

```csharp
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
```

Dosya adı yerine belgenin başlığının görüntülenmesini istiyorsanız bu ayarın etkinleştirilmesi gerekir.

## Adım 6: Pencereyi İlk Sayfaya Sığacak Şekilde Yeniden Boyutlandırın

Bazen, açıldığında belge penceresinin PDF'nin ilk sayfasına uyacak şekilde otomatik olarak yeniden boyutlandırılmasını isteyebilirsiniz. Bu özelliğin etkin olup olmadığını kontrol etmenin yolu:

```csharp
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
```

 Varsayılan olarak bu şu şekilde ayarlanır:`false`Bu, ilk sayfanın boyutundan bağımsız olarak pencere boyutunun aynı kalacağı anlamına gelir.

## Adım 7: Menü Çubuğunu Gizle

Daha odaklı bir okuma deneyimi için, görüntüleyici uygulamasının menü çubuğunu gizlemek isteyebilirsiniz. Bu ayarı aşağıdaki satırı kullanarak alabilirsiniz:

```csharp
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
```

 Bu geri dönecek`true` menü çubuğu gizliyse ve`false` aksi takdirde.

## Adım 8: Araç Çubuğunu Gizle

Benzer şekilde, daha temiz bir kullanıcı arayüzü için PDF görüntüleyicisindeki araç çubuğunu gizlemek isteyebilirsiniz. Bu ayar aşağıdaki şekilde alınabilir:

```csharp
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
```

Bu ayar etkinleştirildiğinde PDF açıldığında araç çubuğu gizlenecektir.

## Adım 9: Kaydırma Çubuklarını ve Kullanıcı Arayüzü Öğelerini Gizle

Kaydırma çubukları gibi ek kullanıcı arayüzü öğeleri olmadan yalnızca sayfa içeriğini görüntülemek istiyorsanız, bu ayar bu davranışı kontrol eder:

```csharp
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
```

 Ayarlandığında`true`, PDF görüntüleyici kaydırma çubuklarını ve diğer kullanıcı arayüzü öğelerini gizleyecek ve yalnızca belge içeriğini bırakacaktır.

## Adım 10: Tam Ekran Olmayan Sayfa Modunu Ayarlayın

 Tam ekran modundan çıktığınızda belgenin nasıl görüneceğini kontrol etmek için`NonFullScreenPageMode` özellik. Bu ayar, kullanıcının tam ekran olmayan modda belgeyle nasıl etkileşime girmesi gerektiğini tanımlamak için yararlıdır.

```csharp
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
```

Çıktı, küçük resimler, ana hatlar veya ekler paneli gibi farklı modlara ayarlanabilir.

## Adım 11: Sayfa Düzenini Tanımlayın

Bu ayar, belge sayfalarının nasıl düzenleneceğini kontrol etmenizi sağlar. Örneğin, tek sayfa görünümü veya sürekli sütun görünümü seçebilirsiniz:

```csharp
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
```

Bu, kullanıcılara belge içeriğini nasıl okuyacakları veya görüntüleyecekleri konusunda esneklik sağlar.

## Adım 12: Sayfa Modunu Belirleyin

 Son olarak,`PageMode` özellik, belgenin açıldığında nasıl görüntüleneceğini tanımlar. Seçenekler arasında küçük resimlerin gösterilmesi, tam ekran moduna girilmesi veya ekler panelinin görüntülenmesi yer alır.

```csharp
Console.WriteLine("PageMode : {0}", pdfDocument.PageMode);
```

İhtiyaçlarınıza bağlı olarak bunu PDF'inizin amacına uygun herhangi bir moda ayarlayabilirsiniz.

## Çözüm

Gördüğünüz gibi, Aspose.PDF for .NET, PDF belgelerinizin çeşitli PDF görüntüleyicilerinde nasıl görüntüleneceğini düzenlemek için kapsamlı araçlar sunar. Araç çubuğunu gizlemek, pencereyi ortalamak veya metin yönünü kontrol etmek istiyorsanız, Aspose.PDF kullanıcının görüntüleme deneyimini geliştirmek için esneklik sunar.

# SSS

### PDF'in başlangıçtaki yakınlaştırma seviyesini özelleştirebilir miyim?
Evet, Aspose.PDF belge açıldığında yakınlaştırma seviyesini ayarlamanıza olanak tanır.

### PDF'in pencere boyutunu nasıl kilitleyebilirim?
 Ayarlayabilirsiniz`FitWindow` Pencerenin yeniden boyutlandırılmasını engelleyen özellik.

### Aspose.PDF farklı okuma modlarını destekliyor mu?
Evet, tam ekran, küçük resim ve ekler gibi farklı modları destekliyor.

### PDF görüntüleyicide kaydırma çubuklarını gizlemek mümkün mü?
 Kesinlikle, kaydırma çubuklarını ayarlayarak gizleyebilirsiniz.`HideWindowUI` mülk`true`.

### Belge penceresini açtığımda ortalayabilir miyim?
 Evet, bunu şu şekilde ayarlayarak kontrol edebilirsiniz:`CenterWindow` mülk.