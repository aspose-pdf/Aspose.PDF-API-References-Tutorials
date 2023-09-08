---
title: بحث والحصول على النص الكل
linktitle: بحث والحصول على النص الكل
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية البحث عن النص والحصول عليه من جميع صفحات مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 420
url: /ar/net/programming-with-text/search-and-get-text-all/
---
يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.PDF لـ .NET للبحث عن النص والحصول عليه من جميع صفحات مستند PDF. يوضح كود مصدر C# المقدم العملية خطوة بخطوة.

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
```

## الخطوة 3: قم بتحميل مستند PDF

 قم بتعيين المسار إلى دليل مستند PDF الخاص بك وقم بتحميل المستند باستخدام ملف`Document` فصل:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 تأكد من استبدال`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

## الخطوة 4: البحث واستخراج النص

 إنشاء`TextFragmentAbsorber` كائن للعثور على كافة مثيلات عبارة البحث المدخلة:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 يستبدل`"text"` بالنص الفعلي الذي تريد البحث عنه.

## الخطوة 5: البحث في جميع الصفحات

قبول المستوعب لجميع صفحات الوثيقة:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## الخطوة 6: الحصول على أجزاء النص المستخرجة

احصل على أجزاء النص المستخرجة باستخدام`TextFragments` ملكية`TextFragmentAbsorber` هدف:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## الخطوة 7: قم بالتمرير خلال أجزاء النص

قم بالمرور عبر أجزاء النص التي تم الحصول عليها والوصول إلى خصائصها:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text: {0} ", textFragment.Text);
    Console.WriteLine("Position: {0} ", textFragment.Position);
    Console.WriteLine("XIndent: {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent: {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name: {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible: {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded: {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset: {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size: {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color: {0} ", textFragment.TextState.ForegroundColor);
}
```

يمكنك تعديل التعليمات البرمجية داخل الحلقة لتنفيذ المزيد من الإجراءات على كل جزء من النص.

### نموذج التعليمات البرمجية المصدر للبحث والحصول على النص الكل باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// قم بإنشاء كائن TextAbsorter للعثور على كافة مثيلات عبارة البحث المدخلة
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// قبول الممتص لجميع الصفحات
pdfDocument.Pages.Accept(textFragmentAbsorber);
// احصل على أجزاء النص المستخرجة
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// حلقة من خلال الشظايا
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text : {0} ", textFragment.Text);
	Console.WriteLine("Position : {0} ", textFragment.Position);
	Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية البحث عن النص والحصول عليه من جميع صفحات مستند PDF باستخدام Aspose.PDF لـ .NET. قدم هذا البرنامج التعليمي دليلاً خطوة بخطوة، بدءًا من تحميل المستند وحتى الوصول إلى أجزاء النص المستخرجة. يمكنك الآن دمج هذا الرمز في مشاريع C# الخاصة بك لتحليل ومعالجة محتوى النص في ملفات PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "البحث والحصول على النص بالكامل"؟

ج: يوضح البرنامج التعليمي "Search And Get Text All" كيفية استخدام مكتبة Aspose.PDF لـ .NET للبحث عن النص واستخراجه من جميع صفحات مستند PDF. يوفر البرنامج التعليمي إرشادات خطوة بخطوة بالإضافة إلى نموذج كود C# لإجراء البحث عن النص واسترجاعه.

#### س: كيف يساعد هذا البرنامج التعليمي في استخراج النص من مستندات PDF؟

ج: يرشدك هذا البرنامج التعليمي خلال عملية استخراج النص من جميع صفحات مستند PDF. ويستخدم مكتبة Aspose.PDF لتحديد عبارات نصية محددة واسترداد المعلومات المرتبطة بها، مثل الموضع وخصائص الخط والألوان.

#### س: ما هي المتطلبات الأساسية لمتابعة هذا البرنامج التعليمي؟

ج: قبل البدء بهذا البرنامج التعليمي، يجب أن يكون لديك فهم أساسي للغة البرمجة C#. بالإضافة إلى ذلك، تحتاج إلى تثبيت Aspose.PDF لمكتبة .NET. يمكنك الحصول عليه من موقع Aspose أو استخدام NuGet لدمجه في مشروعك.

#### س: كيف أقوم بإعداد مشروعي لمتابعة هذا البرنامج التعليمي؟

ج: للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة المفضلة لديك (IDE) وأضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET. سيسمح لك هذا بالوصول إلى وظائف المكتبة في مشروعك.

#### س: كيف يمكنني البحث عن نص معين داخل مستند PDF؟

ج: يمكنك استخدام`TextFragmentAbsorber`للعثور على مثيلات عبارة بحث معينة داخل مستند PDF. من خلال إنشاء مثيل لهذه الفئة وتحديد النص الهدف، يمكنك التقاط كافة تكرارات هذا النص.

#### س: هل يمكنني البحث عن نص في جميع صفحات مستند PDF؟

 ج: نعم، يوضح البرنامج التعليمي كيفية البحث عن نص عبر جميع صفحات مستند PDF. ال`pdfDocument.Pages.Accept(textFragmentAbsorber)` يتم استخدام الطريقة لقبول المستوعب لجميع الصفحات، مما يسمح لك بالبحث عن النص المطلوب في كل صفحة.

#### س: كيف يمكنني الوصول إلى أجزاء النص المستخرجة؟

 ج: بعد البحث عن النص، يمكنك الوصول إلى أجزاء النص المستخرجة باستخدام الملف`TextFragments` ملكية`TextFragmentAbsorber` هدف. توفر هذه الخاصية الوصول إلى مجموعة من`TextFragment` الكائنات التي تحتوي على النص المستخرج والمعلومات ذات الصلة.

#### س: ما هي المعلومات التي يمكنني استرجاعها من أجزاء النص المستخرجة؟

ج: يمكنك استرداد تفاصيل مختلفة من أجزاء النص المستخرجة، مثل محتوى النص الفعلي والموضع (إحداثيات X وY) ومعلومات الخط (الاسم والحجم واللون وما إلى ذلك)، والمزيد. يوضح نموذج التعليمة البرمجية للبرنامج التعليمي كيفية الوصول إلى هذه التفاصيل وطباعتها.

#### س: هل يمكنني تنفيذ المزيد من الإجراءات على أجزاء النص المستخرجة؟

ج: بالتأكيد. بمجرد حصولك على أجزاء النص المستخرجة، يمكنك تعديل التعليمات البرمجية داخل الحلقة لتنفيذ إجراءات مخصصة على كل جزء. يمكن أن يشمل ذلك حفظ النص المستخرج، أو تحليل أنماط النص، أو تطبيق تغييرات التنسيق.