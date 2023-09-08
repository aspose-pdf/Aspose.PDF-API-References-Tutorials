---
title: استبدال الخطوط المفقودة
linktitle: استبدال الخطوط المفقودة
second_title: Aspose.PDF لمرجع .NET API
description: دليل خطوة بخطوة لاستبدال الخطوط المفقودة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 260
url: /ar/net/document-conversion/replace-missing-fonts/
---
في هذا البرنامج التعليمي، سنرشدك خلال عملية استبدال الخطوط المفقودة في ملف PDF باستخدام Aspose.PDF لـ .NET. عند فتح ملف PDF على جهاز مفقود فيه خط معين، قد تكون هناك مشكلات في عرض الخط. في مثل هذه الحالات، من الممكن استبدال الخط المفقود بخط آخر متوفر على الجهاز. باتباع الخطوات الموضحة أدناه، ستتمكن من استبدال الخطوط المفقودة في ملف PDF.

## المتطلبات الأساسية
قبل البدء، تأكد من استيفاء المتطلبات الأساسية التالية:

- المعرفة الأساسية بلغة البرمجة C#.
- مكتبة Aspose.PDF لـ .NET مثبتة على نظامك.
- بيئة تطوير مثل Visual Studio.

## الخطوة 1: العثور على الخط المفقود
الخطوة الأولى هي العثور على الخط المفقود في ملف PDF. استخدم الكود التالي:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
     // ابحث عن الخط الأصلي
     originalFont = FontRepository.FindFont("AgencyFB");
}
catch(Exception)
{
     // الخط مفقود على الجهاز الوجهة
     // إضافة استبدال الخط البسيط
     FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` مع الدليل الفعلي الذي يوجد به ملف PDF الخاص بك.

## الخطوة 2: استبدال الخط المفقود
بعد ذلك، سنقوم باستبدال الخط المفقود بخط آخر متاح. استخدم الكود التالي:

```csharp
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");

// قم بتحويل ملف PDF إلى تنسيق PDF/A مع إزالة الأخطاء
pdf.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

// احفظ ملف PDF الناتج
pdf.Save(fileNew.FullName);
```

 تأكد من استبدال`"input.pdf"` مع المسار الفعلي إلى ملف PDF الأصلي الخاص بك و`"newfile_out.pdf"` بالاسم المطلوب لملف PDF الناتج.

## الخطوة 3: حفظ ملف PDF الناتج
وأخيرًا، سنقوم بحفظ ملف PDF الناتج بالخط الذي تم استبداله. استخدم الكود التالي:

```csharp
// احفظ ملف PDF الناتج
pdf.Save(fileNew.FullName);
```

يضمن التأكد من أنك قمت بتعيين مسار الوجهة الصحيح لملف PDF الناتج.

### مثال على التعليمات البرمجية المصدر لاستبدال الخطوط المفقودة باستخدام Aspose.PDF لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
	originalFont = FontRepository.FindFont("AgencyFB");
}
catch (Exception)
{
	// الخط مفقود على الجهاز الوجهة
	FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");
pdf.Convert( dataDir +  "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
pdf.Save(fileNew.FullName);
```

## خاتمة
في هذا البرنامج التعليمي، قمنا بتغطية العملية خطوة بخطوة لاستبدال الخطوط المفقودة في ملف PDF باستخدام Aspose.PDF لـ .NET. باتباع الإرشادات الموضحة أعلاه، ستتمكن من استبدال الخطوط المفقودة في ملف PDF الخاص بك بنجاح.

### الأسئلة الشائعة

#### س: ما هو Aspose.PDF لـ .NET؟

ج: Aspose.PDF for .NET هي مكتبة قوية تمكن المطورين من العمل مع مستندات PDF في تطبيقات C#. وهو يوفر وظائف متنوعة، بما في ذلك القدرة على استبدال الخطوط المفقودة في ملفات PDF.

#### س: لماذا أواجه خطوطًا مفقودة في ملف PDF؟

ج: يمكن أن يحدث فقدان الخطوط في ملف PDF عند فتح الملف على جهاز لم يتم تثبيت الخطوط الضرورية عليه. يمكن أن يؤدي ذلك إلى استبدال الخط، مما يؤثر على المظهر المرئي للمستند.

#### س: كيف يمكنني العثور على الخطوط المفقودة واستبدالها في ملف PDF باستخدام Aspose.PDF لـ .NET؟

 ج: للبحث عن الخطوط المفقودة واستبدالها، يمكنك استخدام`FontRepository.FindFont` طريقة للتحقق من وجود الخط المطلوب. إذا كان الخط مفقودًا، فيمكنك إضافة بديل للخط باستخدام`FontRepository.Substitutions` ملكية.

#### س: هل يمكنني تخصيص عملية استبدال الخط؟

ج: نعم، يمكنك تخصيص عملية استبدال الخط عن طريق تحديد خط مختلف للاستبدال. في الكود المقدم، استخدمنا Arial كبديل لخط "AgencyFB" المفقود، ولكن يمكنك اختيار خط مختلف وفقًا لتفضيلاتك.

#### س: كيف يمكنني التأكد من دقة عرض الخط بعد الاستبدال؟

ج: يوفر Aspose.PDF for .NET إمكانات قوية للتعامل مع الخطوط، مما يضمن عرضًا دقيقًا للخط بعد الاستبدال. يمكنك معاينة ملف PDF الناتج للتحقق من استبدال الخط.