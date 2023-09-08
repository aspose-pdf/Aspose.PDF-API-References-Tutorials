---
title: Not Yapısı Öğesi Oluştur
linktitle: Not Yapısı Öğesi Oluştur
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak bir PDF belgesinde yapılandırılmış not öğeleri oluşturmak için adım adım kılavuz.
type: docs
weight: 30
url: /tr/net/programming-with-tagged-pdf/create-note-structure-element/
---
Bu eğitimde size Aspose.PDF for .NET kullanarak bir PDF belgesinde not yapısı öğesinin nasıl oluşturulacağı konusunda adım adım bir kılavuz sunacağız. Aspose.PDF, PDF belgelerini programlı olarak oluşturmanıza, değiştirmenize ve dönüştürmenize olanak tanıyan güçlü bir kütüphanedir. Aspose.PDF'in işaretlenmiş içerik yapısı özelliklerini kullanarak PDF belgenize yapılandırılmış notlar ekleyebilirsiniz.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1. .NET framework ile yüklenen Visual Studio.
2. .NET için Aspose.PDF kütüphanesi.

## Adım 1: Proje Kurulumu

Başlamak için Visual Studio'da yeni bir proje oluşturun ve Aspose.PDF for .NET kitaplığına bir referans ekleyin. Kütüphaneyi Aspose resmi web sitesinden indirebilir ve makinenize kurabilirsiniz.

## 2. Adım: Gerekli ad alanlarını içe aktarın

Aspose.PDF tarafından sağlanan sınıflara ve yöntemlere erişmek için gereken ad alanlarını C# kod dosyanıza aktarın:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Adım 3: PDF Belgesi ve Not Yapılandırılmış Öğelerinin Oluşturulması

PDF belgesi oluşturmak ve not yapılandırılmış öğeler eklemek için aşağıdaki kodu kullanın:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample Grade Items");
taggedContent.SetLanguage("fr-FR");

ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);

NoteElement note1 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note1);
note1.SetText("Note with automatically generated ID. ");

NoteElement note2 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note2);
note2.SetText("Note with ID = 'note_002'.");
note2.SetId("note_002");

