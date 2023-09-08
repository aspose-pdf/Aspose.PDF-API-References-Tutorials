---
title: PDF Dosyasına Gizli Metin Ekleme ve Arama
linktitle: PDF Dosyasına Gizli Metin Ekleme ve Arama
second_title: .NET API Referansı için Aspose.PDF
description: Aspose.PDF for .NET kullanarak PDF dosyasına gizli metin ekleme ve arama yapma konusunda adım adım kılavuz.
type: docs
weight: 20
url: /tr/net/programming-with-text/add-and-search-hidden-text/
---
Bu eğitimde, Aspose.PDF for .NET kullanarak PDF dosyasındaki gizli metni nasıl ekleyeceğinizi ve arayacağınızı anlatacağız. Bu işlemi kolayca gerçekleştirmek için aşağıdaki adımları izleyin.

## 1. Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio veya kurulu ve yapılandırılmış başka bir geliştirme ortamı.
- C# programlama dili hakkında temel bilgi.
- .NET için Aspose.PDF kütüphanesi kuruldu. Aspose'un resmi web sitesinden indirebilirsiniz.

## 2. Gizli metin içeren PDF belgesi oluşturma

Başlamak için gizli metin içeren yeni bir PDF belgesi oluşturmak üzere aşağıdaki kodu kullanın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Belge oluştur
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

PDF belgesi için istediğiniz yolu ve dosya adını sağladığınızdan emin olun.

## 3. Belgede metin arayın

Daha sonra PDF belgesindeki gizli metni arayacağız. Aşağıdaki kodu kullanın:

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

Bu, PDF belgesinin ikinci sayfasındaki gizli metni arayacak ve ilgili bilgileri görüntüleyecektir.

### Aspose.PDF for .NET kullanarak Gizli Metin Ekleme ve Arama için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
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
//Belgede metin arayın
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

Tebrikler! Aspose.PDF for .NET'i kullanarak bir PDF belgesine başarıyla eklediniz ve gizli metni buldunuz. Artık PDF dosyalarındaki gizli metni değiştirmek ve aramak için bu yöntemi kendi projelerinize uygulayabilirsiniz.

### SSS'ler

#### S: Aspose.PDF for .NET nedir?

C: Aspose.PDF for .NET, geliştiricilerin .NET uygulamaları içinde PDF belgeleri oluşturmasına, işlemesine ve dönüştürmesine olanak tanıyan güçlü bir kitaplıktır.

#### S: Gizli metin filigran amacıyla kullanılabilir mi?

C: Kesinlikle! Gizli metin, ekstra bir güvenlik katmanı ekleyerek PDF belgelerine filigran eklemenin etkili bir yolu olarak kullanılabilir.

#### S: Bir PDF belgesindeki gizli metni ortaya çıkarmak mümkün müdür?

C: Evet, bir PDF belgesindeki gizli metni arama ve ortaya çıkarma işlemi, bu eğitimde özetlenen teknikler kullanılarak gerçekleştirilebilir.

#### S: Aspose.PDF for .NET başka hangi işlevleri sunuyor?

C: Aspose.PDF for .NET, gizli metin manipülasyonunun ötesinde, PDF oluşturma, dönüştürme, şifreleme ve daha fazlasını içeren çok çeşitli özellikler sunar.