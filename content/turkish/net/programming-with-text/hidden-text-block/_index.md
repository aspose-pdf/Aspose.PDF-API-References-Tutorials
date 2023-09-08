---
title: PDF Dosyasındaki Gizli Metin Bloğu
linktitle: PDF Dosyasındaki Gizli Metin Bloğu
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF dosyasında gizli metin bloklarının nasıl oluşturulacağını öğrenin.
type: docs
weight: 230
url: /tr/net/programming-with-text/hidden-text-block/
---
Bu eğitimde, .NET için Aspose.PDF kütüphanesini kullanarak PDF dosyasında gizli bir metin bloğunun nasıl oluşturulacağını açıklayacağız. Gizli metin bloğu, fare imleci belirli bir alanın üzerine geldiğinde görünür hale gelen kayan bir metindir. Sağlanan C# kaynak kodunu kullanarak gizli metin bloğunu oluşturma işlemini adım adım gerçekleştireceğiz.

## Gereksinimler

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Aspose.PDF for .NET kütüphanesi kuruldu.
- C# programlamanın temel anlayışı.

## 1. Adım: Belge Dizinini Ayarlayın

 Öncelikle oluşturulan PDF dosyasını kaydetmek istediğiniz dizinin yolunu ayarlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir`İstediğiniz dizinin yolunu içeren değişken.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Örnek Belge Oluşturun

Bu adımda örnek bir PDF belgesi oluşturup ona bir metin parçası ekliyoruz. Metin parçası, gizli metin bloğunun görüntülenmesi için tetikleyici görevi görecektir.

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## 3. Adım: Belgeyi Açın

 Şimdi daha önce oluşturduğumuz belgeyi kullanarak açıyoruz.`Document` sınıf.

```csharp
Document document = new Document(outputFile);
```

## 4. Adım: Metin Parçasını Bulun

 Bir kullanıyoruz`TextFragmentAbsorber` Gizli metin bloğunun görüntülenmesini tetikleyecek metin parçasını bulmak için nesneyi kullanın. Bu durumda, "Kayan metni görüntülemek için fare imlecini buraya taşıyın" metnini arıyoruz.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## Adım 5: Gizli Metin Alanını Oluşturun

 Biz bir yaratıyoruz`TextBoxField` gizli metin alanını temsil edecek nesne. Bu alan, fare imleci tetikleyici metnin üzerine geldiğinde görünür hale gelen metni içerecektir.

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

## Adım 6: Gizli Metin Alanını Belgeye Ekleme

Gizli metin alanını belgenin form koleksiyonuna ekliyoruz.

```csharp
document.Form.Add(floatingField);
```

## Adım 7: Görünmez Düğmeyi Oluşturun

Tetikleyici metin parçasının üstüne yerleştirilecek görünmez bir buton alanı oluşturuyoruz. Bu düğme alanı, fareye giriş ve çıkış olaylarıyla ilişkili eylemlere sahip olacaktır.

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## Adım 8: Belgeyi Kaydedin

Son olarak değiştirilen belgeyi gizli metin bloğuyla kaydediyoruz.

```csharp
document. Save(outputFile);
```

### Aspose.PDF for .NET kullanan Gizli Metin Bloğu için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// Metin içeren örnek belge oluşturun
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// Metin içeren belgeyi aç
Document document = new Document(outputFile);
// Normal ifadeyle eşleşen tüm ifadeleri bulmak için TextAbsorber nesnesi oluşturun
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// Belge sayfaları için emiciyi kabul edin
document.Pages.Accept(absorber);
// Çıkarılan ilk metin parçasını alın
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
// Sayfanın belirtilen dikdörtgeninde kayan metin için gizli metin alanı oluşturun
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// Alan değeri olarak görüntülenecek metni ayarlayın
floatingField.Value = "This is the \"floating text field\".";
// Bu senaryo için alanı 'salt okunur' yapmanızı öneririz
floatingField.ReadOnly = true;
// Alanı belge açılışında görünmez hale getirmek için 'gizli' bayrağını ayarlayın
floatingField.Flags |= AnnotationFlags.Hidden;
// Benzersiz bir alan adı ayarlamak gerekli değildir ancak buna izin verilir
floatingField.PartialName = "FloatingField_1";
// Alan görünümünün özelliklerini ayarlamak gerekli değildir ancak daha iyi hale getirir
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// Belgeye metin alanı ekleme
document.Form.Add(floatingField);
// Metin parçası konumunda görünmez düğme oluşturun
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// Belirtilen alan (açıklama) ve görünmezlik bayrağı için yeni gizleme eylemi oluşturun.
//(Yukarıda belirttiyseniz, kayan alana ismiyle de başvurabilirsiniz.)
// Görünmez düğme alanına fare giriş/çıkış işlemlerine eylemler ekleyin
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// Belgeye düğme alanı ekleyin
document.Form.Add(buttonField);
// Belgeyi kaydet
document.Save(outputFile);
```

