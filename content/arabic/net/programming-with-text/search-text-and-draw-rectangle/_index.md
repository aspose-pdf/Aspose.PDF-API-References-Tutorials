---
title: البحث عن النص ورسم المستطيل
linktitle: البحث عن النص ورسم المستطيل
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية البحث عن نص في ملف PDF، ورسم مستطيلات حول النص الموجود، وحفظ المستند المعدل باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 460
url: /ar/net/programming-with-text/search-text-and-draw-rectangle/
---
يوضح هذا البرنامج التعليمي كيفية استخدام Aspose.PDF for .NET للبحث عن نص معين في مستند PDF، ورسم مستطيل حول النص الموجود، وحفظ المستند المعدل. يوضح كود المصدر C# المقدم العملية خطوة بخطوة.

## المتطلبات الأساسية

قبل المتابعة بالبرنامج التعليمي، تأكد من توفر ما يلي:

- المعرفة الأساسية للغة البرمجة C#.
- تم تثبيت مكتبة Aspose.PDF لـ .NET. يمكنك الحصول عليها من موقع Aspose على الويب أو استخدام NuGet لتثبيتها في مشروعك.

## الخطوة 1: إعداد المشروع

ابدأ بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك وأضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: استيراد المساحات الأساسية الضرورية

أضف التوجيهات التالية في بداية ملف C# الخاص بك لاستيراد المساحات المطلوبة:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
```

## الخطوة 3: تعيين المسار إلى دليل المستند

 قم بتعيين المسار إلى دليل المستند الخاص بك باستخدام`dataDir` عامل:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

## الخطوة 4: تحميل مستند PDF

 قم بتحميل مستند PDF باستخدام`Document` فصل:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 يستبدل`"SearchAndGetTextFromAll.pdf"` مع الاسم الفعلي لملف PDF الخاص بك.

## الخطوة 5: إنشاء TextFragmentAbsorber

 إنشاء`TextFragmentAbsorber` كائن للعثور على جميع حالات عبارة البحث المدخلة:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 يستبدل`@"[\S]+"` مع نمط التعبير العادي المطلوب.

## الخطوة 6: تمكين البحث عن التعبيرات العادية

 تمكين البحث عن التعبيرات العادية عن طريق ضبط`TextSearchOptions` خصائص الممتص:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## الخطوة 7: البحث في جميع الصفحات

قبول الامتصاص لجميع صفحات الوثيقة:

```csharp
document.Pages.Accept(textAbsorber);
```

## الخطوة 8: ارسم مستطيلاً حول النص الموجود

 إنشاء`PdfContentEditor` قم بتتبع أجزاء النص المسترجعة والتنقل خلالها، ورسم مستطيل حول كل جزء من النص:

```csharp
var editor = new PdfContentEditor(document);
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

## الخطوة 9: احفظ المستند المعدل

حفظ المستند المعدل:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

 تأكد من الاستبدال`"SearchTextAndDrawRectangle_out.pdf"` مع اسم ملف الإخراج المطلوب.

### عينة من كود المصدر للبحث عن النص ورسم المستطيل باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// فتح المستند
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// إنشاء كائن TextAbsorber للعثور على جميع العبارات المطابقة للتعبير العادي
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
document.Pages.Accept(textAbsorber); 
var editor = new PdfContentEditor(document); 
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
			DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
	}
}
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

## خاتمة

مبروك! لقد تعلمت بنجاح كيفية البحث عن نص معين في مستند PDF، ورسم مستطيل حول النص الموجود، وحفظ المستند المعدل باستخدام Aspose.PDF for .NET. قدم هذا البرنامج التعليمي دليلاً خطوة بخطوة، من إعداد المشروع إلى تنفيذ الإجراءات المطلوبة. يمكنك الآن دمج هذا الكود في مشاريع C# الخاصة بك لمعالجة النص ورسم المستطيلات في ملفات PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "البحث عن النص ورسم المستطيل"؟

أ: يهدف البرنامج التعليمي "البحث عن نص ورسم مستطيل" إلى توجيه المستخدمين خلال عملية استخدام مكتبة Aspose.PDF لـ .NET للبحث عن نص معين داخل مستند PDF، ورسم مستطيلات حول أجزاء النص التي تم العثور عليها، وحفظ المستند المعدل. يوفر البرنامج التعليمي تعليمات مفصلة وعينات من أكواد C# لتوضيح كل خطوة من خطوات العملية.

