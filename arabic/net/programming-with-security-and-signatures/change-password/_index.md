---
title: تغيير كلمة المرور
linktitle: تغيير كلمة المرور
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تغيير كلمة مرور مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-security-and-signatures/change-password/
---

في هذا البرنامج التعليمي ، سنوجهك خلال عملية تغيير كلمة مرور مستند PDF باستخدام Aspose.PDF for .NET. تتيح لك المكتبة فتح ملف PDF موجود وتعديل كلمة المرور الخاصة به وحفظ الإصدار المحدث. هذه الميزة مفيدة عندما تحتاج إلى تأمين مستندات PDF الخاصة بك عن طريق تغيير كلمة المرور.

## الخطوة 1: المتطلبات

قبل أن نبدأ ، تأكد من توفر المتطلبات الأساسية التالية لديك:

- المعرفة الأساسية بلغة البرمجة C #
- تم تثبيت Visual Studio على جهازك
- تثبيت Aspose.PDF لمكتبة .NET

## الخطوة الثانية: تهيئة البيئة

للبدء ، اتبع هذه الخطوات لإعداد بيئة التطوير الخاصة بك:

1. افتح Visual Studio وأنشئ مشروع C # جديد.
2. قم بتثبيت Aspose.PDF لمكتبة .NET باستخدام NuGet Package Manager.
3. قم باستيراد مساحات الأسماء المطلوبة إلى ملف التعليمات البرمجية الخاص بك:

```csharp
using Aspose.Pdf;
```

## الخطوة 3: تحميل مستند PDF

الخطوة الأولى هي تحميل مستند PDF الذي تريد تغيير كلمة المرور الخاصة به. في هذا المثال ، نفترض أن لديك ملف PDF باسم "ChangePassword.pdf" في الدليل المحدد.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document document = new Document(dataDir + "ChangePassword.pdf", "owner");
```

## الخطوة 4: تغيير كلمة المرور

 بمجرد تحميل مستند PDF ، يمكنك تغيير كلمة المرور الخاصة به باستخدام ملف`ChangePasswords`طريقة. تتطلب الطريقة ثلاثة معلمات: كلمة مرور المالك الحالي وكلمة مرور المستخدم الجديدة وكلمة مرور المالك الجديدة.

```csharp
document.ChangePasswords("owner", "newuser", "newowner");
```

تأكد من استبدال العناصر النائبة بكلمات المرور الفعلية التي تريد تعيينها.

## الخطوة 5: حفظ ملف PDF المحدث

 بعد تغيير كلمة المرور ، تحتاج إلى حفظ مستند PDF المحدث. حدد مسار ملف الإخراج واستخدم الامتداد`Save` طريقة لحفظ المستند.

```csharp
dataDir = dataDir + "ChangePassword_out.pdf";
document. Save(dataDir);
Console.WriteLine("\nPDF file password changed successfully.\nFile saved at " + dataDir);
```

سيتم حفظ ملف PDF المحدث في الموقع المحدد.

### نموذج التعليمات البرمجية المصدر لتغيير كلمة المرور باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// افتح المستند
Document document = new Document(dataDir+ "ChangePassword.pdf", "owner");
// تغيير كلمة المرور
document.ChangePasswords("owner", "newuser", "newowner");
dataDir = dataDir + "ChangePassword_out.pdf";
// احفظ ملف PDF المحدث
document.Save(dataDir);
Console.WriteLine("\nPDF file password changed successfully.\nFile saved at " + dataDir);
```

## خاتمة

تهانينا! لقد نجحت في تغيير كلمة مرور مستند PDF باستخدام Aspose.PDF for .NET. غطى هذا البرنامج التعليمي العملية خطوة بخطوة ، من تحميل المستند إلى حفظ الإصدار المحدث. يمكنك الآن استخدام هذه الميزة لتأمين ملفات PDF الخاصة بك بكلمات مرور جديدة.