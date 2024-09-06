---
title: PDF Dosyasına Gizli Metin Ekleme ve Arama
linktitle: PDF Dosyasına Gizli Metin Ekleme ve Arama
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak PDF dosyasına gizli metin ekleme ve arama konusunda adım adım kılavuz.
type: docs
weight: 20
url: /tr/net/programming-with-text/add-and-search-hidden-text/
---
Bu eğitimde, .NET için Aspose.PDF kullanarak PDF dosyasına gizli metin ekleme ve arama konusunda size yol göstereceğiz. Bu işlemi kolayca gerçekleştirmek için şu adımları izleyin.

## 1. Ön koşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio veya herhangi bir geliştirme ortamının kurulu ve yapılandırılmış olması.
- C# programlama dilinin temel bilgisi.
- .NET için Aspose.PDF kütüphanesi yüklü. Aspose resmi web sitesinden indirebilirsiniz.

## 2. Gizli metin içeren PDF belgesinin oluşturulması

Başlamak için gizli metin içeren yeni bir PDF belgesi oluşturmak üzere aşağıdaki kodu kullanın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Bir belge oluşturun
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
// Metin özelliğini ayarla - görünmez
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

PDF belgesi için istediğiniz yolu ve dosya adını belirttiğinizden emin olun.

## 3. Belgede metin arayın

Sonra, PDF belgesinde gizli metni arayacağız. Aşağıdaki kodu kullanın:

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
//Parçalarla bir şeyler yapın
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

Bu, PDF belgesinin ikinci sayfasındaki gizli metni arayacak ve ilgili bilgileri gösterecektir.

### .NET için Aspose.PDF kullanarak Gizli Metin Ekleme ve Arama için örnek kaynak kodu 
```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Gizli metin içeren belge oluştur
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//Metin özelliğini ayarla - görünmez
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
//Belgedeki metni ara
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
foreach (TextFragment fragment in absorber.TextFragments)
{
	//Parçalarla bir şeyler yapın
	Console.WriteLine("Text '{0}' on pos {1} invisibility: {2} ",
	fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesine gizli metin eklediniz ve buldunuz. Artık bu yöntemi kendi projelerinize uygulayarak PDF dosyalarındaki gizli metinleri düzenleyebilir ve arayabilirsiniz.

### SSS

#### S: Aspose.PDF for .NET nedir?

C: Aspose.PDF for .NET, geliştiricilerin .NET uygulamaları içerisinde PDF belgeleri oluşturmasını, düzenlemesini ve dönüştürmesini sağlayan güçlü bir kütüphanedir.

#### S: Gizli metin filigranlama amacıyla kullanılabilir mi?

A: Kesinlikle! Gizli metin, PDF belgelerine filigran eklemenin etkili bir yolu olarak hizmet edebilir ve ekstra bir güvenlik katmanı ekleyebilir.

#### S: PDF belgesinde gizli metni ortaya çıkarmak mümkün müdür?

C: Evet, bu eğitimde anlatılan teknikleri kullanarak PDF belgesinde gizli metni arama ve ortaya çıkarma işlemi gerçekleştirilebilir.

#### S: Aspose.PDF for .NET başka hangi işlevleri sunuyor?

A: Gizli metin düzenlemenin ötesinde, Aspose.PDF for .NET, PDF oluşturma, dönüştürme, şifreleme ve daha fazlası dahil olmak üzere çok çeşitli özellikler sunar.