---
title: البحث والحصول على النص كله
linktitle: البحث والحصول على النص كله
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية البحث والحصول على نص من جميع صفحات مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 420
url: /ar/net/programming-with-text/search-and-get-text-all/
---
يوضح هذا البرنامج التعليمي كيفية استخدام Aspose.PDF لـ .NET للبحث عن نص من جميع صفحات مستند PDF والحصول عليه. يوضح كود المصدر C# المقدم العملية خطوة بخطوة.

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
```

## الخطوة 3: تحميل مستند PDF

 قم بتعيين المسار إلى دليل مستند PDF الخاص بك وقم بتحميل المستند باستخدام`Document` فصل:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 تأكد من الاستبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

## الخطوة 4: البحث عن النص واستخراجه

 إنشاء`TextFragmentAbsorber` كائن للعثور على جميع حالات عبارة البحث المدخلة:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 يستبدل`"text"` مع النص الفعلي الذي تريد البحث عنه.

## الخطوة 5: البحث في جميع الصفحات

قبول الامتصاص لجميع صفحات الوثيقة:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## الخطوة 6: الحصول على أجزاء نصية مستخرجة

احصل على أجزاء النص المستخرجة باستخدام`TextFragments` ممتلكات`TextFragmentAbsorber` هدف:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## الخطوة 7: التنقل عبر أجزاء النص

قم بالتنقل عبر أجزاء النص getd والوصول إلى خصائصها:

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

بإمكانك تعديل الكود داخل الحلقة لأداء إجراءات أخرى على كل جزء من النص.

### عينة من كود المصدر للبحث والحصول على النص بالكامل باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// فتح المستند
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// إنشاء كائن TextAbsorber للعثور على جميع حالات عبارة البحث المدخلة
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// قبول الممتص لجميع الصفحات
pdfDocument.Pages.Accept(textFragmentAbsorber);
// احصل على أجزاء النص المستخرجة
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// التنقل عبر الشظايا
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

مبروك! لقد تعلمت بنجاح كيفية البحث عن النص والحصول عليه من جميع صفحات مستند PDF باستخدام Aspose.PDF for .NET. قدم هذا البرنامج التعليمي دليلاً خطوة بخطوة، من تحميل المستند إلى الوصول إلى أجزاء النص المستخرجة. يمكنك الآن دمج هذا الكود في مشاريع C# الخاصة بك لتحليل ومعالجة محتوى النص في ملفات PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "البحث والحصول على النص الكامل"؟

ج: يوضح البرنامج التعليمي "البحث والحصول على النص بالكامل" كيفية استخدام مكتبة Aspose.PDF لـ .NET للبحث عن نص واستخراجه من جميع صفحات مستند PDF. يوفر البرنامج التعليمي تعليمات خطوة بخطوة إلى جانب عينة من كود C# لإجراء البحث عن النص واسترجاعه.

#### س: كيف يساعد هذا البرنامج التعليمي في استخراج النص من مستندات PDF؟

ج: يرشدك هذا البرنامج التعليمي خلال عملية استخراج النص من جميع صفحات مستند PDF. ويستخدم مكتبة Aspose.PDF لتحديد عبارات نصية معينة واسترجاع المعلومات المرتبطة بها، مثل الموضع وخصائص الخط والألوان.

#### س: ما هي المتطلبات الأساسية لمتابعة هذا البرنامج التعليمي؟

ج: قبل البدء في هذا البرنامج التعليمي، يجب أن يكون لديك فهم أساسي للغة البرمجة C#. بالإضافة إلى ذلك، يجب أن يكون لديك مكتبة Aspose.PDF for .NET مثبتة. يمكنك الحصول عليها من موقع Aspose على الويب أو استخدام NuGet لدمجها في مشروعك.

#### س: كيف أقوم بإعداد مشروعي لمتابعة هذا البرنامج التعليمي؟

ج: للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة المفضلة لديك وأضف مرجعًا إلى مكتبة Aspose.PDF for .NET. سيتيح لك هذا الوصول إلى وظائف المكتبة في مشروعك.

#### س: كيف يمكنني البحث عن نص محدد داخل مستند PDF؟

 أ: يمكنك استخدام`TextFragmentAbsorber`فئة للبحث عن حالات عبارة بحث محددة داخل مستند PDF. من خلال إنشاء مثيل لهذه الفئة وتحديد النص المستهدف، يمكنك التقاط جميع حالات هذا النص.

#### س: هل يمكنني البحث عن نص في جميع صفحات مستند PDF؟

 ج: نعم، يوضح البرنامج التعليمي كيفية البحث عن نص عبر جميع صفحات مستند PDF.`pdfDocument.Pages.Accept(textFragmentAbsorber)` يتم استخدام الطريقة لقبول الممتص لجميع الصفحات، مما يسمح لك بالبحث عن النص المطلوب في كل صفحة.

#### س: كيف يمكنني الوصول إلى أجزاء النص المستخرجة؟

 أ: بعد البحث عن النص، يمكنك الوصول إلى أجزاء النص المستخرجة باستخدام`TextFragments` ممتلكات`TextFragmentAbsorber` الكائن. توفر هذه الخاصية إمكانية الوصول إلى مجموعة من`TextFragment` الكائنات التي تحتوي على النص المستخرج والمعلومات ذات الصلة.

#### س: ما هي المعلومات التي يمكنني استرجاعها من أجزاء النص المستخرجة؟

ج: يمكنك استرداد تفاصيل مختلفة من أجزاء النص المستخرجة، مثل محتوى النص الفعلي، والموضع (إحداثيات X وY)، ومعلومات الخط (الاسم والحجم واللون، وما إلى ذلك)، والمزيد. يوضح كود العينة في البرنامج التعليمي كيفية الوصول إلى هذه التفاصيل وطباعتها.

#### س: هل يمكنني تنفيذ إجراءات أخرى على أجزاء النص المستخرجة؟

ج: بالتأكيد. بمجرد استخراج أجزاء النص، يمكنك تعديل الكود داخل الحلقة لتنفيذ إجراءات مخصصة على كل جزء. قد يتضمن هذا حفظ النص المستخرج، أو تحليل أنماط النص، أو تطبيق تغييرات التنسيق.