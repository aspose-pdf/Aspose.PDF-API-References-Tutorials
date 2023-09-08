---
title: Görüntülerken Sayfayı Belirtin
linktitle: Görüntülerken Sayfayı Belirtin
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak bir PDF'yi görüntülerken bir sayfayı nasıl belirleyeceğinizi öğrenin.
type: docs
weight: 110
url: /tr/net/programming-with-links-and-actions/specify-page-when-viewing/
---
Bu adım adım kılavuzla Aspose.PDF for .NET kullanarak bir PDF dosyasını görüntülerken bir sayfayı nasıl belirleyeceğinizi öğrenin.

## 1. Adım: Ortamı ayarlama

Geliştirme ortamınızı bir C# projesi ve uygun Aspose.PDF referanslarıyla kurduğunuzdan emin olun.

## Adım 2: PDF dosyasını yükleme

Belgelerinizin dizin yolunu ayarlayın ve aşağıdaki kodu kullanarak PDF dosyasını yükleyin:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// PDF dosyasını yükleyin
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## 3. Adım: Hedef sayfayı belirtme

Aşağıdaki kodu kullanarak hedef sayfa örneğini alın:

```csharp
Page page2 = doc.Pages[2];
```

 Endeksi ayarlayabilirsiniz`[2]` İstediğiniz sayfayı seçmek için

## 4. Adım: Yakınlaştırma ayarını yapılandırma

Hedef sayfa yakınlaştırma faktörünü ayarlamak için bir değişken oluşturun:

```csharp
double zoom = 1;
```

Yakınlaştırma değerini ihtiyaçlarınıza göre ayarlayabilirsiniz.

## 5. Adım: Gezinme eylemini oluşturun

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

## 8. Adım: Güncellenen belgeyi kaydedin

 Güncellenen belgeyi kullanarak kaydedin.`Save` yöntem:

```csharp
doc.Save(dataDir + "goto2page_out.pdf");
```

### Aspose.PDF for .NET kullanarak Görüntülerken Sayfayı Belirtin için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// PDF dosyasını yükleyin
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
// Belgenin ikinci sayfasının örneğini alın
Page page2 = doc.Pages[2];
// Hedef sayfanın yakınlaştırma faktörünü ayarlamak için değişkeni oluşturun
double zoom = 1;
// GoToAction örneği oluşturun
GoToAction action = new GoToAction(doc.Pages[2]);
// 2 sayfaya git
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
// Belge açma eylemini ayarlama
doc.OpenAction = action;
// Güncellenen belgeyi kaydet
doc.Save(dataDir + "goto2page_out.pdf");
```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF'yi görüntülerken bir sayfayı nasıl belirleyeceğinizi biliyorsunuz. PDF belgelerinizdeki kullanıcı görüntüleme deneyimini özelleştirmek için bu bilgiyi kullanın.

Artık bu kılavuzu tamamladığınıza göre, bu kavramları kendi projelerinize uygulayabilir ve Aspose.PDF for .NET'in sunduğu özellikleri daha fazla keşfedebilirsiniz.

### SSS'ler 

#### S: Bir PDF dosyasını görüntülerken hedef sayfayı belirtmenin amacı nedir?

C: Bir hedef sayfa belirlemek, dosya açıldığında PDF belgesinin hangi sayfasının görüntüleneceğini kontrol etmenize olanak tanır. Bu, kullanıcıları belirli bir ilgi çekici sayfaya yönlendirerek kullanıcı deneyimini geliştirebilir.

#### S: PDF belgelerinde hedef sayfa belirlemek nasıl faydalı olabilir?

C: Kullanıcıların sayfalar arasında manuel olarak gezinmesine gerek kalmadan, kullanıcıları bir PDF belgesi içindeki belirli bir bölüme veya içeriğe yönlendirmek istediğinizde, hedef sayfanın belirtilmesi yararlı olur.

#### S: Aspose.PDF for .NET, görüntülenecek hedef sayfayı belirlemeyi nasıl kolaylaştırır?

C: Aspose.PDF for .NET, hedef sayfa, yakınlaştırma düzeyi ve diğer görüntüleme özellikleri de dahil olmak üzere bir PDF belgesinin ilk görünümünü ayarlamanıza olanak tanıyan API'ler sağlar.

#### S: Hedef sayfa olarak herhangi bir sayfayı belirtebilir miyim?

C: Evet, PDF belgesindeki herhangi bir sayfayı görüntülenecek hedef sayfa olarak belirtebilirsiniz. İstediğiniz sayfayı seçmek için uygun dizini kullanmanız yeterlidir.

#### S: Hedef sayfayı belirlerken yakınlaştırma faktörünün önemi nedir?

C: Yakınlaştırma faktörü, PDF belgesi açıldığında hedef sayfaya uygulanan büyütme düzeyini belirler. Görünüm alanında ne kadar içeriğin görüntüleneceğini kontrol eder.

#### S: Farklı hedef sayfalar için farklı yakınlaştırma faktörleri ayarlayabilir miyim?

C: Evet, ayrı sayfalar oluşturarak farklı hedef sayfalar için farklı yakınlaştırma faktörleri ayarlayabilirsiniz.`GoToAction` örnekleri ve hedeflerini buna göre yapılandırmak.

#### S: Hedef sayfa belirlemede herhangi bir sınırlama var mı?

C: Hedef sayfayı belirlemek, PDF açıldığında ilk görünümü kontrol etmekle sınırlıdır. PDF görüntülendikten sonra kullanıcı etkileşimlerini veya gezinmeyi etkilemez.

#### S: Bu özelliği bir PDF belgesinde sunumlar oluşturmak için kullanabilir miyim?

C: Evet, bu özelliği bir PDF belgesinde sunum benzeri deneyimler oluşturmak ve kullanıcılara farklı bölümler veya konular boyunca rehberlik etmek için kullanabilirsiniz.

#### S: İlk görünümün sayfa düzeni gibi diğer yönlerini özelleştirebilir miyim?

C: Evet, Aspose.PDF for .NET, sayfa düzeni, sayfa modu ve daha fazlası dahil olmak üzere ilk görünümün diğer yönlerini özelleştirmek için özellikler sağlar.

#### S: Belirtilen hedef sayfanın ve yakınlaştırma faktörünün amaçlandığı gibi çalışıp çalışmadığını nasıl test edebilirim?

C: Hedef sayfayı ve yakınlaştırma faktörünü belirlemek için sağlanan kodu uyguladıktan sonra, değiştirilen PDF dosyasını açın ve dosyanın doğru sayfa ve yakınlaştırma düzeyiyle açıldığını doğrulayın.