---
title: Eksik Yazı Tiplerini Değiştirin
linktitle: Eksik Yazı Tiplerini Değiştirin
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak bir PDF dosyasındaki eksik yazı tiplerini değiştirmek için adım adım kılavuz.
type: docs
weight: 260
url: /tr/net/document-conversion/replace-missing-fonts/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasındaki eksik yazı tiplerini değiştirme sürecinde size yol göstereceğiz. Belirli bir yazı tipinin eksik olduğu bir makinede bir PDF dosyasını açtığınızda yazı tipi görüntüleme sorunları ortaya çıkabilir. Bu gibi durumlarda eksik yazı tipini makinede bulunan başka bir yazı tipiyle değiştirmek mümkündür. Aşağıdaki adımları takip ederek PDF dosyasındaki eksik fontları değiştirebileceksiniz.

## Önkoşullar
Başlamadan önce aşağıdaki önkoşulları karşıladığınızdan emin olun:

- C# programlama dili hakkında temel bilgiler.
- Sisteminizde yüklü olan .NET için Aspose.PDF kütüphanesi.
- Visual Studio gibi bir geliştirme ortamı.

## 1. Adım: Eksik yazı tipini bulma
İlk adım, PDF dosyasında eksik yazı tipini bulmaktır. Aşağıdaki kodu kullanın:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
     // Orijinal yazı tipini bulun
     originalFont = FontRepository.FindFont("AgencyFB");
}
catch(Exception)
{
     // Hedef makinede yazı tipi eksik
     // Basit yazı tipi değişimi ekleme
     FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
```

 Değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` PDF dosyanızın bulunduğu gerçek dizinle.

## 2. Adım: Eksik yazı tipini değiştirin
Daha sonra eksik yazı tipini mevcut başka bir yazı tipiyle değiştireceğiz. Aşağıdaki kodu kullanın:

```csharp
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");

// PDF dosyasını hata giderme özelliğiyle PDF/A formatına dönüştürün
pdf.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

// Ortaya çıkan PDF dosyasını kaydedin
pdf.Save(fileNew.FullName);
```

 Değiştirdiğinizden emin olun`"input.pdf"` orijinal PDF dosyanızın gerçek yolunu ve`"newfile_out.pdf"` ortaya çıkan PDF dosyası için istenen adla.

## 3. Adım: Ortaya çıkan PDF dosyasını kaydetme
Son olarak, ortaya çıkan PDF dosyasını değiştirilen yazı tipiyle kaydedeceğiz. Aşağıdaki kodu kullanın:

```csharp
// Ortaya çıkan PDF dosyasını kaydedin
pdf.Save(fileNew.FullName);
```

Ortaya çıkan PDF dosyası için doğru hedef yolunu ayarladığınızdan emin olmanızı sağlar.

### Aspose.PDF for .NET kullanarak Eksik Fontları Değiştirmek için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
	originalFont = FontRepository.FindFont("AgencyFB");
}
catch (Exception)
{
	// Hedef makinede yazı tipi eksik
	FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");
pdf.Convert( dataDir +  "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
pdf.Save(fileNew.FullName);
```

## Çözüm
Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF dosyasındaki eksik fontları değiştirme işlemini adım adım anlattık. Yukarıda özetlenen talimatları izleyerek PDF dosyanızdaki eksik yazı tiplerini başarıyla değiştirebileceksiniz.

### SSS'ler

#### S: Aspose.PDF for .NET nedir?

C: Aspose.PDF for .NET, geliştiricilerin C# uygulamalarında PDF belgeleriyle çalışmasına olanak tanıyan güçlü bir kitaplıktır. PDF dosyalarındaki eksik yazı tiplerini değiştirme yeteneği de dahil olmak üzere çeşitli işlevler sunar.

#### S: Bir PDF dosyasında neden eksik yazı tipleriyle karşılaşayım?

C: Dosya gerekli yazı tiplerinin yüklü olmadığı bir makinede açıldığında PDF dosyasında eksik yazı tipleri oluşabilir. Bu, belgenin görsel görünümünü etkileyen yazı tipi değişikliğine yol açabilir.

#### S: Aspose.PDF for .NET kullanarak bir PDF dosyasındaki eksik yazı tiplerini nasıl bulabilir ve değiştirebilirim?

 C: Eksik yazı tiplerini bulmak ve değiştirmek için`FontRepository.FindFont` Gerekli yazı tipinin varlığını kontrol etme yöntemi. Yazı tipi eksikse, kullanarak bir yazı tipi değişimi ekleyebilirsiniz.`FontRepository.Substitutions` mülk.

#### S: Yazı tipi değiştirme işlemini özelleştirebilir miyim?

C: Evet, değişiklik için farklı bir yazı tipi belirterek yazı tipi değiştirme işlemini özelleştirebilirsiniz. Verilen kodda eksik olan "AgencyFB" fontunun yerine Arial kullandık ancak siz tercihlerinize göre farklı bir font seçebilirsiniz.

#### S: Değiştirme sonrasında yazı tipi oluşturmanın doğruluğunu nasıl sağlayabilirim?

C: Aspose.PDF for .NET, güçlü yazı tipi işleme yetenekleri sağlayarak, değiştirildikten sonra doğru yazı tipi oluşturmayı sağlar. Yazı tipi değişimini doğrulamak için ortaya çıkan PDF dosyasını önizleyebilirsiniz.