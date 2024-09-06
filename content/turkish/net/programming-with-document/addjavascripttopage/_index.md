---
title: PDF Dosyasına Java Script Ekle
linktitle: Java Script PDF Dosyası Ekle
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasına JavaScript eklemeyi öğrenin. Belge ve sayfa düzeyinde komut dosyası oluşturma için kod eğitimleriyle adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-document/addjavascripttopage/
---
## giriiş

PDF'lerinizi açılır uyarılar veya otomatik yazdırma işlevleri gibi etkileşimli öğelerle nasıl geliştirebileceğinizi hiç merak ettiniz mi? İyi haber şu ki, yapabilirsiniz! Aspose.PDF for .NET kullanarak, PDF belgelerinize sorunsuz bir şekilde JavaScript ekleyebilirsiniz. İster görevleri otomatikleştirin ister dinamik kullanıcı deneyimleri oluşturun, JavaScript'i PDF'lere yerleştirmek dosyalarınıza o ekstra işlevsellik düzeyini kazandırır.

## Ön koşullar

Kodlama kısmına geçmeden önce, ayarlamanız gereken birkaç şey var:

-  .NET için Aspose.PDF: Kütüphaneyi şu adresten indirin:[Aspose Sürümleri](https://releases.aspose.com/pdf/net/) veya bir tane al[ücretsiz deneme](https://releases.aspose.com/).
- Geliştirme Ortamı: Visual Studio gibi herhangi bir .NET uyumlu IDE.
- Temel C# Bilgisi: Bu kılavuz, temel C# sözdizimine aşina olduğunuzu varsayar.
-  Geçici Lisans (İsteğe bağlı): Bir tane alabilirsiniz[geçici lisans](https://purchase.aspose.com/temporary-license/) Gelişiminiz sırasında sınırlamalardan kaçınmak istiyorsanız.

## Paketleri İçe Aktar

Kod yazmaya başlamadan önce, Aspose.PDF kütüphanesinden gerekli ad alanlarını içe aktarmanız gerekir. Bu ad alanları PDF'leri düzenlemenize ve JavaScript eylemlerini kolayca eklemenize olanak tanır.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Artık doğru ad alanlarını içe aktardığınıza göre, kodlamaya başlamaya hazırsınız.

## Adım 1: Mevcut bir PDF'yi yükleyin

İlk önce ilk şeyler—JavaScript eklemek istediğiniz PDF belgesini yüklemeniz gerekir. Bu adım, tüm sonraki değişiklikler için sahneyi hazırlar. Açıldığında belgeyi otomatik olarak yazdırmak gibi dinamik işlevsellikle geliştirmek istediğiniz bir PDF'niz olduğunu düşünün.

PDF dosyasını şu şekilde yükleyebilirsiniz:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Mevcut bir PDF dosyasını yükleyin
Document doc = new Document(dataDir + "input.pdf");
```

 Bu kod parçacığında şunu kullanıyoruz:`Document` belirtilen dizinden mevcut bir PDF dosyasını yüklemek için sınıf. Değiştirdiğinizden emin olun`"YOUR DOCUMENT DIRECTORY"` PDF dosyanızın gerçek yolunu belirtin.

## Adım 2: Belge Düzeyinde JavaScript Ekleyin

Şimdi, belge açıldığında tetiklenecek biraz JavaScript ekleyelim. Bu örnekte, kullanıcı PDF'yi açar açmaz yazdırma iletişim kutusunu açan bir betik yazacağız.

Belge düzeyindeki JavaScript, tüm PDF'e uygulamak istediğiniz eylemler için mükemmeldir. Bunu, belgeniz için genel bir kural ayarlamak gibi düşünün.

İşte kod:

```csharp
// Belge Düzeyinde JavaScript Ekleme
// JavascriptAction'ı istenen JavaScript ifadesiyle örneklendirin
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

// JavascriptAction nesnesini Belgenin OpenAction'ına atayın
doc.OpenAction = javaScript;
```

 Bu adımda bir tane oluşturuyoruz`JavascriptAction` Belge açıldığında yazdırma iletişim kutusunu açmak için bir JavaScript işlevi tanımlayan nesne.`doc.OpenAction` Daha sonra özelliğe bu JavaScript eylemi atanır.

## Adım 3: Sayfa Düzeyinde JavaScript Ekleyin

Her eylemin tüm belgeyi etkilemesi gerekmez. Bazen, belirli sayfalar açıldığında veya kapatıldığında belirli eylemlerin gerçekleşmesini istersiniz. Burada, belirli bir sayfa (örneğin sayfa 2) açıldığında ve kapatıldığında JavaScript eylemleri ayarlayacağız.

Sayfa düzeyinde JavaScript, hedeflenen etkileşimler için kullanışlıdır. Bir kullanıcı bir sayfaya gittiğinde bir mesaj görüntülemekten, form alanlarını otomatik doldurma gibi özel eylemlere kadar her şey olabilir.

Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
// Sayfa Düzeyinde JavaScript Ekleme
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('Page 2 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('Page 2 closed')");
```

Bu kod parçacığına iki JavaScript eylemi ekliyoruz:
1. OnOpen Eylemi: Kullanıcı 2. sayfayı açtığında “2. sayfa açıldı” uyarısını görüntüler.
2. OnClose Eylemi: Kullanıcı 2. sayfadan ayrıldığında “Sayfa 2 kapatıldı” uyarısını görüntüler.

Bu, PDF'nize bir etkileşim katmanı ekler. Kullanıcıyı farklı sayfalardaki bir dizi adımda yönlendirdiğinizi ve bir sayfaya girdiklerinde veya sayfadan ayrıldıklarında açılan uyarılarla hayal edin.

## Adım 4: PDF Belgesini Kaydedin

Artık hem belgeye hem de belirli sayfalara JavaScript eklediniz. Son adım, değiştirilen PDF'yi istediğiniz yere kaydetmektir. Bu kısım basit ama çok önemlidir—çalışmanızı kaydetmeyi unutmayın!

İşte kod:

```csharp
// Çıktı dosyası yolunu belirtin
dataDir = dataDir + "JavaScript-Added_out.pdf";

// Güncellenen PDF belgesini kaydedin
doc.Save(dataDir);

Console.WriteLine("\nJavaScript added successfully to the PDF.\nFile saved at " + dataDir);
```

 Bu kod parçacığında, eklenen JavaScript ile güncellenen belgeyi yeni bir dosyaya kaydediyoruz.`"JavaScript-Added_out.pdf"`Bu, orijinal dosyanızın üzerine yazmamanızı sağlar ve üzerinde çalışabileceğiniz bir yedek sunar.

## Çözüm

Aspose.PDF for .NET kullanarak PDF dosyalarına JavaScript eklemek, etkileşimli, dinamik PDF'ler oluşturmanın güçlü bir yoludur. Yazdırma veya özel uyarılar oluşturma gibi görevleri otomatikleştiriyor olun, JavaScript'i PDF'nize yerleştirme yeteneği belgelerinizi daha ilgi çekici ve işlevsel hale getirir.

## SSS

### Bir PDF'deki farklı sayfalara birden fazla JavaScript eylemi ekleyebilir miyim?
Evet, farklı JavaScript eylemlerini tek tek sayfalara veya tüm belgeye atayabilirsiniz.

### PDF'e JavaScript eklendikten sonra JavaScript'i kaldırmak mümkün müdür?
Evet, mevcut JavaScript eylemlerini temizleyerek kaldırabilir veya değiştirebilirsiniz.`Actions` Belgenin veya sayfanın özellikleri.

### PDF'de hangi tür JavaScript fonksiyonlarını kullanabilirim?
Yazdırma, uyarılar ve form düzenlemeleri gibi Adobe Acrobat'ın JavaScript motorunun desteklediği tüm JavaScript'leri kullanabilirsiniz.

### JavaScript tüm PDF görüntüleyicilerinde çalışır mı?
Çoğu JavaScript eylemi, Adobe Acrobat gibi etkileşimli PDF'leri destekleyen PDF görüntüleyicilerinde çalışır. Ancak, bazı temel PDF okuyucuları JavaScript'i desteklemeyebilir.

### PDF'deki kullanıcı girdisine bağlı olarak JavaScript eylemlerini tetikleyebilir miyim?
Evet, kullanıcı girdisine göre eylemleri tetiklemek için JavaScript'i form alanlarına bağlayabilirsiniz.