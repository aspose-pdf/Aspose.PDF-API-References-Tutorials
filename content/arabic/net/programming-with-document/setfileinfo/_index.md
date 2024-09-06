---
title: تعيين معلومات الملف في ملف PDF
linktitle: تعيين معلومات الملف في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية استخدام Aspose.PDF لـ .NET لتعيين معلومات الملف في ملف PDF باستخدام هذا الدليل خطوة بخطوة.
type: docs
weight: 310
url: /ar/net/programming-with-document/setfileinfo/
---
إذا كنت تعمل على مشروع يتطلب إدارة ملفات PDF باستخدام Aspose.PDF for .NET، فإن إحدى الميزات التي قد ترغب في الاستفادة منها هي القدرة على تعيين معلومات الملف لمستند PDF. تتضمن معلومات الملف تفاصيل مختلفة مثل المؤلف وتاريخ الإنشاء والكلمات الأساسية وتاريخ التعديل والموضوع والعنوان. سيرشدك هذا الدليل خلال عملية تعيين معلومات الملف لمستند PDF باستخدام كود المصدر C# مع Aspose.PDF for .NET.

## دليل خطوة بخطوة لتعيين معلومات الملف باستخدام Aspose.PDF لـ .NET

1. قم بإنشاء مشروع C# جديد في Visual Studio IDE الخاص بك.
2. أضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET في مشروعك.
3. قم بإنشاء كائن مستند PDF جديد عن طريق توفير المسار إلى ملف PDF الذي تريد تعديل معلومات الملف له.

## الخطوة 1: تعيين المسار إلى دليل المستندات.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: افتح مستند PDF

```csharp
// فتح المستند
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

## الخطوة 6: تأكد من تحديث معلومات الملف بنجاح.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

لقد قمت بنجاح بتعيين معلومات الملف لمستند PDF باستخدام Aspose.PDF لـ .NET.

### مثال على كود المصدر لتعيين معلومات الملف باستخدام Aspose.PDF لـ .NET


```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// فتح المستند
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
// حفظ المستند الناتج
pdfDocument.Save(dataDir);

Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

## خاتمة

في الختام، يوفر Aspose.PDF for .NET طريقة بسيطة وفعالة لتعيين معلومات الملف لمستندات PDF. باتباع الخطوات المذكورة أعلاه، يمكنك بسهولة تعيين قيم معلومات الملف المطلوبة لمستندات PDF الخاصة بك باستخدام كود المصدر C#.

### الأسئلة الشائعة حول معلومات الملف المحددة في ملف PDF

#### س: هل يمكنني تعيين خصائص معلومات الملف الإضافية غير المذكورة في المثال؟

 ج: نعم، يمكنك تعيين خصائص معلومات الملف الإضافية باستخدام`DocumentInfo` الكائن في Aspose.PDF لـ .NET.`DocumentInfo`توفر الفئة خصائص مختلفة تسمح لك بتعيين معلومات إضافية مثل المنتج والإصدار والخصائص المخصصة.

#### س: هل من الممكن استرجاع معلومات الملف من مستند PDF موجود؟

 ج: نعم، يمكنك استرداد معلومات الملف من مستند PDF موجود باستخدام Aspose.PDF لـ .NET. للقيام بذلك، يمكنك استخدام`DocumentInfo` كائن للوصول إلى خصائص معلومات الملف وقراءة المعلومات المخزنة في مستند PDF.

#### س: هل يؤدي ضبط معلومات الملف إلى تعديل مستند PDF الأصلي؟

ج: لا، لا يؤدي ضبط معلومات الملف باستخدام Aspose.PDF لـ .NET إلى تعديل مستند PDF الأصلي. بدلاً من ذلك، يقوم بإنشاء مستند PDF جديد بمعلومات الملف المحدثة. يظل مستند PDF الأصلي دون تغيير.