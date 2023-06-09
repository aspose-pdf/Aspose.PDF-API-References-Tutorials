---
title: Hedef Bağlantıyı Ayarla
linktitle: Hedef Bağlantıyı Ayarla
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF dosyasında bir hedef bağlantısını nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 90
url: /tr/net/programming-with-links-and-actions/set-destination-link/
---

Bu adım adım kılavuz ile Aspose.PDF for .NET kullanarak bir PDF dosyasında nasıl hedef bağlantı ayarlayacağınızı öğrenin.

## 1. Adım: Ortamı ayarlama

Geliştirme ortamınızı bir C# projesi ve uygun Aspose.PDF referansları ile kurduğunuzdan emin olun.

## 2. Adım: PDF dosyasını yükleme

Belgelerinizin dizin yolunu ayarlayın ve aşağıdaki kodu kullanarak PDF dosyasını yükleyin:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// PDF dosyasını yükleyin
Document doc = new Document(dataDir + "UpdateLinks.pdf");
```

## 3. Adım: Hedef bağlantısını düzenleme

Aşağıdaki kodu kullanarak değiştirmek için bağlantı ek açıklamasını alın:

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
```

 ayarlayabilirsiniz`[1]` belirli bir sayfa veya ek açıklamayı seçmek için dizinler.

Ardından, bağlantı eylemini değiştirerek ve hedefi bir web adresi olarak ayarlayarak bağlantıyı düzenleyin:

```csharp
linkAnnot.Action = new GoToURIAction("www.aspose.com");
```

## 4. Adım: Belgeyi güncellenmiş bağlantıyla kaydedin

kullanarak belgeyi güncellenmiş bağlantıyla kaydedin.`Save` yöntem:

```csharp
dataDir = dataDir + "SetDestinationLink_out.pdf";
doc.Save(dataDir);
```

## 5. Adım: Sonucun görüntülenmesi

Hedef bağlantının başarıyla yapılandırıldığını belirten bir mesaj görüntüleyin ve kaydedilen dosyanın konumunu belirtin:

```csharp
Console.WriteLine("\nDestination link configured successfully.\nFile saved to location: " + dataDir);
```

### Aspose.PDF for .NET kullanarak Set Destination Link için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// PDF dosyasını yükleyin
	Document doc = new Document(dataDir + "UpdateLinks.pdf");
	// Belgenin ilk sayfasından ilk bağlantı ek açıklamasını alın
	LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
	// Değişiklik bağlantısı: bağlantı eylemini değiştirin ve hedefi web adresi olarak ayarlayın
	linkAnnot.Action = new GoToURIAction("www.aspose.com");           
	dataDir = dataDir + "SetDestinationLink_out.pdf";
	// Belgeyi güncellenmiş bağlantıyla kaydedin
	doc.Save(dataDir);
	Console.WriteLine("\nDestination link setup successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF dosyasında nasıl hedef bağlantı ayarlayacağınızı biliyorsunuz. PDF belgelerinizdeki bağlantıları özelleştirmek ve kullanıcılar için etkileşimli deneyimler oluşturmak için bu bilgiyi kullanın.

Artık bu kılavuzu tamamladığınıza göre, bu kavramları kendi projelerinize uygulayabilir ve Aspose.PDF for .NET tarafından sunulan özellikleri daha fazla keşfedebilirsiniz.