---
title: PDF Dosyasında Gizli Metin Bloğu
linktitle: PDF Dosyasında Gizli Metin Bloğu
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasında gizli metin bloklarının nasıl oluşturulacağını öğrenin.
type: docs
weight: 230
url: /tr/net/programming-with-text/hidden-text-block/
---
Bu eğitimde, .NET için Aspose.PDF kütüphanesini kullanarak PDF dosyasında gizli metin bloğunun nasıl oluşturulacağını açıklayacağız. Gizli metin bloğu, fare imleci belirli bir alanın üzerine geldiğinde görünür hale gelen yüzen bir metindir. Sağlanan C# kaynak kodunu kullanarak gizli metin bloğunu oluşturmanın adım adım sürecini ele alacağız.

## Gereksinimler

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.PDF for .NET kütüphanesi kuruldu.
- C# programlamanın temellerini anlamak.

## Adım 1: Belge Dizinini Ayarlayın

 Öncelikle, oluşturulan PDF dosyasını kaydetmek istediğiniz dizinin yolunu ayarlamanız gerekir. Değiştir`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir` İstediğiniz dizinin yolunu içeren değişken.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Örnek Bir Belge Oluşturun

Bu adımda, örnek bir PDF belgesi oluşturup buna bir metin parçası ekliyoruz. Metin parçası, gizli metin bloğunu görüntülemek için tetikleyici görevi görecektir.

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## Adım 3: Belgeyi açın

 Şimdi, daha önce oluşturulan belgeyi kullanarak açıyoruz`Document` sınıf.

```csharp
Document document = new Document(outputFile);
```

## Adım 4: Metin Parçasını Bulun

 Biz bir kullanıyoruz`TextFragmentAbsorber`Gizli metin bloğunun görüntülenmesini tetikleyecek metin parçasını bulmak için nesne. Bu durumda, "Yüzen metni görüntülemek için fare imlecini buraya taşıyın" metninin tam olarak aynısını arıyoruz.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## Adım 5: Gizli Metin Alanını Oluşturun

 Biz bir tane yaratıyoruz`TextBoxField` Gizli metin alanını temsil eden nesne. Bu alan, fare imleci tetikleyici metnin üzerine geldiğinde görünür hale gelen metni içerecektir.

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

## Adım 6: Gizli Metin Alanını Belgeye Ekleyin

Gizli metin alanını belgenin form koleksiyonuna ekliyoruz.

```csharp
document.Form.Add(floatingField);
```

## Adım 7: Görünmez Düğmeyi Oluşturun

Tetikleyici metin parçasının üstüne konumlandırılacak görünmez bir buton alanı oluşturuyoruz. Bu buton alanı fare giriş ve çıkış olaylarıyla ilişkili eylemlere sahip olacak.

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## Adım 8: Belgeyi Kaydedin

Son olarak değiştirilmiş belgeyi gizli metin bloğuyla birlikte kaydediyoruz.

```csharp
document. Save(outputFile);
```

