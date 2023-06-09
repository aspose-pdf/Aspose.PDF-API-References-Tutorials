---
title: Hedef Bağlantıyı Ayarla
linktitle: Hedef Bağlantıyı Ayarla
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF dosyasında nasıl hedef bağlantı ayarlayacağınızı öğrenin.
type: docs
weight: 100
url: /tr/net/programming-with-links-and-actions/set-target-link/
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
Document document = new Document(dataDir + "UpdateLinks.pdf");
```

## 3. Adım: Hedef bağlantıyı düzenleme

Aşağıdaki kodu kullanarak değiştirmek için bağlantı ek açıklamasını alın:

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
```

 ayarlayabilirsiniz`[1]` belirli bir sayfa veya ek açıklamayı seçmek için dizinler.

Ardından, dosyayı güncellemeden hedefi güncelleyin:

```csharp
goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
```

Ayrıca dosyayı güncellemek isterseniz:

```csharp
goToR.File = new FileSpecification(dataDir + "input.pdf");
```

## 4. Adım: Belgeyi güncellenmiş bağlantıyla kaydedin

kullanarak belgeyi güncellenmiş bağlantıyla kaydedin.`Save` yöntem:

```csharp
dataDir = dataDir + "SetTargetLink_out.pdf";
document. Save(dataDir);
```

## 5. Adım: Sonucun görüntülenmesi

Hedef bağlantının başarıyla yapılandırıldığını belirten bir mesaj görüntüleyin ve kaydedilen dosyanın konumunu belirtin:

```csharp
Console.WriteLine("\nConfiguration of target link successful.\nFile saved at location: " + dataDir);
```

### Aspose.PDF for .NET kullanarak Set Target Link için örnek kaynak kodu 
```csharp
try
{
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// PDF dosyasını yükleyin
	Document document = new Document(dataDir + "UpdateLinks.pdf");
	LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
	GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
	// Sonraki satır güncelleme hedefi, dosyayı güncelleme
	goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
	// Sonraki satır güncelleme dosyası
	goToR.File = new FileSpecification(dataDir +  "input.pdf");
	dataDir = dataDir + "SetTargetLink_out.pdf";
	// Belgeyi güncellenmiş bağlantıyla kaydedin
	document.Save(dataDir);
	Console.WriteLine("\nTarget link setup successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Çözüm

Tebrikler! Artık Aspose.PDF for .NET kullanarak bir PDF dosyasında nasıl hedef bağlantı ayarlayacağınızı biliyorsunuz. PDF belgelerinizdeki bağlantıları özelleştirmek ve kullanıcılar için etkileşimli deneyimler oluşturmak için bu bilgiyi kullanın.

Artık bu kılavuzu tamamladığınıza göre, bu kavramları kendi projelerinize uygulayabilir ve Aspose.PDF for .NET tarafından sunulan özellikleri daha fazla keşfedebilirsiniz.