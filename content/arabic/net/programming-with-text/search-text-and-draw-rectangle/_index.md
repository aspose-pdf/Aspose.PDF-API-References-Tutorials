---
title: البحث عن نص ورسم مستطيل
linktitle: البحث عن نص ورسم مستطيل
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية البحث عن نص في ملف PDF، ورسم مستطيلات حول النص الذي تم العثور عليه، وحفظ المستند المعدل باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 460
url: /ar/net/programming-with-text/search-text-and-draw-rectangle/
---
يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.PDF لـ .NET للبحث عن نص محدد في مستند PDF، ورسم مستطيل حول النص الذي تم العثور عليه، وحفظ المستند المعدل. يوضح كود مصدر C# المقدم العملية خطوة بخطوة.

## المتطلبات الأساسية

قبل متابعة البرنامج التعليمي، تأكد من أن لديك ما يلي:

- المعرفة الأساسية بلغة البرمجة C#.
- تم تثبيت Aspose.PDF لمكتبة .NET. يمكنك الحصول عليه من موقع Aspose أو استخدام NuGet لتثبيته في مشروعك.

## الخطوة 1: إعداد المشروع

ابدأ بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة المفضلة لديك (IDE) وأضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: استيراد مساحات الأسماء الضرورية

أضف ما يلي باستخدام التوجيهات في بداية ملف C# الخاص بك لاستيراد مساحات الأسماء المطلوبة:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
```

## الخطوة 3: قم بتعيين المسار إلى دليل المستند

 قم بتعيين المسار إلى دليل المستند الخاص بك باستخدام`dataDir` عامل:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

## الخطوة 4: قم بتحميل مستند PDF

 قم بتحميل مستند PDF باستخدام`Document` فصل:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 يستبدل`"SearchAndGetTextFromAll.pdf"` بالاسم الفعلي لملف PDF الخاص بك.

## الخطوة 5: إنشاء TextFragmentAbsorter

 إنشاء`TextFragmentAbsorber` كائن للعثور على كافة مثيلات عبارة البحث المدخلة:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 يستبدل`@"[\S]+"` بنمط التعبير العادي الذي تريده.

## الخطوة 6: تمكين البحث بالتعبير العادي

 تمكين البحث بالتعبير العادي عن طريق تعيين`TextSearchOptions` خاصية الامتصاص:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## الخطوة 7: البحث في جميع الصفحات

قبول المستوعب لجميع صفحات الوثيقة:

```csharp
document.Pages.Accept(textAbsorber);
```

## الخطوة 8: ارسم مستطيلاً حول النص الموجود

 إنشاء`PdfContentEditor` الكائن والتكرار عبر أجزاء النص المستردة، مع رسم مستطيل حول كل مقطع نص:

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

احفظ المستند المعدل:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

 تأكد من استبدال`"SearchTextAndDrawRectangle_out.pdf"` مع اسم ملف الإخراج المطلوب.

### نموذج التعليمات البرمجية المصدر لـ Search Text And Draw Rectangle باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// قم بإنشاء كائن TextAbsorter للعثور على جميع العبارات المطابقة للتعبير العادي
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

تهانينا! لقد تعلمت بنجاح كيفية البحث عن نص معين في مستند PDF، ورسم مستطيل حول النص الذي تم العثور عليه، وحفظ المستند المعدل باستخدام Aspose.PDF لـ .NET. قدم هذا البرنامج التعليمي دليلاً خطوة بخطوة، بدءًا من إعداد المشروع وحتى تنفيذ الإجراءات المطلوبة. يمكنك الآن دمج هذا الرمز في مشاريع C# الخاصة بك لمعالجة النص ورسم المستطيلات في ملفات PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "البحث عن نص ورسم مستطيل"؟

ج: يهدف البرنامج التعليمي "البحث عن نص ورسم مستطيل" إلى توجيه المستخدمين خلال عملية استخدام مكتبة Aspose.PDF لـ .NET للبحث عن نص معين داخل مستند PDF، ورسم مستطيلات حول مقاطع النص التي تم العثور عليها، وحفظ النص المعدل. وثيقة. يوفر البرنامج التعليمي تعليمات تفصيلية وعينات من أكواد C# لتوضيح كل خطوة من خطوات العملية.

#### س: كيف يساعد هذا البرنامج التعليمي في رسم مستطيلات حول نص معين في مستند PDF؟

ج: يوفر هذا البرنامج التعليمي دليلاً شاملاً حول كيفية تحديد موقع المستطيلات ورسمها حول مقاطع نصية محددة داخل مستند PDF. فهو يوضح عملية إعداد المشروع، وتحميل مستند PDF، وتمكين البحث بالتعبير العادي، ورسم المستطيلات حول أجزاء النص التي تم العثور عليها، وحفظ ملف PDF المعدل.

#### س: ما هي المتطلبات الأساسية المطلوبة لمتابعة هذا البرنامج التعليمي؟

ج: قبل البدء في البرنامج التعليمي، يجب أن يكون لديك فهم أساسي للغة البرمجة C#. بالإضافة إلى ذلك، تحتاج إلى تثبيت Aspose.PDF لمكتبة .NET. يمكنك الحصول عليه من موقع Aspose أو تثبيته في مشروعك باستخدام NuGet.

#### س: كيف أقوم بإعداد مشروعي لمتابعة هذا البرنامج التعليمي؟

ج: ابدأ بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة المفضلة لديك (IDE). ثم قم بإضافة مرجع إلى مكتبة Aspose.PDF لـ .NET إلى مشروعك. سيمكنك هذا من استخدام وظائف المكتبة لمعالجة مستندات PDF.

#### س: هل يمكنني رسم مستطيلات حول نص معين باستخدام هذا البرنامج التعليمي؟

ج: نعم، يركز البرنامج التعليمي على رسم المستطيلات حول مقاطع نصية محددة داخل مستند PDF. ويوضح كيفية تحديد موقع النص المطلوب باستخدام التعبيرات العادية، وإنشاء مستطيلات حول أجزاء النص المحددة، وحفظ ملف PDF المعدل.

#### س: كيف يمكنني تحديد النص الذي أريد البحث عنه ورسم المستطيلات حوله؟

 ج: لتحديد النص الذي تريد البحث عنه ورسم المستطيلات حوله، قم بإنشاء ملف`TextFragmentAbsorber` كائن وتعيين نمطه باستخدام`Text` معامل. استبدل النمط الافتراضي`@"[\S]+"` في رمز البرنامج التعليمي بنمط التعبير العادي الذي تريده.

#### س: كيف يمكنني تمكين البحث بالتعبير العادي عن النص؟

 ج: يتم تمكين البحث عن التعبير العادي عن طريق إنشاء ملف`TextSearchOptions` الكائن وتحديد قيمته`true` . قم بتعيين هذا الكائن إلى`TextSearchOptions` ملكية`TextFragmentAbsorber` مثال. وهذا يضمن استخدام نمط التعبير العادي أثناء البحث عن النص.

#### س: كيف أرسم مستطيلات حول النص الموجود؟

 ج: بعد تحديد مقاطع النص باستخدام`TextFragmentAbsorber` ، يوفر البرنامج التعليمي حلقة للتكرار عبر هذه المقاطع. لكل مقطع نص، يوضح البرنامج التعليمي كيفية إنشاء مستطيل حوله باستخدام`DrawBox` الطريقة وتحديد مظهر المستطيل.

#### س: ما هي خطوات حفظ ملف PDF المعدل بالمستطيلات المرسومة؟

ج: بعد رسم المستطيلات حول أجزاء النص المطلوبة، استخدم`Document` الطبقة`Save` طريقة حفظ الوثيقة المعدلة. يعرض نموذج التعليمات البرمجية الخاص بالبرنامج التعليمي كيفية حفظ ملف PDF المحرر وعرض رسالة النجاح.

#### س: هل يمكنني تخصيص مظهر المستطيلات المرسومة؟

 ج: نعم، يمكنك تخصيص مظهر المستطيلات المرسومة. في نموذج التعليمات البرمجية للبرنامج التعليمي، فإن`DrawBox` يتم استخدام الطريقة لإنشاء المستطيلات. يمكنك تعديل خصائص مثل اللون والنمط والسمك لتخصيص مظهر المستطيلات المرسومة.