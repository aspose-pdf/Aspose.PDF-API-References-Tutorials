---
title: البحث عن تعبير عادي في ملف PDF
linktitle: البحث عن تعبير عادي في ملف PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية البحث عن النص واسترجاعه باستخدام التعبيرات العادية في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 440
url: /ar/net/programming-with-text/search-regular-expression/
---
يوضح هذا البرنامج التعليمي كيفية استخدام Aspose.PDF لـ .NET للبحث عن واسترجاع النص الذي يتطابق مع تعبير عادي في ملف PDF. يوضح كود المصدر C# المقدم العملية خطوة بخطوة.

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
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 تأكد من الاستبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

## الخطوة 4: البحث باستخدام التعبيرات العادية

 إنشاء`TextFragmentAbsorber` الكائن وتعيين نمط التعبير العادي للعثور على جميع العبارات التي تطابق النمط:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // مثل 1999-2000
```

 يستبدل`"\\d{4}-\\d{4}"` مع نمط التعبير العادي المطلوب.

## الخطوة 5: تعيين خيارات البحث النصي

 إنشاء`TextSearchOptions` الكائن وضبطه على`TextSearchOptions` ممتلكات`TextFragmentAbsorber` كائن لتمكين استخدام التعابير العادية:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## الخطوة 6: البحث في جميع الصفحات

قبول الامتصاص لجميع صفحات الوثيقة:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## الخطوة 7: استرداد أجزاء النص المستخرجة

 احصل على أجزاء النص المستخرجة باستخدام`TextFragments` ممتلكات`TextFragmentAbsorber` هدف:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## الخطوة 8: التنقل عبر أجزاء النص

قم بالتنقل عبر أجزاء النص المسترجعة والوصول إلى خصائصها:

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

### عينة من كود المصدر لتعبير البحث العادي باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// فتح المستند
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
//إنشاء كائن TextAbsorber للعثور على جميع العبارات المطابقة للتعبير العادي
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // مثل 1999-2000
// تعيين خيار البحث النصي لتحديد استخدام التعبيرات العادية
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
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

مبروك! لقد تعلمت بنجاح كيفية البحث عن نص يطابق تعبيرًا عاديًا في مستند PDF واسترجاعه باستخدام Aspose.PDF for .NET. قدم هذا البرنامج التعليمي دليلًا خطوة بخطوة، من تحميل المستند إلى الوصول إلى أجزاء النص المستخرجة. يمكنك الآن دمج هذا الكود في مشاريع C# الخاصة بك لإجراء عمليات بحث متقدمة عن النصوص في ملفات PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "البحث عن تعبير عادي في ملف PDF"؟

أ: يهدف البرنامج التعليمي "البحث عن تعبير عادي في ملف PDF" إلى عرض كيفية استخدام مكتبة Aspose.PDF لـ .NET للبحث عن واستخراج نص يطابق نمط تعبير عادي محدد داخل ملف PDF. يوفر البرنامج التعليمي إرشادات شاملة وعينة من كود C# لتوضيح العملية.

#### س: كيف يساعد هذا البرنامج التعليمي في البحث عن نص باستخدام التعبيرات العادية في مستند PDF؟

ج: يوفر هذا البرنامج التعليمي نهجًا خطوة بخطوة لاستخدام مكتبة Aspose.PDF لإجراء عمليات بحث نصية في مستند PDF استنادًا إلى نمط تعبير عادي. ويوضح بالتفصيل كيفية إعداد المشروع وتحميل مستند PDF وتحديد نمط تعبير عادي واسترداد أجزاء النص المطابقة.

#### س: ما هي المتطلبات الأساسية لمتابعة هذا البرنامج التعليمي؟

ج: قبل البدء في هذا البرنامج التعليمي، يجب أن يكون لديك فهم أساسي للغة البرمجة C#. بالإضافة إلى ذلك، يجب أن يكون لديك مكتبة Aspose.PDF for .NET مثبتة. يمكنك الحصول عليها من موقع Aspose على الويب أو استخدام NuGet لدمجها في مشروعك.

#### س: كيف أقوم بإعداد مشروعي لمتابعة هذا البرنامج التعليمي؟

ج: للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة المفضلة لديك وأضف مرجعًا إلى مكتبة Aspose.PDF for .NET. سيتيح لك هذا الاستفادة من إمكانيات المكتبة داخل مشروعك.

#### س: هل يمكنني استخدام التعبيرات العادية للبحث عن نص في مستند PDF؟

 ج: نعم، يوضح هذا البرنامج التعليمي كيفية استخدام التعبيرات العادية للبحث عن نص واستخراجه من مستند PDF. ويتضمن ذلك الاستفادة من`TextFragmentAbsorber` الفئة وتحديد نمط تعبير منتظم للعثور على العبارات التي تطابق النمط المقدم.

#### س: كيف أقوم بتعريف نمط التعبير العادي للبحث النصي؟

 أ: لتحديد نمط تعبير منتظم للبحث النصي، قم بإنشاء`TextFragmentAbsorber` الكائن وتعيين نمطه باستخدام`Text` المعلمة. استبدال النمط الافتراضي`"\\d{4}-\\d{4}"` في كود البرنامج التعليمي باستخدام نمط التعبير العادي المطلوب.

#### س: كيف يمكنني تمكين استخدام التعبيرات العادية للبحث النصي؟

 أ: يتم تمكين استخدام التعابير العادية عن طريق إنشاء`TextSearchOptions` الكائن وتعيين قيمته إلى`true` . تعيين هذا الكائن إلى`TextSearchOptions` ممتلكات`TextFragmentAbsorber` يضمن هذا تطبيق نمط التعبير العادي أثناء البحث عن النص.

#### س: هل يمكنني استرجاع أجزاء النص التي تتطابق مع نمط التعبير العادي؟

 ج: بالتأكيد. بعد تطبيق البحث باستخدام التعبيرات العادية على مستند PDF، يمكنك استرداد أجزاء النص المستخرجة باستخدام`TextFragments` ممتلكات`TextFragmentAbsorber` تحتوي أجزاء النص هذه على أجزاء نصية تتطابق مع نمط التعبير العادي المحدد.

#### س: ما الذي يمكنني الوصول إليه من أجزاء النص المسترجعة؟

ج: من خلال أجزاء النص المسترجعة، يمكنك الوصول إلى خصائص مختلفة مثل محتوى النص المطابق، والموضع (إحداثيات X وY)، ومعلومات الخط (الاسم والحجم واللون)، والمزيد. يوضح الكود النموذجي داخل حلقة البرنامج التعليمي كيفية الوصول إلى هذه الخصائص وعرضها.

#### س: كيف يمكنني تخصيص الإجراءات على أجزاء النص المستخرجة؟

ج: بمجرد استخراج أجزاء النص، يمكنك تخصيص الكود داخل الحلقة لتنفيذ إجراءات إضافية على كل جزء من النص. وقد يتضمن ذلك حفظ النص المستخرج، أو تحليل الأنماط، أو تنفيذ تغييرات التنسيق بناءً على متطلباتك.