---
title: Not Yapısı Elemanı Oluştur
linktitle: Not Yapısı Elemanı Oluştur
second_title: Aspose.PDF for .NET API Referansı
description: Bu ayrıntılı, adım adım eğitimle Aspose.PDF for .NET ile PDF'lerde not yapı öğeleri oluşturmayı öğrenin.
type: docs
weight: 30
url: /tr/net/programming-with-tagged-pdf/create-note-structure-element/
---
## giriiş

Günümüzün dijital dünyasında, özellikle PDF'lerle uğraşırken, yapılandırılmış belgeler oluşturmak esastır. Belge erişilebilirliği söz konusu olduğunda, .NET için Aspose.PDF kitaplığı, geliştiricilerin PDF içeriğini sorunsuz bir şekilde yönetmesine yardımcı olan güçlü bir araçtır. Bu eğitimde, .NET için Aspose.PDF kullanarak bir PDF içinde not yapı öğelerinin nasıl oluşturulacağını derinlemesine inceleyeceğiz. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu kılavuz sizi her adımda konuşma dilinde, anlaşılması kolay bir şekilde yönlendirecektir. Hadi başlayalım!

## Ön koşullar

Kodlamaya ve not yapı öğelerini oluşturmaya başlamadan önce, ihtiyacınız olan her şeyin hazır olduğundan emin olalım:

1. .NET Ortamı: Visual Studio gibi bir .NET geliştirme ortamınız olmalıdır.
2.  Aspose.PDF Kütüphanesi: Aspose.PDF kütüphanesini indirip yüklemeniz gerekecek. Bunu şuradan alabilirsiniz:[Burada](https://releases.aspose.com/pdf/net/).
3. Temel C# Bilgisi: Bu eğitimden en iyi şekilde faydalanmak için C# programlamaya aşinalık gereklidir.
4. .NET Framework'e Erişim: Projenizin .NET Framework'ün uyumlu bir sürümünü hedeflediğinden emin olun.
5. Belge Dizini: PDF ve günlük dosyalarınızı depolamak için bir dizin ayarlayın. 

Her şey hazır mı? Harika! Hadi kodlara geçelim!

## Paketleri İçe Aktar

İlk adım gerekli paketleri içe aktarmaktır. Bu, geliştirme ortamınızda yapılabilir. Bunu yapmanın basit bir yolu şudur:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Bu ad alanları, PDF belgelerini oluşturmak ve düzenlemek için gereken sınıflara ve yöntemlere erişim sağlar.

## Adım 1: Belgeyi Ayarlama

Başlamak için yeni bir belge örneği oluşturmanız gerekir. Bu, oluşturmak istediğiniz herhangi bir PDF'nin başlangıç noktasıdır. Bunu şu şekilde yaparsınız:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";

// PDF Belgesi Oluştur
Document document = new Document();
```
Bu kod yeni bir kod başlatır`Document` nesne ve çıktı PDF ve günlük dosyaları için dosya yollarını ayarlar. Değiştirdiğinizden emin olun`"YOUR DOCUMENT DIRECTORY"` gerçek dizin yolunuzla.

## Adım 2: Etiketli İçerik Niteliklerini Ayarlama

Şimdi, PDF'niz için etiketli içeriği ayarlamaya geçelim. Bu, başlık ve dil niteliklerini tanımlamayı içerir.

```csharp
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
```
 Burada, şuraya erişiyoruz:`TaggedContent` Belgenin başlığını ve dilini ayarlamak. Bu, erişilebilirlik standartları için önemlidir ve belgenize daha profesyonel bir dokunuş kazandırır.

## Adım 3: Bir Paragraf Öğesi Oluşturma

Şimdi, etiketli içeriğe bir paragraf öğesi ekleyeceğiz. Bu, notlarınız için bir kapsayıcı görevi görecek.

```csharp
// Paragraf Öğesi Ekle
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
```
 Bir tane oluşturarak`ParagraphElement`, not öğelerinin ekleneceği bir temel sağlıyoruz. Duvarları inşa etmeden önce bir evin temelini atmaya benzer.

## Adım 4: Not Öğelerinin Eklenmesi

Şimdi eğlenceli kısım: not öğeleri ekleme! Birden fazla not oluşturabilirsiniz—hadi bunu üç adımda yapalım!

### Adım 4.1: İlk Notu Ekleyin

```csharp
// NoteElement'i ekle
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID.");
```
Bu kod otomatik olarak oluşturulmuş bir ID ile ilk notu oluşturur. Önceki paragrafımıza içerik eklemenin ne kadar kolay olduğuna dikkat edin.

### Adım 4.2: İkinci Notayı Ekleyin

```csharp
// NoteElement'i ekle
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
```
 İkinci not için açıkça bir kimlik belirledik`note_002`. Kimliklere dikkat etmek önemlidir çünkü bunlar daha sonra belirli notlara başvurmanın bir yolunu sağlar.

### Adım 4.3: Üçüncü Notu Ekleyin

```csharp
// NoteElement'i ekle
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
// İstisna atılmalıdır - Aspose.Pdf.Tagged.TaggedException: ID='note_002' olan yapı öğesi zaten mevcut
```
 Bu üçüncü not ikincisine çok benzer ancak başka bir benzersiz kimlik kullanır. Dikkatli olun; aynı kimliğe sahip başka bir not oluşturmaya çalışmak`note_002` bir istisna fırlatacaktır. 

## Adım 5: Belgeyi Kaydetme

Notlarınız eklendikten sonra, belgeyi kaydetme zamanı geldi!

```csharp
// Etiketli PDF Belgesini Kaydet
document.Save(outFile);
```
Bu basit satır tüm emeklerinizi belirtilen PDF dosyasına kaydeder. 

## Adım 6: PDF/UA Uyumluluğunu Doğrulayın

Belgenizin erişilebilirlik standartlarını karşıladığından emin olmak için onu doğrulayabilirsiniz.

```csharp
// PDF/UA uyumluluğunun kontrol edilmesi
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```
Bu kod parçası PDF'nizi PDF/UA (Evrensel Erişilebilirlik) standardına göre kontrol eder. Uyumluluğu belirten bir boole değeri alacaksınız!

## Çözüm

İşte oldu! Artık .NET için Aspose.PDF sayesinde daha iyi erişilebilirlik ve yapı sağlayan bir PDF belgesi içinde not yapısı öğelerini başarıyla oluşturdunuz! Bu adımları izleyerek PDF'lerinizi daha verimli bir şekilde yönetebilir ve daha kullanıcı dostu hale getirebilirsiniz. 

## SSS

### PDF'lerde not yapı öğeleri nelerdir?
Not öğeleri, PDF'in belirli bölümlerine eklenen, netliği ve anlaşılırlığı artıran açıklamalar veya yorumlardır.

### Aspose.PDF for .NET ücretsiz mi?
Ücretsiz deneme imkânı sunmasına rağmen Aspose.PDF ticari bir üründür; fiyatları kullanımınıza ve ihtiyaç duyduğunuz özelliklere göre değişmektedir.

### Aspose.PDF ile başka türde öğeler oluşturabilir miyim?
Evet! Aspose.PDF belgelerinizi zenginleştirmek için resim, tablo ve köprü metni gibi çok sayıda öğeyi destekler.

### PDF/UA uyumluluğu nedir?
PDF/UA uyumluluğu, PDF'lerin küresel standartlarla uyumlu olacak şekilde engelli bireyler tarafından erişilebilir olmasını sağlar.

### Aspose.PDF için desteği nereden alabilirim?
 Destek için şu adresi ziyaret edin:[Aspose forumu](https://forum.aspose.com/c/pdf/10) Sorularınızı sorabileceğiniz ve deneyimlerinizi paylaşabileceğiniz bir yer.