---
title: Gizli Metin Ekle ve Ara
linktitle: Gizli Metin Ekle ve Ara
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesine gizli metin eklemek ve aramak için adım adım kılavuz.
type: docs
weight: 20
url: /tr/net/programming-with-text/add-and-search-hidden-text/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesine nasıl gizli metin ekleyeceğinizi ve bu metni nasıl arayacağınızı göstereceğiz. Bu işlemi kolayca gerçekleştirmek için aşağıdaki adımları izleyin.

## 1. Önkoşullar

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Visual Studio veya kurulu ve yapılandırılmış başka bir geliştirme ortamı.
- C# programlama dili hakkında temel bilgi.
- Aspose.PDF kitaplığı for .NET kurulu. Aspose resmi sitesinden indirebilirsiniz.

## 2. PDF belgesini gizli metinle oluşturma

Başlamak için, gizli metin içeren yeni bir PDF belgesi oluşturmak üzere aşağıdaki kodu kullanın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Bir belge oluştur
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

PDF belgesi için istenen yolu ve dosya adını sağladığınızdan emin olun.

## 3. Belgede metin arayın

Ardından, PDF belgesindeki gizli metni arayacağız. Aşağıdaki kodu kullanın:

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
//Parçalarla bir şeyler yap
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

Bu, PDF belgesinin ikinci sayfasındaki gizli metni arayacak ve ilgili bilgileri gösterecektir.

### Aspose.PDF for .NET kullanarak Add And Search Hidden Text için örnek kaynak kodu 
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
//Belgede metin ara
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
foreach (TextFragment fragment in absorber.TextFragments)
{
	//Parçalarla bir şeyler yap
	Console.WriteLine("Text '{0}' on pos {1} invisibility: {2} ",
	fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

## Çözüm

Tebrikler! Aspose.PDF for .NET'i kullanarak bir PDF belgesine gizli metni başarıyla eklediniz ve buldunuz. Artık PDF dosyalarındaki gizli metinleri değiştirmek ve aramak için bu yöntemi kendi projelerinize uygulayabilirsiniz.