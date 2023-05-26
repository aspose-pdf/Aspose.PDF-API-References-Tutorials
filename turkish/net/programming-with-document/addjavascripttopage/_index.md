---
title: Sayfaya Java Script Ekle
linktitle: Sayfaya Java Script Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyalarına nasıl JavaScript ekleyeceğinizi öğrenin. Belge ve sayfa düzeyinde komut dosyası oluşturmaya yönelik kod eğitimlerini içeren adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-document/addjavascripttopage/
---

Bir PDF dosyasına JavaScript eklemek için Aspose.PDF for .NET'i kullanacağız. Bu kitaplık, .NET uygulamalarında PDF dosyalarıyla çalışmanın basit ve etkili bir yolunu sağlar. Aşağıdaki adımlar, Aspose.PDF for .NET kullanarak bir PDF dosyasına JavaScript ekleme sürecinde size rehberlik edecektir.

## 1. Adım: PDF Dosyasını Yükleyin

 İlk adım, JavaScript eklemek istediğiniz PDF dosyasını yüklemektir. Bunu kullanarak yapabilirsiniz`Document` Aspose.PDF for .NET tarafından sağlanan sınıf. bu`Document` class, PDF dosyalarını yüklemek, kaydetmek ve değiştirmek için yöntemler sağlar.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mevcut bir PDF dosyasını yükleyin
Document doc = new Document(dataDir + "input.pdf");
```

## 2. Adım: JavaScript'i Belge Düzeyinde Ekleyin

 JavaScript'i belge düzeyinde eklemek için kullanacağız`JavascriptAction` Aspose.PDF for .NET tarafından sağlanan sınıf. Bu sınıf, PDF dosyasına eklemek istediğiniz JavaScript deyimini belirtmenize olanak tanır.

```csharp
// Belge Düzeyinde JavaScript Ekleme
// JavascriptAction'ı istenen JavaScript deyimiyle örnekleyin
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Belgenin istenen eylemine JavascriptAction nesnesini atayın
doc.OpenAction = javaScript;
```

Bu eğitimde, belge açıldığında PDF dosyasını belirtilen seçeneklerle yazdıracak bir JavaScript ifadesi ekliyoruz.

## 3. Adım: Sayfa Düzeyinde JavaScript ekleyin

 Sayfa düzeyinde JavaScript eklemek için kullanacağız`JavascriptAction` sınıf ve`Actions` Aspose.PDF for .NET tarafından sağlanan özellik. Bu özellik, sayfa açıldığında veya kapatıldığında yürütülecek JavaScript deyimlerini belirtmenize olanak tanır.

```csharp
// Sayfa Düzeyinde JavaScript Ekleme
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");
```

Bu eğitimde, sayfa açıldığında veya kapatıldığında bir uyarı mesajı görüntüleyecek JavaScript ifadeleri ekliyoruz.

## 4. Adım: PDF Dosyasını Kaydedin

 JavaScript'i PDF dosyasına ekledikten sonra değiştirilen dosyayı kaydetmeniz gerekir. Bunu kullanarak yapabilirsiniz`Save` tarafından sağlanan yöntem`Document` sınıf.

```csharp
dataDir = dataDir + "JavaScript-Added_out.pdf";
// PDF Belgesini Kaydet
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);
```

Bu kod, değiştirilen PDF dosyasını belirtilen dizine kaydedecektir.

### Aspose.PDF for .NET kullanarak Sayfaya Java Script Ekleme için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mevcut bir PDF dosyasını yükleyin

```csharp
            
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mevcut bir PDF dosyasını yükleyin
Document doc = new Document(dataDir + "input.pdf");

// Belge Düzeyinde JavaScript Ekleme
//JavascriptAction'ı istenen JavaScript deyimiyle örnekleyin
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Belgenin istenen eylemine JavascriptAction nesnesini atayın
doc.OpenAction = javaScript;

// Sayfa Düzeyinde JavaScript Ekleme
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");

dataDir = dataDir + "JavaScript-Added_out.pdf";
// PDF Belgesini Kaydet
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);
        
```

## Çözüm

Bu yazıda, Aspose.PDF for .NET kullanarak bir PDF dosyasına hem belge düzeyinde hem de sayfa düzeyinde nasıl JavaScript ekleneceğini açıkladık. Adım adım talimatlar sağladık ve her örnek için tam kaynak kodunu ekledik. Bu bilgiyle PDF dosyalarınıza JavaScript ekleyebilir ve davranışlarını ihtiyaçlarınıza göre özelleştirebilirsiniz.


