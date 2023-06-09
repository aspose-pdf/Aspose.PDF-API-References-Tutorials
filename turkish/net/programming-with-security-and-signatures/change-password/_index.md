---
title: Şifre değiştir
linktitle: Şifre değiştir
second_title: Aspose.PDF for .NET API Referansı
description: Aspose.PDF for .NET kullanarak bir PDF belgesinin şifresini nasıl değiştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-security-and-signatures/change-password/
---

Bu eğitimde, Aspose.PDF for .NET kullanarak bir PDF belgesinin şifresini değiştirme sürecinde size rehberlik edeceğiz. Kitaplık, mevcut bir PDF dosyasını açmanıza, parolasını değiştirmenize ve güncellenmiş sürümü kaydetmenize olanak tanır. Bu özellik, parolayı değiştirerek PDF belgelerinizi korumanız gerektiğinde kullanışlı olur.

## 1. Adım: Gereksinimler

Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

- C# programlama dili hakkında temel bilgi
- Makinenizde yüklü Visual Studio
- Aspose.PDF for .NET library yüklü

## 2. Adım: Ortamı Kurma

Başlamak için, geliştirme ortamınızı kurmak üzere şu adımları izleyin:

1. Visual Studio'yu açın ve yeni bir C# projesi oluşturun.
2. NuGet Paket Yöneticisi'ni kullanarak Aspose.PDF for .NET kitaplığını kurun.
3. Gerekli ad alanlarını kod dosyanıza aktarın:

```csharp
using Aspose.Pdf;
```

## 3. Adım: PDF Belgesini Yükleme

İlk adım, şifresini değiştirmek istediğiniz PDF belgesini yüklemektir. Bu örnekte, belirtilen dizinde "ChangePassword.pdf" adlı bir PDF dosyanız olduğunu varsayıyoruz.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document document = new Document(dataDir + "ChangePassword.pdf", "owner");
```

## 4. Adım: Parolayı Değiştirme

 PDF belgesini yükledikten sonra, şifresini kullanarak değiştirebilirsiniz.`ChangePasswords`yöntem. Yöntem üç parametre gerektirir: mevcut sahip şifresi, yeni kullanıcı şifresi ve yeni sahip şifresi.

```csharp
document.ChangePasswords("owner", "newuser", "newowner");
```

Yer tutucuları, ayarlamak istediğiniz gerçek parolalarla değiştirdiğinizden emin olun.

## 5. Adım: Güncellenmiş PDF'yi Kaydetme

 Parolayı değiştirdikten sonra, güncellenmiş PDF belgesini kaydetmeniz gerekir. Çıktı dosyası yolunu belirtin ve`Save` Belgeyi kaydetme yöntemi.

```csharp
dataDir = dataDir + "ChangePassword_out.pdf";
document. Save(dataDir);
Console.WriteLine("\nPDF file password changed successfully.\nFile saved at " + dataDir);
```

Güncellenen PDF belirtilen konuma kaydedilecektir.

### Aspose.PDF for .NET kullanarak Change Password için örnek kaynak kodu 
```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Belgeyi aç
Document document = new Document(dataDir+ "ChangePassword.pdf", "owner");
// Şifre değiştir
document.ChangePasswords("owner", "newuser", "newowner");
dataDir = dataDir + "ChangePassword_out.pdf";
// Güncellenmiş PDF'yi kaydet
document.Save(dataDir);
Console.WriteLine("\nPDF file password changed successfully.\nFile saved at " + dataDir);
```

## Çözüm

Tebrikler! Aspose.PDF for .NET kullanarak bir PDF belgesinin şifresini başarıyla değiştirdiniz. Bu eğitim, belgenin yüklenmesinden güncellenmiş sürümün kaydedilmesine kadar adım adım süreci kapsıyordu. Artık PDF dosyalarınızı yeni parolalarla güvenceye almak için bu özelliği kullanabilirsiniz.