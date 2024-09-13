---
title: PDF Dosya İmzası Kullanarak Akıllı Kartla İmzalayın
linktitle: PDF Dosya İmzası Kullanarak Akıllı Kartla İmzalayın
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET ile akıllı kart kullanarak PDF dosyalarını nasıl imzalayacağınızı öğrenin. Güvenli dijital imzalar için bu adım adım kılavuzu izleyin.
type: docs
weight: 110
url: /tr/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
## giriiş

Dijital çağda, belgeleri güvence altına almak her zamankinden daha önemlidir. İster bir sözleşme, ister bir anlaşma veya herhangi bir hassas bilgi olsun, belgenin gerçek olduğundan ve kurcalanmadığından emin olmak çok önemlidir. Dijital imzalar devreye giriyor! Bugün, .NET için Aspose.PDF ile akıllı kart kullanarak bir PDF dosyasını nasıl imzalayacağımızı inceleyeceğiz. Bu güçlü kitaplık, geliştiricilerin güvenli dijital imzalar eklemek de dahil olmak üzere PDF belgelerini etkili bir şekilde düzenlemelerine ve oluşturmalarına olanak tanır. O halde akıllı kartınızı alın ve başlayalım!

## Ön koşullar

PDF dosyasını imzalamanın inceliklerine dalmadan önce, ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım. İşte hazırlanmanıza yardımcı olacak bir kontrol listesi:

1.  .NET için Aspose.PDF: Aspose.PDF kütüphanesinin yüklü olduğundan emin olun. Bunu şuradan indirebilirsiniz:[alan](https://releases.aspose.com/pdf/net/).
2. Visual Studio: .NET kodlarınızı yazıp çalıştırabileceğiniz bir geliştirme ortamı.
3. Akıllı Kart: Geçerli bir dijital sertifikaya sahip akıllı karta ihtiyacınız olacak.
4. C# Temel Anlayışı: Bu dilde kod parçacıkları yazacağımız için C# programlamaya aşina olmak faydalı olacaktır.
5. PDF Belgesi: Örnek bir PDF dosyası (örneğin`blank.pdf`) İmzalama sürecimizi test etmek için.

Bu ön koşullar sağlandığında, koda dalmaya hazırsınız!

## Paketleri İçe Aktar

İlk önce gerekli paketleri içe aktaralım. Projenizde Aspose.PDF kütüphanesine referanslar eklemeniz gerekecek. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

1. Visual Studio’yu açın.
2. Yeni bir proje oluşturun veya mevcut bir projeyi açın.
3.  Çözüm Gezgini'nde projenize sağ tıklayın ve şunu seçin:`Manage NuGet Packages`.
4.  Arama`Aspose.PDF` ve en son sürümü yükleyin.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Artık gerekli paketleri içe aktardığımıza göre, kodu adım adım parçalayalım.

## Adım 1: Belgenizi Ayarlayın

Sürecimizin ilk adımı imzalamak istediğimiz PDF belgesini ayarlamaktır. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
```
 Bu kod parçacığında, belgeler dizinimize giden yolu tanımlıyoruz ve bir örnek oluşturuyoruz`Document` adlı bir örnek PDF dosyası kullanan sınıf`blank.pdf` . Değiştirdiğinizden emin olun`"YOUR DOCUMENTS DIRECTORY"` PDF'inizin bulunduğu gerçek yol ile.

## Adım 2: PdfFileSignature'ı Başlatın

 Daha sonra, şunu başlatacağız:`PdfFileSignature` İmzalama sürecini yönetmekten sorumlu sınıf.

```csharp
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
    pdfSign.BindPdf(doc);
```
Burada, bir örnek oluşturuyoruz`PdfFileSignature`ve bunu PDF belgemize bağlayalım. Bu, belgeyi imzalamaya hazırlar.

## Adım 3: Akıllı Kart Sertifikasına Erişim

Şimdi kritik kısım geliyor: akıllı kartınızda saklanan dijital sertifikaya erişim. Bunu şu şekilde yapabiliriz:

### Sertifika Deposunu açın

```csharp
System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
```
Mevcut kullanıcının profilinde bulunan sertifika deposunu açıyoruz. Bu, akıllı kartınızdakiler de dahil olmak üzere makinenize yüklenen sertifikalara erişmemizi sağlar.

### Sertifikayı seçin

```csharp
System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel =
    System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(
        store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
```
Bu kod kullanıcıdan koleksiyondan bir sertifika seçmesini ister. Kullanıcı arayüzü tüm kullanılabilir sertifikaları görüntüler ve akıllı kartınızla ilişkili olanı seçmenize olanak tanır.

## Adım 4: Harici İmzayı Oluşturun

Sertifikanızı seçtikten sonraki adım, seçilen sertifikayı kullanarak harici bir imza oluşturmaktır.

```csharp
Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
```
Burada, bir örnek oluşturuyoruz`ExternalSignature` seçili sertifikayı kullanarak. Bu nesne PDF belgesini imzalamak için kullanılacaktır.

## Adım 5: İmza Görünümünü Ayarlayın

Şimdi imzamızın görünümünü ayarlayalım. İmzanızın belgede nasıl görüneceğini özelleştirebileceğiniz yer burasıdır.

```csharp
pdfSign.SignatureAppearance = dataDir + "demo.png";
```
 Bu kod parçacığında, bir resim dosyasına (bir logo veya imza grafiği gibi) giden yolu sağlayarak imzanın görünümünü belirtiyoruz. Değiştirdiğinizden emin olun`"demo.png"` kullanmak istediğiniz gerçek görüntü ile.

## Adım 6: PDF'yi imzalayın

Her şey tamamsa, artık PDF belgesini imzalamanın zamanı geldi!

```csharp
pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
pdfSign.Save(dataDir + "externalSignature2.pdf");
```
Bu adımda şunu çağırıyoruz:`Sign` yöntemimiz`pdfSign` nesne. Her parametrenin anlamı şu şekildedir:
- `1`: İmzanın yer alacağı sayfa numarası.
- `"Reason"`: Belgenin imzalanma sebebi.
- `"Contact"`: İmzalayanın iletişim bilgileri.
- `"Location"`: İmzalayanın yeri.
- `true`: Görünür bir imza oluşturulup oluşturulmayacağını belirtir.
- `new System.Drawing.Rectangle(100, 100, 200, 200)`: PDF'deki imzanın konumu ve boyutu.
- `externalSignature`: Daha önce oluşturduğumuz imza nesnesi.

 Son olarak imzalanmış belgeyi şu şekilde kaydediyoruz:`externalSignature2.pdf`.

## Adım 7: İmzayı Doğrulayın

Belgeyi imzaladıktan sonra imzanın geçerli olduğunu doğrulamak önemlidir. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

### Doğrulama İşlemini Başlat

```csharp
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
    IList<string> sigNames = pdfSign.GetSignNames();
```
 Yeni bir örnek oluşturuyoruz`PdfFileSignature` imzalanmış belge için. Daha sonra belgede bulunan tüm imzaların isimlerini alırız.

### İmzanın Geçerliliğini Kontrol Et

```csharp
for (int index = 0; index <= sigNames.Count - 1; index++)
{
    if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
    {
        throw new ApplicationException("Not verified");
    }
}
```
Her imza adının üzerinden geçeriz ve geçerliliğini doğrularız. Herhangi bir imza doğrulamada başarısız olursa, imzanın geçerli olmadığını belirten bir istisna atılır.

## Çözüm

Ve işte karşınızda! Aspose.PDF for .NET ile akıllı kart kullanarak bir PDF belgesini başarıyla imzaladınız. Bu işlem yalnızca belgenizi güvence altına almakla kalmaz, aynı zamanda günümüzün dijital dünyasında önemli olan bir özgünlük katmanı da ekler. İster sözleşmelerle, ister yasal belgelerle veya herhangi bir hassas bilgiyle uğraşıyor olun, dijital imzaların nasıl uygulanacağını bilmek değerli bir beceridir. 

## SSS

### Aspose.PDF for .NET nedir?
Aspose.PDF for .NET, geliştiricilerin .NET uygulamaları içerisinde PDF belgeleri oluşturmalarına, düzenlemelerine ve dönüştürmelerine olanak tanıyan güçlü bir kütüphanedir.

### PDF'leri imzalamak için akıllı karta ihtiyacım var mı?
Akıllı kart zorunlu olmasa da güvenli dijital imzalar için ekstra bir güvenlik katmanı sağladığı için şiddetle tavsiye edilir.

### İmzalamak için herhangi bir PDF dosyasını kullanabilir miyim?
Evet, herhangi bir PDF dosyasını kullanabilirsiniz, ancak parola korumalı olmadığından emin olun. Eğer öyleyse, önce kilidini açmanız gerekir.

### Dijital sertifikam yoksa ne olur?
Güvenilir bir sertifika yetkilisinden (CA) dijital sertifika alabilir veya test amaçlı kendi kendine imzalı bir sertifika kullanabilirsiniz.

### Aspose.PDF'in deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünü şu adresten indirebilirsiniz:[Aspose web sitesi](https://releases.aspose.com/).