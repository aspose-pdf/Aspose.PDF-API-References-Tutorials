---
title: تحديد كلمة المرور الصحيحة
linktitle: تحديد كلمة المرور الصحيحة
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تحديد كلمة المرور الصحيحة لملف PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 30
url: /ar/net/programming-with-security-and-signatures/determine-correct-password/
---

في هذا البرنامج التعليمي ، سنرشدك خلال عملية تحديد كلمة المرور الصحيحة لملف PDF باستخدام Aspose.PDF for .NET. تتيح لك هذه الميزة التحقق مما إذا كان ملف PDF محميًا بكلمة مرور والعثور على كلمة المرور الصحيحة من قائمة محددة مسبقًا.

## الخطوة 1: المتطلبات الأساسية

قبل أن تبدأ ، تأكد من توفر المتطلبات الأساسية التالية لديك:

- المعرفة الأساسية بلغة البرمجة C #
- تثبيت Visual Studio على جهازك
- تثبيت مكتبة Aspose.PDF لـ .NET

## الخطوة 2: إعداد البيئة

للبدء ، اتبع هذه الخطوات لإعداد بيئة التطوير الخاصة بك:

1. افتح Visual Studio وأنشئ مشروع C # جديد.
2. قم باستيراد مساحات الأسماء المطلوبة إلى ملف التعليمات البرمجية الخاص بك:

```csharp
using Aspose.Pdf;
```

## الخطوة 3: تحميل ملف PDF المصدر

الخطوة الأولى هي تحميل ملف PDF المصدر الذي تريد التحقق منه. في هذا المثال ، نفترض أن لديك ملف PDF باسم "IsPasswordProtected.pdf" في الدليل المحدد.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
```

تأكد من استبدال العناصر النائبة بالمواقع الفعلية لملف PDF الخاص بك.

## الخطوة 4: تحديد مصدر تشفير PDF

 بمجرد تحميل ملف PDF المصدر ، يمكنك تحديد ما إذا كان مشفرًا باستخدام امتداد`IsEncrypted` طريقة`PdfFileInfo` هدف.

```csharp
Console.WriteLine("The file is password protected: " + info.IsEncrypted);
```

يعرض هذا البيان ما إذا كان ملف PDF محميًا بكلمة مرور أم لا.

## الخطوة الخامسة: البحث عن كلمة المرور الصحيحة

بعد ذلك ، سنبحث عن كلمة المرور الصحيحة باستخدام قائمة كلمات المرور المحددة مسبقًا. نتصفح كل كلمة مرور في القائمة ونحاول تحميل مستند PDF بكلمة المرور هذه.

```csharp
String[] passwords = new String[5] { "test", "test1", "test2", "test3", "sample" };
for (int passwordcount = 0; passwordcount < passwords.Length; passwordcount++)
{
try
{
Document doc = new Document(dataDir + "IsPasswordProtected.pdf", passwords[passwordcount]);
if (doc.Pages.Count > 0)
Console.WriteLine("The document contains " + doc.Pages.Count + " pages.");
}
catch (InvalidPasswordException)
{
Console.WriteLine("The password " + passwords[passwordcount] + " is not correct.");
}
}
```

تختبر هذه الحلقة كل كلمة مرور من القائمة. إذا كانت كلمة المرور صحيحة ، فسيتم عرض عدد الصفحات في المستند. خلاف ذلك ، يتم عرض رسالة تشير إلى أن كلمة المرور غير صحيحة.


### نموذج التعليمات البرمجية المصدر لتحديد كلمة المرور الصحيحة باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";            
// قم بتحميل ملف PDF المصدر
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
// حدد ما إذا كان ملف PDF المصدر مشفرًا أم لا
Console.WriteLine("File is password protected " + info.IsEncrypted);
String[] passwords = new String[5] { "test", "test1", "test2", "test3", "sample" };
for (int passwordcount = 0; passwordcount < passwords.Length; passwordcount++)
{
	try
	{
		Document doc = new Document(dataDir + "IsPasswordProtected.pdf", passwords[passwordcount]);
		if (doc.Pages.Count > 0)
			Console.WriteLine("Number of Page in document are = " + doc.Pages.Count);
	}
	catch (InvalidPasswordException)
	{
		Console.WriteLine("Password = " + passwords[passwordcount] + "  is not correct");
	}
}
```

## خاتمة

تهنئة ! لقد نجحت في تحديد كلمة المرور الصحيحة لملف PDF باستخدام Aspose.PDF for .NET. غطى هذا البرنامج التعليمي العملية خطوة بخطوة ، من التحقق من تشفير الملف إلى العثور على كلمة المرور الصحيحة من قائمة محددة مسبقًا. يمكنك الآن استخدام هذه الميزة للتحقق والعثور على كلمة المرور الصحيحة لملفات PDF الخاصة بك.