### .NET için Aspose.PDF kullanılarak Gizli Metin Bloğu için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// Metin içeren örnek belge oluşturun
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// Metin içeren belgeyi aç
Document document = new Document(outputFile);
//Düzenli ifadeyle eşleşen tüm ifadeleri bulmak için TextAbsorber nesnesi oluşturun
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// Belge sayfaları için emiciyi kabul edin
document.Pages.Accept(absorber);
// İlk çıkarılan metin parçasını al
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
//Sayfanın belirtilen dikdörtgeninde yüzen metin için gizli metin alanı oluştur
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// Alan değeri olarak görüntülenecek metni ayarlayın
floatingField.Value = "This is the \"floating text field\".";
// Bu senaryo için alanı 'salt okunur' yapmanızı öneririz
floatingField.ReadOnly = true;
// Belge açıldığında alanı görünmez yapmak için 'gizli' bayrağını ayarlayın
floatingField.Flags |= AnnotationFlags.Hidden;
// Benzersiz bir alan adı belirlemek gerekli değildir ancak izin verilir
floatingField.PartialName = "FloatingField_1";
// Alan görünümünün özelliklerini ayarlamak gerekli değildir ancak daha iyi hale getirir
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// Belgeye metin alanı ekle
document.Form.Add(floatingField);
// Metin parçası konumunda görünmez düğme oluştur
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// Belirtilen alan (açıklama) ve görünmezlik bayrağı için yeni gizleme eylemi oluştur.
// (Yukarıda belirttiyseniz, kayan alana adıyla da başvurabilirsiniz.)
// Görünmez düğme alanına fare girişi/çıkışı sırasında eylemler ekleyin
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// Belgeye düğme alanı ekle
document.Form.Add(buttonField);
// Belgeyi kaydet
document.Save(outputFile);
```

## Çözüm

Bu eğitimde, Aspose.PDF for .NET kütüphanesini kullanarak gizli bir metin bloğu oluşturmayı öğrendiniz. Adım adım kılavuzu izleyerek, fare imleci belirli bir alanın üzerine geldiğinde görünür hale gelen gizli bir metin alanına sahip bir PDF belgesi oluşturabilirsiniz. Gizli metin bloğunun görünümünü ve davranışını gereksinimlerinize göre özelleştirebilirsiniz.

### SSS

#### S: "PDF Dosyasında Gizli Metin Bloğu" eğitiminin amacı nedir?

A: "PDF Dosyasında Gizli Metin Bloğu" öğreticisi, .NET için Aspose.PDF kütüphanesini kullanarak bir PDF dosyasında gizli bir metin bloğunun nasıl oluşturulacağını açıklar. Gizli bir metin bloğu, fare imleci belirli bir alanın üzerine geldiğinde görünür hale gelen yüzen bir metindir. Bu öğretici, C# kaynak kodunu kullanarak adım adım bir kılavuz sağlar.

#### S: Neden bir PDF dosyasında gizli bir metin bloğu oluşturmak isteyeyim?

A: Gizli bir metin bloğu oluşturmak, yalnızca kullanıcının fare imlecini belirli bir alanın üzerine getirdiğinde görünür hale gelen ek bilgi veya bağlam sağlamak istediğiniz etkileşimli PDF belgeleri için yararlı olabilir.

#### S: Belge dizinini nasıl ayarlarım?

A: Belge dizinini ayarlamak için:

1.  Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir` Oluşturulan PDF dosyasını kaydetmek istediğiniz dizinin yolunu içeren değişken.

#### S: Örnek bir belge nasıl oluşturabilirim ve buna bir metin parçası nasıl ekleyebilirim?

 A: Eğitimde şunu kullanıyorsunuz:`Document` Bir örnek PDF belgesi oluşturmak ve bir metin parçası eklemek için sınıf. Bu metin parçası, gizli metin bloğunu görüntülemek için tetikleyici görevi görür.

#### S: Gizli metin bloğunu tetikleyen metin parçasını nasıl bulabilirim?

 A: Eğitimde bir`TextFragmentAbsorber` Gizli metin bloğunun görüntülenmesini tetikleyen metin parçasını bulmak için nesne. PDF belgesi içinde belirli bir metin dizesini arar.

#### S: Gizli metin alanını nasıl oluşturabilir ve özelleştirebilirim?

 A: Sen bir tane yarat`TextBoxField`Gizli metin alanını temsil eden nesne. Eğitim, gizli metin alanının konumu, değeri, görünümü ve davranışı gibi çeşitli özellikleri ayarlamak için kod sağlar.

#### S: Gizli metin bloğuyla ilişkili görünmez bir düğme nasıl oluştururum?

 A: Görünmez bir düğme alanı, şunu kullanarak oluşturulur:`ButtonField` sınıf. Bu düğme alanı tetikleyici metin parçasının üstünde konumlandırılmıştır ve fare giriş ve çıkış olaylarıyla ilişkili eylemlere sahiptir. Bu eylemler gizli metin bloğunun görünürlüğünü kontrol eder.

#### S: Gizli metin bloğunun ve tetikleyici alanının görünümünü özelleştirebilir miyim?

C: Evet, hem gizli metin alanının hem de görünmez butonun yazı tipi, rengi, boyutu ve konumu gibi çeşitli özelliklerini özelleştirebilirsiniz.

#### S: Gizli metin bloğuyla değiştirilen belgeyi nasıl kaydederim?

 A: Eğitimde, değiştirilen belgenin nasıl kaydedileceği gösterilmektedir.`Save` yöntemi`Document` sınıf.