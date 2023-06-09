---
title: Gizli Metin Bloğu
linktitle: Gizli Metin Bloğu
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF'de gizli metin bloklarını nasıl oluşturacağınızı öğrenin.
type: docs
weight: 230
url: /tr/net/programming-with-text/hidden-text-block/
---

Bu eğitimde, Aspose.PDF kütüphanesini kullanarak .NET için gizli bir metin bloğunun nasıl oluşturulacağını açıklayacağız. Gizli metin bloğu, fare imleci belirli bir alanın üzerine geldiğinde görünür hale gelen kayan bir metindir. Sağlanan C# kaynak kodunu kullanarak gizli metin bloğu oluşturma sürecini adım adım inceleyeceğiz.

## Gereksinimler

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.PDF for .NET kitaplığı yüklendi.
- Temel bir C# programlama anlayışı.

## 1. Adım: Belge Dizinini kurun

 Öncelikle, oluşturulan PDF dosyasını kaydetmek istediğiniz dizinin yolunu belirlemeniz gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir` istediğiniz dizinin yolu ile değişken.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Örnek Bir Belge Oluşturun

Bu adımda örnek bir PDF belgesi oluşturuyoruz ve buna bir metin parçası ekliyoruz. Metin parçası, gizli metin bloğunu görüntülemek için tetik görevi görecektir.

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## 3. Adım: Belgeyi Açın

 Şimdi, daha önce oluşturulan belgeyi kullanarak açıyoruz.`Document` sınıf.

```csharp
Document document = new Document(outputFile);
```

## 4. Adım: Metin Parçasını Bulun

 biz bir`TextFragmentAbsorber` gizli metin bloğunun görüntülenmesini tetikleyecek metin parçasını bulmak için nesne. Bu durumda, tam olarak "Kayan metni görüntülemek için fare imlecini buraya getirin" metnini arıyoruz.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## 5. Adım: Gizli Metin Alanını Oluşturun

 biz bir yaratırız`TextBoxField`gizli metin alanını temsil eden nesne. Bu alan, fare imleci tetikleyici metnin üzerine geldiğinde görünür hale gelen metni içerecektir.

```csharp
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
floatingField.Value = "This is the \"floating text field\".";
floatingField. ReadOnly = true;
floatingField.Flags |= AnnotationFlags.Hidden;
floatingField.PartialName = "FloatingField_1";
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField. Multiline = true;
```

## 6. Adım: Gizli Metin Alanını Belgeye Ekleyin

Gizli metin alanını belgenin form koleksiyonuna ekliyoruz.

```csharp
document.Form.Add(floatingField);
```

## 7. Adım: Görünmez Düğmeyi Oluşturun

Tetikleyici metin parçasının üstüne konumlanacak görünmez bir düğme alanı oluşturuyoruz. Bu düğme alanı, fare giriş ve çıkış olaylarıyla ilişkili eylemlere sahip olacaktır.

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## 8. Adım: Belgeyi Kaydedin

Son olarak, değiştirilen belgeyi gizli metin bloğu ile kaydediyoruz.

```csharp
document. Save(outputFile);
```

### Aspose.PDF for .NET kullanan Hidden Text Block için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// Metin içeren örnek belge oluşturun
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// Belgeyi metinle aç
Document document = new Document(outputFile);
// Normal ifadeyle eşleşen tüm ifadeleri bulmak için TextAbsorber nesnesi oluşturun
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// Belge sayfaları için emiciyi kabul edin
document.Pages.Accept(absorber);
// Ayıklanan ilk metin parçasını alın
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
// Sayfanın belirtilen dikdörtgeninde kayan metin için gizli metin alanı oluşturun
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// Alan değeri olarak görüntülenecek metni ayarla
floatingField.Value = "This is the \"floating text field\".";
// Bu senaryo için alanı 'salt okunur' yapmanızı öneririz.
floatingField.ReadOnly = true;
// Belge açılışında alanı görünmez yapmak için 'gizli' bayrağını ayarlayın
floatingField.Flags |= AnnotationFlags.Hidden;
//Benzersiz bir alan adı ayarlamak gerekli değildir ancak buna izin verilir
floatingField.PartialName = "FloatingField_1";
// Alan görünümünün özelliklerini ayarlamak gerekli değildir, ancak daha iyi hale getirir
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// Belgeye metin alanı ekleyin
document.Form.Add(floatingField);
//Metin parçası konumunda görünmez düğme oluştur
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// Belirtilen alan (açıklama) ve görünmezlik bayrağı için yeni gizleme eylemi oluşturun.
// (Yukarıda belirttiyseniz, kayan alana da ada göre başvurabilirsiniz.)
// Görünmez düğme alanına fare giriş/çıkış işlemleri ekleyin
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// Belgeye düğme alanı ekle
document.Form.Add(buttonField);
// Belgeyi kaydet
document.Save(outputFile);
```

## Çözüm

Bu öğreticide, Aspose.PDF for .NET kitaplığını kullanarak nasıl gizli bir metin bloğu oluşturacağınızı öğrendiniz. Adım adım kılavuzu izleyerek, fare imleci belirli bir alanın üzerine geldiğinde görünür hale gelen gizli bir metin alanına sahip bir PDF belgesi oluşturabilirsiniz. Gizli metin bloğunun görünümünü ve davranışını gereksinimlerinize göre özelleştirebilirsiniz.