## Çözüm

Bu eğitimde Aspose.PDF for .NET kütüphanesini kullanarak gizli bir metin bloğunun nasıl oluşturulacağını öğrendiniz. Adım adım kılavuzu izleyerek, fare imleci belirli bir alanın üzerine geldiğinde görünür hale gelen gizli metin alanına sahip bir PDF belgesi oluşturabilirsiniz. Gizli metin bloğunun görünümünü ve davranışını gereksinimlerinize göre özelleştirebilirsiniz.

### SSS'ler

#### S: "PDF Dosyasındaki Gizli Metin Bloğu" eğitiminin amacı nedir?

C: "PDF Dosyasında Gizli Metin Bloğu" eğitiminde, .NET için Aspose.PDF kütüphanesini kullanarak bir PDF dosyasında gizli metin bloğunun nasıl oluşturulacağı açıklanmaktadır. Gizli metin bloğu, fare imleci belirli bir alanın üzerine geldiğinde görünür hale gelen kayan bir metindir. Bu öğretici, C# kaynak kodunu kullanan adım adım bir kılavuz sağlar.

#### S: Bir PDF dosyasında neden gizli bir metin bloğu oluşturmak isteyeyim?

C: Gizli bir metin bloğu oluşturmak, yalnızca kullanıcı fare imlecini belirlenmiş bir alanın üzerine getirdiğinde görünür hale gelen ek bilgi veya bağlam sağlamak istediğiniz etkileşimli PDF belgeleri için yararlı olabilir.

#### S: Belge dizinini nasıl ayarlarım?

C: Belge dizinini ayarlamak için:

1.  Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` içinde`dataDir` oluşturulan PDF dosyasını kaydetmek istediğiniz dizinin yolunu içeren değişken.

#### S: Örnek bir belgeyi nasıl oluşturabilirim ve ona bir metin parçasını nasıl eklerim?

C: Eğitimde şunları kullanacaksınız:`Document` Örnek bir PDF belgesi oluşturmak ve bir metin parçası eklemek için sınıfı kullanın. Bu metin parçası, gizli metin bloğunun görüntülenmesi için tetikleyici görevi görür.

#### S: Gizli metin bloğunu tetikleyen metin parçasını nasıl bulurum?

 C: Eğitimde bir uygulamanın nasıl kullanılacağı gösterilmektedir.`TextFragmentAbsorber` Gizli metin bloğunun görüntülenmesini tetikleyen metin parçasını bulmak için nesneyi kullanın. PDF belgesinde belirli bir metin dizesini arar.

#### S: Gizli metin alanını nasıl oluşturup özelleştirebilirim?

 C: Siz bir`TextBoxField` gizli metin alanını temsil edecek nesne. Öğretici, gizli metin alanının konumu, değeri, görünümü ve davranışı gibi çeşitli özellikleri ayarlamak için kod sağlar.

#### S: Gizli metin bloğuyla ilişkili görünmez bir düğmeyi nasıl oluşturabilirim?

 C: Görünmez bir düğme alanı kullanılarak oluşturulur.`ButtonField` sınıf. Bu düğme alanı, tetikleyici metin parçasının üstünde konumlandırılmıştır ve fareye giriş ve çıkış olaylarıyla ilişkili eylemleri içerir. Bu eylemler gizli metin bloğunun görünürlüğünü kontrol eder.

#### S: Gizli metin bloğunun ve tetikleyici alanın görünümünü özelleştirebilir miyim?

C: Evet, hem gizli metin alanının hem de görünmez düğmenin yazı tipi, renk, boyut ve konumlandırma gibi çeşitli özelliklerini özelleştirebilirsiniz.

#### S: Değiştirilen belgeyi gizli metin bloğuyla nasıl kaydederim?

 C: Eğitimde, değiştirilen belgenin aşağıdaki komut kullanılarak nasıl kaydedileceği gösterilmektedir:`Save` yöntemi`Document` sınıf.