#### س: كيف يساعد هذا البرنامج التعليمي في رسم المستطيلات حول نص معين في مستند PDF؟

ج: يوفر هذا البرنامج التعليمي دليلاً شاملاً حول كيفية تحديد ورسم مستطيلات حول أجزاء نصية معينة داخل مستند PDF. ويوضح عملية إعداد مشروع، وتحميل مستند PDF، وتمكين البحث باستخدام التعبيرات العادية، ورسم مستطيلات حول أجزاء النص الموجودة، وحفظ ملف PDF المعدل.

#### س: ما هي المتطلبات الأساسية المطلوبة لمتابعة هذا البرنامج التعليمي؟

ج: قبل البدء في البرنامج التعليمي، يجب أن يكون لديك فهم أساسي للغة البرمجة C#. بالإضافة إلى ذلك، يجب أن يكون لديك مكتبة Aspose.PDF for .NET مثبتة. يمكنك الحصول عليها من موقع Aspose على الويب أو تثبيتها في مشروعك باستخدام NuGet.

#### س: كيف أقوم بإعداد مشروعي لمتابعة هذا البرنامج التعليمي؟

ج: ابدأ بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة المفضلة لديك (IDE). ثم أضف مرجعًا إلى مكتبة Aspose.PDF for .NET إلى مشروعك. سيمكنك هذا من استخدام وظائف المكتبة للتعامل مع مستندات PDF.

#### س: هل يمكنني رسم مستطيلات حول نص معين باستخدام هذا البرنامج التعليمي؟

ج: نعم، يركز البرنامج التعليمي على رسم مستطيلات حول أجزاء نصية محددة داخل مستند PDF. ويوضح كيفية تحديد النص المطلوب باستخدام التعبيرات العادية، وإنشاء مستطيلات حول أجزاء النص المحددة، وحفظ ملف PDF المعدل.

#### س: كيف يمكنني تحديد النص الذي أريد البحث عنه ورسم المستطيلات حوله؟

 أ: لتحديد النص الذي تريد البحث عنه ورسم المستطيلات حوله، قم بإنشاء`TextFragmentAbsorber` الكائن وتعيين نمطه باستخدام`Text` المعلمة. استبدال النمط الافتراضي`@"[\S]+"` في كود البرنامج التعليمي باستخدام نمط التعبير العادي المطلوب.

#### س: كيف أقوم بتمكين البحث عن التعبيرات العادية للنص؟

 أ: يتم تمكين البحث عن التعبيرات العادية عن طريق إنشاء`TextSearchOptions` الكائن وتعيين قيمته إلى`true` . تعيين هذا الكائن إلى`TextSearchOptions` ممتلكات`TextFragmentAbsorber` يضمن هذا استخدام نمط التعبير العادي أثناء البحث عن النص.

#### س: كيف أرسم مستطيلات حول النص الموجود؟

 أ: بعد تحديد أجزاء النص باستخدام`TextFragmentAbsorber` يوفر البرنامج التعليمي حلقة للتكرار خلال هذه المقاطع. لكل مقطع نصي، يوضح البرنامج التعليمي كيفية إنشاء مستطيل حوله باستخدام`DrawBox` الطريقة وتحديد مظهر المستطيل.

#### س: ما هي خطوات حفظ ملف PDF المعدل مع رسم المستطيلات؟

أ: بعد رسم المستطيلات حول أجزاء النص المطلوبة، استخدم`Document` الصف`Save` طريقة لحفظ المستند المعدّل. يوضح كود العينة في البرنامج التعليمي كيفية حفظ ملف PDF المعدّل وعرض رسالة نجاح.

#### س: هل يمكنني تخصيص مظهر المستطيلات المرسومة؟

 ج: نعم، يمكنك تخصيص مظهر المستطيلات المرسومة. في التعليمات البرمجية النموذجية للبرنامج التعليمي،`DrawBox` تُستخدم هذه الطريقة لإنشاء المستطيلات. يمكنك تعديل خصائص مثل اللون والنمط والسمك لتخصيص مظهر المستطيلات المرسومة.