NoteElement note3 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note3);
note3.SetText("Note with ID = 'note_003'.");
note3.SetId("note_003");
```

Bu kod boş bir PDF belgesi oluşturur ve bir paragrafa yapılandırılmış not öğeleri ekler. Her not Aspose.PDF tarafından sağlanan yöntemler kullanılarak oluşturulur.

## Adım 4: PDF Belgesini Kaydetme

PDF belgesini kaydetmek için aşağıdaki kodu kullanın:

```csharp
document. Save(outFile);
```

Bu kod, not yapılandırılmış öğeleri içeren PDF belgesini belirtilen bir dosyaya kaydeder.

### Aspose.PDF for .NET kullanarak Not Yapısı Öğesi Oluşturma için örnek kaynak kodu 

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
// Pdf Belgesi Oluştur
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
// Paragraf Öğesi Ekle
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
// NoteElement Ekle
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
// NoteElement Ekle
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
// NoteElement Ekle
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
// İstisna oluşturulmalı - Aspose.Pdf.Tagged.TaggedException : ID='note_002' olan yapı öğesi zaten mevcut
//note3.SetId("note_002");
// Ortaya çıkan belge PDF/UA ile uyumlu değil Not Yapısı Öğesi için ClearId() kullanılıyorsa
//note3.ClearId();
// Etiketli Pdf Belgesini Kaydet
document.Save(outFile);
// PDF/UA uyumluluğunu kontrol etme
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Çözüm

Bu eğitimde Aspose.PDF for .NET kullanarak bir PDF belgesinde not yapısı öğelerinin nasıl oluşturulacağını öğrendiniz. Yapılandırılmış not öğeleri, PDF belgenize ek, yapılandırılmış bilgiler eklemenizi sağlar.

### SSS'ler

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesinde not yapısı öğeleri oluşturmanın amacı nedir?

C: Aspose.PDF for .NET kullanarak bir PDF belgesinde not yapısı öğeleri oluşturmak, belgenin içeriğine yapılandırılmış notlar eklemenizi sağlar. Bu notlar, içeriğin belirli bölümlerine ek bağlam, açıklamalar veya referanslar sağlayabilir.

#### S: Aspose.PDF kütüphanesi bir PDF belgesinde not yapısı öğeleri oluşturmaya nasıl yardımcı olur?

C: Aspose.PDF for .NET, PDF belgelerini programlı olarak oluşturmak, değiştirmek ve dönüştürmek için işlevler sağlayan güçlü bir kitaplıktır. Bu eğitimde, kitaplığın işaretli içerik yapısı özellikleri, PDF belgesinin içeriğinde yapılandırılmış not öğeleri oluşturmak için kullanılır.

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesinde not yapısı öğeleri oluşturmanın önkoşulları nelerdir?

C: Başlamadan önce, Visual Studio'nun .NET framework ile kurulu olduğundan ve projenizde .NET için Aspose.PDF kütüphanesinin referans alındığından emin olun.

#### S: Sağlanan C# kodu, PDF belgesinin içeriğinde not yapısı öğelerini nasıl oluşturur?

C: Kod, bir PDF belgesinin nasıl oluşturulacağını, not yapılandırılmış öğelerinin nasıl tanımlanacağını ve bunların bir paragrafa nasıl ekleneceğini gösterir. Her not, Aspose.PDF tarafından sağlanan yöntemler kullanılarak oluşturulur ve yapılandırılmış notları içeriğe dahil etmenize olanak tanır.

#### S: Oluşturduğum not yapısı öğelerinin içeriğini ve özelliklerini özelleştirebilir miyim?

C: Evet, Aspose.PDF kütüphanesinin sağladığı yöntem ve özellikleri kullanarak not yapısı öğelerinin içeriğini ve özelliklerini özelleştirebilirsiniz. Kod, not öğelerinin metninin ve kimliğinin nasıl ayarlanacağını gösterir, ancak bunları gerektiği gibi daha da özelleştirebilirsiniz.

#### S: Not yapısı öğeleri ile belgenin içeriği arasında hiyerarşik ilişki nasıl kuruluyor?

 C: Hiyerarşik ilişki, not yapısı öğelerinin paragraflar gibi diğer yapılandırılmış öğelerin alt öğeleri olarak eklenmesiyle kurulur. Kodda, not öğeleri bir paragraf öğesine şu şekilde eklenir:`AppendChild` yöntem.

#### S: Not yapısı öğelerine benzersiz kimlikler atayabilir miyim?

C: Evet, not yapısı öğelerine benzersiz kimlikler atayabilirsiniz.`SetId` yöntem. Kod, not öğelerinin kimliklerinin benzersiz değerlere nasıl ayarlanacağını gösterir.

#### S: Bir not yapısı öğesine yinelenen bir kimlik atamaya çalışırsam ne olur?

C: Bir not yapısı öğesine yinelenen bir kimlik atamaya çalışmak bir istisnayla sonuçlanacaktır. Öğreticide sağlanan kod, bu senaryoyu gösteren bir açıklama içerir.

#### S: Not yapısı öğeleri oluştururken PDF/UA uyumluluğunu nasıl sağlayabilirim?

 C: Eğitimde sağlanan kod, PDF/UA uyumluluğunun nasıl doğrulanacağını gösterir.`Validate` yöntem. Belgeyi PDF/UA standardına göre doğrulayarak eklenen not yapısı öğelerinin erişilebilirlik yönergelerine uygun olmasını sağlayabilirsiniz.

#### S: Bu yaklaşımı mevcut bir PDF belgesine not yapısı öğeleri eklemek için kullanabilir miyim?

C: Evet, mevcut bir PDF belgesine not yapısı öğeleri eklemek için sağlanan yaklaşımı değiştirebilirsiniz. Yeni bir belge oluşturmak yerine mevcut belgeyi Aspose.PDF kullanarak yükleyebilir ve ardından not öğeleri eklemek için benzer adımları uygulayabilirsiniz.
