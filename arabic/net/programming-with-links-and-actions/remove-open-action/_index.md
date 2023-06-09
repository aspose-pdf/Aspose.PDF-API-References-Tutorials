---
title: إزالة الإجراء المفتوح
linktitle: إزالة الإجراء المفتوح
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إزالة الإجراء المفتوح من ملف PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 80
url: /ar/net/programming-with-links-and-actions/remove-open-action/
---

تعرف على كيفية إزالة الإجراء المفتوح من ملف PDF باستخدام Aspose.PDF for .NET باستخدام هذا الدليل المفصل خطوة بخطوة.

## الخطوة الأولى: تهيئة البيئة

تأكد من قيامك بإعداد بيئة التطوير الخاصة بك باستخدام مشروع C # ومراجع Aspose.PDF المناسبة.

## الخطوة الثانية: تحميل ملف PDF

قم بتعيين مسار الدليل للمستندات الخاصة بك وقم بتحميل ملف PDF باستخدام الكود التالي:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// افتح المستند
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
```

## الخطوة 3: حذف الإجراء المفتوح

 قم بإزالة الإجراء المفتوح من المستند عن طريق تعيين ملف`OpenAction` الخاصية لاغية:

```csharp
document. OpenAction = null;
```

## الخطوة 4: احفظ المستند المحدث

 احفظ المستند المحدث باستخدام ملف`Save` طريقة:

```csharp
dataDir = dataDir + "RemoveOpenAction_out.pdf";
document. Save(dataDir);
```

## الخطوة 5: عرض النتيجة

اعرض رسالة تشير إلى أن الإجراء المفتوح قد تمت إزالته بنجاح وحدد موقع الملف المحفوظ:

```csharp
Console.WriteLine("\nOpen action deleted successfully.\nFile saved to location: " + dataDir);
```

### نموذج التعليمات البرمجية المصدر لـ Remove Open Action باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
// إزالة وثيقة العمل المفتوح
document.OpenAction = null;
dataDir = dataDir + "RemoveOpenAction_out.pdf";
// احفظ المستند المحدث
document.Save(dataDir);
Console.WriteLine("\nOpen action removed successfully.\nFile saved at " + dataDir); 
```

## خاتمة

تهنئة ! أنت الآن تعرف كيفية إزالة الإجراء المفتوح من ملف PDF باستخدام Aspose.PDF for .NET. استخدم هذه المعرفة لتخصيص خصائص وسلوك ملفات PDF في مشاريعك.

الآن بعد أن أكملت هذا الدليل ، يمكنك تطبيق هذه المفاهيم على مشاريعك الخاصة واستكشاف المزيد من الميزات التي يوفرها Aspose.PDF لـ .NET.