---
title: تعيين الامتيازات
linktitle: تعيين الامتيازات
second_title: Aspose.PDF لمرجع .NET API
description: قم بتعيين امتيازات الوصول لملفات PDF الخاصة بك بسهولة باستخدام Aspose.PDF for .NET.
type: docs
weight: 100
url: /ar/net/programming-with-security-and-signatures/set-privileges/
---

غالبًا ما يكون من الضروري تعيين امتيازات وصول محددة لملفات PDF. باستخدام Aspose.PDF for .NET ، يمكنك بسهولة تعيين امتيازات الوصول باستخدام التعليمات البرمجية المصدر التالية:

## الخطوة 1: استيراد المكتبات المطلوبة

قبل أن تبدأ ، تحتاج إلى استيراد المكتبات اللازمة لمشروع C # الخاص بك. فيما يلي توجيهات الاستيراد الضرورية:

```csharp
using Aspose.Pdf;
```

## الخطوة 2: حدد المسار إلى مجلد المستندات

 في هذه الخطوة ، تحتاج إلى تحديد المسار إلى المجلد الذي يحتوي على ملف PDF الذي تريد تحريره. يستبدل`"YOUR DOCUMENTS DIRECTORY"` في الكود التالي بالمسار الفعلي لمجلد المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 3: تحميل ملف PDF المصدر

سنقوم الآن بتحميل ملف PDF المصدر باستخدام الكود التالي:

```csharp
using (Document document = new Document(dataDir + "input.pdf"))
```

## الخطوة 4: تعيين امتيازات الوصول

 في هذه الخطوة ، سنقوم بإنشاء مثيل`DocumentPrivilege` لتعيين امتيازات الوصول المطلوبة. يمكنك تطبيق قيود على جميع الامتيازات باستخدام`DocumentPrivilege.ForbidAll` . على سبيل المثال ، إذا كنت تريد السماح بقراءة الشاشة فقط ، فيمكنك ضبط`AllowScreenReaders` ل`true`. هذا هو الكود المقابل:

```csharp
DocumentPrivilege documentPrivilege = DocumentPrivilege.ForbidAll;
documentPrivilege.AllowScreenReaders = true;
```

## الخطوة 5: تشفير وحفظ المستند

 أخيرًا ، يمكننا تشفير مستند PDF باستخدام كلمة مرور المستخدم والمالك`Encrypt` وتحديد خوارزمية التشفير المطلوبة. ثم نقوم بحفظ المستند المحدث. هذا هو الكود المقابل:

```csharp
document.Encrypt("user", "owner", documentPrivilege, CryptoAlgorithm.AESx128, false);
document.Save(dataDir + "SetPrivileges_out.pdf");
```

### نموذج التعليمات البرمجية المصدر لـ Set Privileges باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// قم بتحميل ملف PDF المصدر
using (Document document = new Document(dataDir + "input.pdf"))
{
	// إنشاء كائن امتيازات المستند
	// تطبيق قيود على جميع الامتيازات
	DocumentPrivilege documentPrivilege = DocumentPrivilege.ForbidAll;
	// السماح بقراءة الشاشة فقط
	documentPrivilege.AllowScreenReaders = true;
	// تشفير الملف بكلمة مرور المستخدم والمالك.
	// تحتاج إلى تعيين كلمة المرور ، بحيث بمجرد عرض المستخدم للملف بكلمة مرور المستخدم ،
	//تم تمكين خيار قراءة الشاشة فقط
	document.Encrypt("user", "owner", documentPrivilege, CryptoAlgorithm.AESx128, false);
	// احفظ المستند المحدث
	document.Save(dataDir + "SetPrivileges_out.pdf");
}
```

## خاتمة

تهنئة ! لديك الآن دليل تفصيلي خطوة بخطوة لتعيين امتيازات الوصول إلى مستند PDF باستخدام Aspose.PDF for .NET. يمكنك استخدام هذا الرمز لتطبيق قيود محددة وحماية ملفات PDF الخاصة بك حسب الحاجة.

تأكد من إطلاعك على وثائق Aspose.PDF الرسمية لمزيد من المعلومات حول أمان مستندات PDF المتقدم وميزات إدارة امتيازات الوصول.