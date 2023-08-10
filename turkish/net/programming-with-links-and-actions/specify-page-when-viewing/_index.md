---
title: Görüntülerken Sayfayı Belirtin
linktitle: Görüntülerken Sayfayı Belirtin
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF görüntülerken sayfa belirtmeyi öğrenin.
type: docs
weight: 110
url: /tr/net/programming-with-links-and-actions/specify-page-when-viewing/
---
Bu adım adım kılavuz ile Aspose.PDF for .NET kullanarak bir PDF dosyasını görüntülerken bir sayfayı nasıl belirteceğinizi öğrenin.

## 1. Adım: Ortamı ayarlama

Geliştirme ortamınızı bir C# projesi ve uygun Aspose.PDF referansları ile kurduğunuzdan emin olun.

## 2. Adım: PDF dosyasını yükleme

Belgelerinizin dizin yolunu ayarlayın ve aşağıdaki kodu kullanarak PDF dosyasını yükleyin:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// PDF dosyasını yükleyin
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## 3. Adım: Hedef sayfayı belirleme

Aşağıdaki kodu kullanarak hedef sayfa örneğini alın:

```csharp
Page page2 = doc.Pages[2];
```

 İndeksi ayarlayabilirsiniz`[2]` istediğiniz sayfayı seçmek için

## 4. Adım: Yakınlaştırma ayarını yapılandırma

Hedef sayfa yakınlaştırma faktörünü ayarlamak için bir değişken oluşturun:

```csharp
double zoom = 1;
```

Zum değerini ihtiyaçlarınıza göre ayarlayabilirsiniz.

## 5. Adım: Gezinme eylemini oluşturun

Belirtilen hedef sayfayı kullanarak gezinme eyleminin bir örneğini oluşturun:

```csharp
GoToAction action = new GoToAction(doc.Pages[2]);
```

## 6. Adım: Hedefin ayarlanması

Koordinatları ve yakınlaştırmayı kullanarak hedef sayfaya gitmek için hedefi ayarlayın:

```csharp
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

## 7. Adım: Belge Açma İşlemini Yapılandırma

Oluşturulan gezinme eylemiyle belge açma eylemini ayarlayın:

```csharp
doc. OpenAction = action;
```

## 8. Adım: Güncellenen belgeyi kaydedin

 kullanarak güncellenen belgeyi kaydedin.`Save` yöntem:

```csharp
doc.Save(dataDir + "goto2page_out.pdf");
```

### Aspose.PDF for .NET kullanarak Görüntülerken Sayfayı Belirt için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// PDF dosyasını yükleyin
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
// Belgenin ikinci sayfasının örneğini alın
Page page2 = doc.Pages[2];
// Hedef sayfanın yakınlaştırma faktörünü ayarlamak için değişkeni oluşturun
double zoom = 1;
// GoToAction örneği oluştur
GoToAction action = new GoToAction(doc.Pages[2]);
// 2 sayfaya git
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
// Belge açma eylemini ayarla
doc.OpenAction = action;
// Güncellenen belgeyi kaydet
doc.Save(dataDir + "goto2page_out.pdf");
```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF görüntülerken bir sayfayı nasıl belirteceğinizi biliyorsunuz. PDF belgelerinizdeki kullanıcı görüntüleme deneyimini özelleştirmek için bu bilgiyi kullanın.

Artık bu kılavuzu tamamladığınıza göre, bu kavramları kendi projelerinize uygulayabilir ve Aspose.PDF for .NET tarafından sunulan özellikleri daha fazla keşfedebilirsiniz.

### SSS 

#### S: Bir PDF dosyasını görüntülerken bir hedef sayfa belirtmenin amacı nedir?

C: Bir hedef sayfa belirlemek, dosya açıldığında bir PDF belgesinin hangi sayfasının görüntüleneceğini kontrol etmenizi sağlar. Bu, kullanıcı deneyimini ilgilenilen belirli bir sayfaya yönlendirerek geliştirebilir.

#### S: PDF belgelerinde bir hedef sayfa belirlemek nasıl yararlı olabilir?

Y: Kullanıcıları, sayfalar arasında manuel olarak gezinmelerini gerektirmeden bir PDF belgesindeki belirli bir bölüme veya içeriğe yönlendirmek istediğinizde, bir hedef sayfa belirlemek faydalıdır.

#### S: Aspose.PDF for .NET, görüntüleme için bir hedef sayfa belirlemeyi nasıl kolaylaştırır?

Y: Aspose.PDF for .NET, hedef sayfa, yakınlaştırma düzeyi ve diğer görüntüleme özellikleri dahil olmak üzere bir PDF belgesinin ilk görünümünü ayarlamanıza izin veren API'ler sağlar.

#### S: Herhangi bir sayfayı hedef sayfa olarak belirtebilir miyim?

C: Evet, PDF belgesindeki herhangi bir sayfayı görüntülemek için hedef sayfa olarak belirleyebilirsiniz. İstediğiniz sayfayı seçmek için uygun dizini kullanmanız yeterlidir.

#### S: Bir hedef sayfa belirtirken yakınlaştırma faktörünün önemi nedir?

Y: Yakınlaştırma faktörü, PDF belgesi açıldığında hedef sayfaya uygulanan büyütme düzeyini belirler. Görünüm alanında ne kadar içeriğin görüntüleneceğini kontrol eder.

#### S: Farklı hedef sayfalar için farklı yakınlaştırma faktörleri ayarlayabilir miyim?

C: Evet, ayrı sayfalar oluşturarak farklı hedef sayfalar için farklı yakınlaştırma faktörleri ayarlayabilirsiniz.`GoToAction` örnekleri ve hedeflerini buna göre yapılandırma.

#### S: Bir hedef sayfa belirtmek için herhangi bir sınırlama var mı?

Y: Bir hedef sayfa belirlemek, PDF açıldığında ilk görünümü kontrol etmekle sınırlıdır. PDF görüntülendikten sonra kullanıcı etkileşimlerini veya gezinmeyi etkilemez.

#### S: Bu özelliği bir PDF belgesi içinde sunumlar oluşturmak için kullanabilir miyim?

C: Evet, bu özelliği bir PDF belgesinde sunuma benzer deneyimler oluşturmak için kullanabilir, kullanıcılara farklı bölümler veya konularda rehberlik edebilirsiniz.

#### S: Sayfa düzeni gibi ilk görünümün diğer özelliklerini özelleştirebilir miyim?

C: Evet, Aspose.PDF for .NET, sayfa düzeni, sayfa modu ve daha fazlası dahil olmak üzere ilk görünümün diğer yönlerini özelleştirmek için özellikler sağlar.

#### S: Belirtilen hedef sayfanın ve yakınlaştırma faktörünün amaçlandığı gibi çalışıp çalışmadığını nasıl test edebilirim?

Y: Hedef sayfayı ve yakınlaştırma faktörünü belirtmek için sağlanan kodu uyguladıktan sonra, değiştirilen PDF dosyasını açın ve doğru sayfa ve yakınlaştırma düzeyiyle açıldığını doğrulayın.