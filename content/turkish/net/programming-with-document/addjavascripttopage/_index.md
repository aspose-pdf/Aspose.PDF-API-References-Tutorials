---
title: PDF Dosyasına Java Komut Dosyası Ekleme
linktitle: Java Komut Dosyası PDF Dosyası Ekle
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF dosyasına nasıl JavaScript ekleyeceğinizi öğrenin. Belge ve sayfa düzeyinde komut dosyası oluşturmaya yönelik kod eğitimlerini içeren adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-document/addjavascripttopage/
---
Bir PDF dosyasına JavaScript eklemek için Aspose.PDF for .NET'i kullanacağız. Bu kitaplık, .NET uygulamalarında PDF dosyalarıyla çalışmanın basit ve etkili bir yolunu sağlar. Aşağıdaki adımlar Aspose.PDF for .NET kullanarak bir PDF dosyasına JavaScript ekleme sürecinde size yol gösterecektir.

## 1. Adım: PDF Dosyasını Yükleyin

 İlk adım, JavaScript eklemek istediğiniz PDF dosyasını yüklemektir. Bunu kullanarak yapabilirsiniz`Document` sınıf Aspose.PDF for .NET tarafından sağlanmıştır.`Document` class, PDF dosyalarını yüklemek, kaydetmek ve değiştirmek için yöntemler sağlar.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mevcut bir PDF dosyasını yükleyin
Document doc = new Document(dataDir + "input.pdf");
```

## 2. Adım: Belge Düzeyinde JavaScript ekleyin

Belge düzeyinde JavaScript eklemek için şunu kullanacağız:`JavascriptAction` sınıf Aspose.PDF for .NET tarafından sağlanmıştır. Bu sınıf, PDF dosyasına eklemek istediğiniz JavaScript ifadesini belirtmenize olanak tanır.

```csharp
// Belge Düzeyinde JavaScript Ekleme
// İstediğiniz JavaScript ifadesiyle JavascriptAction örneğini oluşturun
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// Belgenin istenen eylemine JavascriptAction nesnesini atayın
doc.OpenAction = javaScript;
```

Bu eğitimde, PDF dosyasını belge açıldığında belirtilen seçeneklerle yazdıracak bir JavaScript ifadesi ekliyoruz.

## 3. Adım: Sayfa Düzeyinde JavaScript ekleyin

 Sayfa düzeyinde JavaScript eklemek için şunu kullanacağız:`JavascriptAction` sınıf ve`Actions` Aspose.PDF for .NET tarafından sağlanan özellik. Bu özellik, sayfa açıldığında veya kapatıldığında yürütülecek JavaScript ifadelerini belirtmenize olanak tanır.

```csharp
// Sayfa Düzeyinde JavaScript Ekleme
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");
```

Bu eğitimde, sayfa açıldığında veya kapatıldığında bir uyarı mesajı görüntüleyecek JavaScript ifadeleri ekliyoruz.

## Adım 4: PDF Dosyasını Kaydedin

JavaScript'i PDF dosyasına ekledikten sonra değiştirilen dosyayı kaydetmeniz gerekir. Bunu kullanarak yapabilirsiniz`Save` tarafından sağlanan yöntem`Document` sınıf.

```csharp
dataDir = dataDir + "JavaScript-Added_out.pdf";
// PDF Belgesini Kaydet
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);
```

Bu kod, değiştirilen PDF dosyasını belirtilen dizine kaydedecektir.

### Aspose.PDF for .NET kullanarak Sayfaya Java Komut Dosyası Ekleme için örnek kaynak kodu

```csharp
            
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mevcut bir PDF dosyasını yükleyin
Document doc = new Document(dataDir + "input.pdf");

// Belge Düzeyinde JavaScript Ekleme
// İstenilen JavaScript ifadesiyle JavascriptAction örneğini oluşturun
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

Bu yazıda Aspose.PDF for .NET kullanarak bir PDF dosyasına hem belge düzeyinde hem de sayfa düzeyinde JavaScript'in nasıl ekleneceğini açıkladık. Her örnek için adım adım talimatlar sağladık ve tam kaynak kodunu ekledik. Bu bilgiyle PDF dosyalarınıza JavaScript ekleyebilir ve davranışlarını ihtiyaçlarınıza göre özelleştirebilirsiniz.


### PDF dosyasına java betiği eklemek için SSS

#### S: Aspose.PDF for .NET nedir?

C: Aspose.PDF for .NET, geliştiricilerin .NET uygulamalarında PDF dosyalarıyla çalışmasına olanak tanıyan güçlü bir kitaplıktır. PDF belgelerini oluşturmak, değiştirmek ve işlemek için çok çeşitli özellikler sunar.

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesine JavaScript ekleyebilir miyim?

C: Evet, Aspose.PDF for .NET, bir PDF dosyasının hem belge düzeyine hem de sayfa düzeyine JavaScript eklemenizi sağlayarak dinamik ve etkileşimli PDF belgeleri oluşturmanıza olanak tanır.

#### S: Mevcut bir PDF dosyasını Aspose.PDF for .NET kullanarak nasıl yüklerim?

 C: Mevcut bir PDF dosyasını kullanarak yükleyebilirsiniz.`Document` Adım adım kılavuzda gösterildiği gibi sınıf ve yöntemleri.

#### S: Bir PDF belgesine ne tür JavaScript eylemleri ekleyebilirim?

C: Aspose.PDF for .NET ile yazdırma, uyarı mesajları, form alanı düzenleme ve daha fazlası gibi çok çeşitli JavaScript eylemleri ekleyebilirsiniz.

#### S: Aspose.PDF for .NET ticari projeler için uygun mudur?

C: Evet, Aspose.PDF for .NET, ticari projelerde PDF düzenleme ve oluşturma görevleri için yaygın olarak kullanılan güvenilir ve sağlam bir kitaplıktır.

