---
title: تعيين معلومات الملف في ملف PDF
linktitle: تعيين معلومات الملف في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام Aspose.PDF لـ .NET لتعيين معلومات الملف في ملف PDF باستخدام هذا الدليل التفصيلي خطوة بخطوة.
type: docs
weight: 310
url: /ar/net/programming-with-document/setfileinfo/
---
إذا كنت تعمل على مشروع يتطلب إدارة ملفات PDF باستخدام Aspose.PDF لـ .NET، فإن إحدى الميزات التي قد ترغب في استخدامها هي القدرة على تعيين معلومات الملف لمستند PDF. تتضمن معلومات الملف تفاصيل مختلفة مثل المؤلف وتاريخ الإنشاء والكلمات الرئيسية وتاريخ التعديل والموضوع والعنوان. سيرشدك هذا الدليل خلال عملية إعداد معلومات الملف لمستند PDF باستخدام كود مصدر C# مع Aspose.PDF لـ .NET.

## دليل خطوة بخطوة لإعداد معلومات الملف باستخدام Aspose.PDF لـ .NET

1. قم بإنشاء مشروع C# جديد في Visual Studio IDE الخاص بك.
2. أضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET في مشروعك.
3. قم بإنشاء كائن مستند PDF جديد عن طريق توفير المسار إلى ملف PDF الذي تريد تعديل معلومات الملف له.

## الخطوة 1: قم بتعيين المسار إلى دليل المستندات.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح مستند PDF

```csharp
// افتح المستند
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## الخطوة 3: استخدم كائن DocumentInfo للوصول إلى معلومات الملف الخاصة بمستند PDF.

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## الخطوة 4: قم بتعيين قيم معلومات الملف المطلوبة باستخدام خصائص كائن DocumentInfo.

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## الخطوة 5: احفظ مستند PDF المحدث في الموقع المحدد.

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## الخطوة 6: التحقق من تحديث معلومات الملف بنجاح.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

لقد قمت بنجاح بتعيين معلومات الملف لمستند PDF باستخدام Aspose.PDF لـ .NET.

### مثال على التعليمات البرمجية المصدر لتعيين معلومات الملف باستخدام Aspose.PDF لـ .NET


```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// افتح المستند
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

// تحديد معلومات الوثيقة
DocumentInfo docInfo = new DocumentInfo(pdfDocument);

docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";

dataDir = dataDir + "SetFileInfo_out.pdf";
// حفظ مستند الإخراج
pdfDocument.Save(dataDir);

Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

## خاتمة

في الختام، يوفر Aspose.PDF for .NET طريقة بسيطة وفعالة لإعداد معلومات الملف لمستندات PDF. باتباع الخطوات المذكورة أعلاه، يمكنك بسهولة تعيين قيم معلومات الملف المطلوبة لمستندات PDF الخاصة بك باستخدام كود مصدر C#.

### الأسئلة الشائعة لتعيين معلومات الملف في ملف PDF

#### س: هل يمكنني تعيين خصائص معلومات الملف الإضافية غير المذكورة في المثال؟

 ج: نعم، يمكنك تعيين خصائص معلومات الملف الإضافية باستخدام الملف`DocumentInfo` الكائن في Aspose.PDF لـ .NET. ال`DocumentInfo`توفر الفئة خصائص متنوعة تسمح لك بتعيين معلومات إضافية مثل المنتج والإصدار والخصائص المخصصة.

#### س: هل من الممكن استرجاع معلومات الملف من مستند PDF موجود؟

 ج: نعم، يمكنك استرداد معلومات الملف من مستند PDF موجود باستخدام Aspose.PDF لـ .NET. للقيام بذلك، يمكنك استخدام`DocumentInfo` كائن للوصول إلى خصائص معلومات الملف وقراءة المعلومات المخزنة في وثيقة PDF.

#### س: هل يؤدي تعيين معلومات الملف إلى تعديل مستند PDF الأصلي؟

ج: لا، لا يؤدي تعيين معلومات الملف باستخدام Aspose.PDF لـ .NET إلى تعديل مستند PDF الأصلي. وبدلاً من ذلك، يقوم بإنشاء مستند PDF جديد يتضمن معلومات الملف المحدثة. يبقى مستند PDF الأصلي دون تغيير.