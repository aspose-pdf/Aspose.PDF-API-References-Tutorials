---
title: Görüntülerken Sayfayı Belirle
linktitle: Görüntülerken Sayfayı Belirle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF'i görüntülerken bir sayfanın nasıl belirleneceğini öğrenin.
type: docs
weight: 110
url: /tr/net/programming-with-links-and-actions/specify-page-when-viewing/
---
Bu adım adım kılavuzla Aspose.PDF for .NET kullanarak bir PDF dosyasını görüntülerken bir sayfanın nasıl belirleneceğini öğrenin.

## Adım 1: Ortamı kurma

Geliştirme ortamınızı bir C# projesi ve uygun Aspose.PDF referanslarıyla kurduğunuzdan emin olun.

## Adım 2: PDF dosyasını yükleme

Belgelerinizin dizin yolunu ayarlayın ve aşağıdaki kodu kullanarak PDF dosyasını yükleyin:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// PDF dosyasını yükle
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## Adım 3: Hedef sayfanın belirtilmesi

Aşağıdaki kodu kullanarak hedef sayfa örneğini alın:

```csharp
Page page2 = doc.Pages[2];
```

 İndeksi ayarlayabilirsiniz`[2]` İstediğiniz sayfayı seçmek için.

## Adım 4: Yakınlaştırma ayarını yapılandırma

Hedef sayfa yakınlaştırma faktörünü ayarlamak için bir değişken oluşturun:

```csharp
double zoom = 1;
```

Yakınlaştırma değerini ihtiyacınıza göre ayarlayabilirsiniz.

## Adım 5: Gezinme eylemini oluşturun

Belirtilen hedef sayfayı kullanarak gezinme eyleminin bir örneğini oluşturun:

```csharp
GoToAction action = new GoToAction(doc.Pages[2]);
```

## Adım 6: Hedefi ayarlama

Koordinatları ve yakınlaştırmayı kullanarak hedef sayfaya gitmek için hedefi ayarlayın:

```csharp
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

## Adım 7: Belge Açma Eylemini Yapılandırma

Oluşturulan gezinme eylemiyle belge açma eylemini ayarlayın:

```csharp
doc. OpenAction = action;
```

## Adım 8: Güncellenen belgeyi kaydedin

 Güncellenen belgeyi kullanarak kaydedin`Save` yöntem:

```csharp
doc.Save(dataDir + "goto2page_out.pdf");
```

### .NET için Aspose.PDF kullanarak Sayfayı Görüntülerken Belirle için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// PDF dosyasını yükle
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
// Belgenin ikinci sayfasının örneğini al
Page page2 = doc.Pages[2];
// Hedef sayfanın yakınlaştırma faktörünü ayarlamak için değişkeni oluşturun
double zoom = 1;
// GoToAction örneği oluştur
GoToAction action = new GoToAction(doc.Pages[2]);
// 2. sayfaya git
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
// Belge açma eylemini ayarla
doc.OpenAction = action;
// Güncellenen belgeyi kaydet
doc.Save(dataDir + "goto2page_out.pdf");
```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF'i görüntülerken bir sayfayı nasıl belirleyeceğinizi biliyorsunuz. Bu bilgiyi kullanarak PDF belgelerinizdeki kullanıcı görüntüleme deneyimini özelleştirin.

Artık bu kılavuzu tamamladığınıza göre, bu kavramları kendi projelerinize uygulayabilir ve Aspose.PDF for .NET tarafından sunulan özellikleri daha ayrıntılı olarak inceleyebilirsiniz.

### SSS 

#### S: Bir PDF dosyasını görüntülerken hedef sayfa belirtmenin amacı nedir?

A: Hedef sayfa belirtmek, dosya açıldığında PDF belgesinin hangi sayfasının görüntüleneceğini kontrol etmenizi sağlar. Bu, kullanıcı deneyimini, onları ilgi duydukları belirli bir sayfaya yönlendirerek iyileştirebilir.

#### S: PDF belgelerinde hedef sayfa belirtmenin faydası ne olabilir?

A: Kullanıcıların sayfalar arasında manuel olarak gezinmelerine gerek kalmadan onları PDF belgesindeki belirli bir bölüme veya içeriğe yönlendirmek istediğinizde hedef sayfa belirtmek faydalıdır.

#### S: Aspose.PDF for .NET, görüntülenecek hedef sayfanın belirlenmesini nasıl kolaylaştırır?

A: Aspose.PDF for .NET, hedef sayfa, yakınlaştırma düzeyi ve diğer görüntüleme özellikleri de dahil olmak üzere bir PDF belgesinin ilk görünümünü ayarlamanıza olanak tanıyan API'ler sağlar.

#### S: Hedef sayfa olarak herhangi bir sayfayı belirleyebilir miyim?

A: Evet, PDF belgesindeki herhangi bir sayfayı görüntüleme için hedef sayfa olarak belirtebilirsiniz. İstediğiniz sayfayı seçmek için uygun dizini kullanmanız yeterlidir.

#### S: Hedef sayfa belirlenirken yakınlaştırma faktörünün önemi nedir?

A: Yakınlaştırma faktörü, PDF belgesi açıldığında hedef sayfaya uygulanan büyütme düzeyini belirler. Görünüm alanında ne kadar içerik görüntüleneceğini kontrol eder.

#### S: Farklı hedef sayfalar için farklı yakınlaştırma faktörleri ayarlayabilir miyim?

A: Evet, ayrı yakınlaştırma faktörleri oluşturarak farklı hedef sayfalar için farklı yakınlaştırma faktörleri ayarlayabilirsiniz.`GoToAction` örnekleri ve hedeflerini buna göre yapılandırma.

#### S: Hedef sayfa belirtmede herhangi bir sınırlama var mı?

A: Hedef sayfa belirtmek, PDF açıldığında ilk görünümü kontrol etmekle sınırlıdır. PDF görüntülendikten sonra kullanıcı etkileşimlerini veya gezinmeyi etkilemez.

#### S: Bu özelliği PDF belgesi içerisinde sunum oluşturmak için kullanabilir miyim?

C: Evet, bu özelliği kullanarak PDF belgesinde sunum benzeri deneyimler yaratabilir, kullanıcıları farklı bölümler veya konular arasında yönlendirebilirsiniz.

#### S: Başlangıç görünümünün sayfa düzeni gibi diğer yönlerini özelleştirebilir miyim?

C: Evet, Aspose.PDF for .NET, sayfa düzeni, sayfa modu ve daha fazlası dahil olmak üzere ilk görünümün diğer yönlerini özelleştirmek için özellikler sağlar.

#### S: Belirtilen hedef sayfanın ve yakınlaştırma faktörünün amaçlandığı gibi çalışıp çalışmadığını nasıl test edebilirim?

A: Hedef sayfayı ve yakınlaştırma faktörünü belirtmek için verilen kodu uyguladıktan sonra, değiştirilmiş PDF dosyasını açın ve doğru sayfa ve yakınlaştırma seviyesiyle açıldığını doğrulayın.