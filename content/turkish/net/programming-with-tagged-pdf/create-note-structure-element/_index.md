---
title: Not Yapısı Elemanı Oluştur
linktitle: Not Yapısı Elemanı Oluştur
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesinde yapılandırılmış not öğeleri oluşturmaya yönelik adım adım kılavuz.
type: docs
weight: 30
url: /tr/net/programming-with-tagged-pdf/create-note-structure-element/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesinde not yapısı öğesinin nasıl oluşturulacağına dair adım adım bir kılavuz sağlayacağız. Aspose.PDF, PDF belgelerini programatik olarak oluşturmanıza, düzenlemenize ve dönüştürmenize olanak tanıyan güçlü bir kütüphanedir. Aspose.PDF'nin işaretli içerik yapısı özelliklerini kullanarak PDF belgenize yapılandırılmış notlar ekleyebilirsiniz.

## Ön koşullar

Başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

1. .NET framework ile Visual Studio kuruldu.
2. .NET için Aspose.PDF kütüphanesi.

## Adım 1: Proje Kurulumu

Başlamak için, Visual Studio'da yeni bir proje oluşturun ve Aspose.PDF for .NET kütüphanesine bir referans ekleyin. Kütüphaneyi Aspose resmi web sitesinden indirebilir ve makinenize kurabilirsiniz.

## Adım 2: Gerekli ad alanlarını içe aktarın

C# kod dosyanıza, Aspose.PDF tarafından sağlanan sınıflara ve yöntemlere erişmek için gereken ad alanlarını içe aktarın:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Adım 3: PDF Belgesini Oluşturma ve Yapılandırılmış Öğeleri Not Etme

Bir PDF belgesi oluşturmak ve not yapılandırılmış öğeler eklemek için aşağıdaki kodu kullanın:

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

### .NET için Aspose.PDF kullanarak Not Yapısı Elemanı Oluşturma için örnek kaynak kodu 

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
// PDF Belgesi Oluştur
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
// Paragraf Öğesi Ekle
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
// NoteElement'i ekle
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
// NoteElement'i ekle
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
// NoteElement'i ekle
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
//İstisna atılmalıdır - Aspose.Pdf.Tagged.TaggedException: ID='note_002' olan yapı öğesi zaten mevcut
//not3.SetId("not_002");
// ClearId() Not Yapı Elemanı için kullanılırsa, ortaya çıkan belge PDF/UA ile uyumlu değildir
//not3.ClearId();
// Etiketli PDF Belgesini Kaydet
document.Save(outFile);
// PDF/UA uyumluluğunun kontrol edilmesi
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Çözüm

Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF belgesinde not yapı öğelerinin nasıl oluşturulacağını öğrendiniz. Yapılandırılmış not öğeleri, PDF belgenize ek, yapılandırılmış bilgiler eklemenize olanak tanır.

### SSS

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesinde not yapı öğeleri oluşturmanın amacı nedir?

A: Aspose.PDF for .NET kullanarak bir PDF belgesinde not yapı öğeleri oluşturmak, belgenin içeriğine yapılandırılmış notlar eklemenize olanak tanır. Bu notlar, içeriğin belirli bölümlerine ek bağlam, açıklamalar veya referanslar sağlayabilir.

#### S: Aspose.PDF kütüphanesi bir PDF belgesinde not yapı öğelerinin oluşturulmasına nasıl yardımcı olur?

A: Aspose.PDF for .NET, PDF belgelerini programatik olarak oluşturma, düzenleme ve dönüştürme işlevleri sağlayan güçlü bir kütüphanedir. Bu eğitimde, kütüphanenin işaretli içerik yapısı özellikleri PDF belgesinin içeriğinde yapılandırılmış not öğeleri oluşturmak için kullanılır.

#### S: Aspose.PDF for .NET kullanarak bir PDF belgesinde not yapı öğeleri oluşturmanın ön koşulları nelerdir?

C: Başlamadan önce, Visual Studio'nun .NET Framework ile birlikte yüklü olduğundan ve projenizde .NET için Aspose.PDF kütüphanesine başvurulduğundan emin olun.

#### S: Sağlanan C# kodu PDF belgesinin içeriğinde not yapı elemanlarını nasıl oluşturur?

A: Kod, bir PDF belgesinin nasıl oluşturulacağını, not yapılandırılmış öğelerin nasıl tanımlanacağını ve bunların bir paragrafa nasıl ekleneceğini gösterir. Her not, Aspose.PDF tarafından sağlanan yöntemler kullanılarak oluşturulur ve yapılandırılmış notları içeriğe dahil etmenize olanak tanır.

#### S: Oluşturduğum not yapı öğelerinin içeriğini ve özelliklerini özelleştirebilir miyim?

C: Evet, Aspose.PDF kütüphanesi tarafından sağlanan yöntemleri ve özellikleri kullanarak not yapı öğelerinin içeriğini ve özelliklerini özelleştirebilirsiniz. Kod, not öğelerinin metninin ve kimliğinin nasıl ayarlanacağını gösterir, ancak bunları gerektiği gibi daha da özelleştirebilirsiniz.

#### S: Not yapı unsurları ile belgenin içeriği arasındaki hiyerarşik ilişki nasıl kurulur?

 A: Hiyerarşik ilişki, paragraflar gibi diğer yapılandırılmış öğelerin çocukları olarak not yapı öğeleri eklenerek kurulur. Kodda, not öğeleri bir paragraf öğesine şu şekilde eklenir:`AppendChild` Yöntem.

#### S: Not yapı elemanlarına benzersiz kimlikler atayabilir miyim?

 A: Evet, not yapı öğelerine benzersiz kimlikler atayabilirsiniz.`SetId` yöntem. Kod, not öğelerinin kimliklerinin benzersiz değerlere nasıl ayarlanacağını gösterir.

#### S: Bir not yapı öğesine yinelenen bir kimlik atamayı denersem ne olur?

A: Bir not yapı öğesine yinelenen bir kimlik atamaya çalışmak bir istisnayla sonuçlanacaktır. Eğitimde sağlanan kod, bu senaryoyu gösteren bir yorum içerir.

#### S: Not yapı öğeleri oluştururken PDF/UA uyumluluğunu nasıl sağlayabilirim?

A: Eğitimde sağlanan kod, PDF/UA uyumluluğunun nasıl doğrulanacağını göstermektedir.`Validate` yöntem. Belgeyi PDF/UA standardına göre doğrulayarak, eklenen not yapı öğelerinin erişilebilirlik yönergelerine uymasını sağlayabilirsiniz.

#### S: Bu yaklaşımı mevcut bir PDF belgesine not yapısı öğeleri eklemek için kullanabilir miyim?

A: Evet, not yapısı öğelerini mevcut bir PDF belgesine eklemek için sağlanan yaklaşımı değiştirebilirsiniz. Yeni bir belge oluşturmak yerine, Aspose.PDF kullanarak mevcut belgeyi yükler ve ardından not öğelerini eklemek için benzer adımları izlersiniz.
