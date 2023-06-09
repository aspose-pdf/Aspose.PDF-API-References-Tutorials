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