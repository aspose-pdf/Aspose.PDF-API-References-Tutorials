---
title: البحث عن التعبير العادي في ملف PDF
linktitle: البحث عن التعبير العادي في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية البحث عن النص واسترداده باستخدام التعبيرات العادية في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 440
url: /ar/net/programming-with-text/search-regular-expression/
---
يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.PDF لـ .NET للبحث عن النص الذي يطابق التعبير العادي في ملف PDF واسترداده. يوضح كود مصدر C# المقدم العملية خطوة بخطوة.

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
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 تأكد من استبدال`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

## الخطوة 4: البحث باستخدام التعبير العادي

 إنشاء`TextFragmentAbsorber` كائن وقم بتعيين نمط التعبير العادي للعثور على جميع العبارات التي تطابق النمط:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // مثل 1999-2000
```

 يستبدل`"\\d{4}-\\d{4}"` بنمط التعبير العادي الذي تريده.

## الخطوة 5: ضبط خيارات البحث عن النص

 إنشاء`TextSearchOptions` الكائن وتعيينه على`TextSearchOptions` ملكية`TextFragmentAbsorber` كائن لتمكين استخدام التعبير العادي:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## الخطوة 6: البحث في جميع الصفحات

قبول المستوعب لجميع صفحات الوثيقة:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## الخطوة 7: استرداد أجزاء النص المستخرجة

احصل على أجزاء النص المستخرجة باستخدام`TextFragments` ملكية`TextFragmentAbsorber` هدف:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## الخطوة 8: قم بالتمرير خلال أجزاء النص

قم بالمراجعة عبر أجزاء النص المستردة والوصول إلى خصائصها:

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

### نموذج التعليمات البرمجية المصدر للبحث عن التعبير العادي باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
// قم بإنشاء كائن TextAbsorter للعثور على جميع العبارات المطابقة للتعبير العادي
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // مثل 1999-2000
// قم بتعيين خيار البحث عن النص لتحديد استخدام التعبير العادي
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
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

تهانينا! لقد تعلمت بنجاح كيفية البحث عن النص الذي يتطابق مع تعبير عادي في مستند PDF واسترداده باستخدام Aspose.PDF لـ .NET. قدم هذا البرنامج التعليمي دليلاً خطوة بخطوة، بدءًا من تحميل المستند وحتى الوصول إلى أجزاء النص المستخرجة. يمكنك الآن دمج هذا الرمز في مشاريع C# الخاصة بك لإجراء عمليات بحث نصية متقدمة في ملفات PDF.

### الأسئلة الشائعة

#### س: ما هو الغرض من البرنامج التعليمي "البحث عن التعبير العادي في ملف PDF"؟

ج: يهدف البرنامج التعليمي "البحث عن التعبير العادي في ملف PDF" إلى عرض كيفية استخدام مكتبة Aspose.PDF لـ .NET للبحث عن النص الذي يتطابق مع نمط تعبير عادي محدد داخل ملف PDF واستخراجه. يوفر البرنامج التعليمي إرشادات شاملة ونموذجًا لرمز C# لتوضيح العملية.

#### س: كيف يساعد هذا البرنامج التعليمي في البحث عن نص باستخدام التعبيرات العادية في مستند PDF؟

ج: يوفر هذا البرنامج التعليمي طريقة خطوة بخطوة لاستخدام مكتبة Aspose.PDF لإجراء عمليات بحث نصية في مستند PDF استنادًا إلى نمط التعبير العادي. فهو يوضح بالتفصيل كيفية إعداد المشروع، وتحميل مستند PDF، وتحديد نمط التعبير العادي، واسترداد أجزاء النص المطابقة.

#### س: ما هي المتطلبات الأساسية لمتابعة هذا البرنامج التعليمي؟

ج: قبل البدء بهذا البرنامج التعليمي، يجب أن يكون لديك فهم أساسي للغة البرمجة C#. بالإضافة إلى ذلك، تحتاج إلى تثبيت Aspose.PDF لمكتبة .NET. يمكنك الحصول عليه من موقع Aspose أو استخدام NuGet لدمجه في مشروعك.

#### س: كيف أقوم بإعداد مشروعي لمتابعة هذا البرنامج التعليمي؟

ج: للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة المفضلة لديك (IDE) وأضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET. سيسمح لك ذلك بالاستفادة من إمكانيات المكتبة ضمن مشروعك.

#### س: هل يمكنني استخدام التعبيرات العادية للبحث عن نص في مستند PDF؟

 ج: نعم، يوضح هذا البرنامج التعليمي كيفية استخدام التعبيرات العادية للبحث عن نص واستخراجه من مستند PDF. أنها تنطوي على الاستفادة من`TextFragmentAbsorber` فئة وتحديد نمط التعبير العادي للعثور على العبارات التي تطابق النمط المقدم.

#### س: كيف يمكنني تحديد نمط التعبير العادي للبحث عن النص؟

 ج: لتحديد نمط التعبير العادي للبحث عن النص، قم بإنشاء ملف`TextFragmentAbsorber` كائن وتعيين نمطه باستخدام`Text` معامل. استبدل النمط الافتراضي`"\\d{4}-\\d{4}"` في رمز البرنامج التعليمي بنمط التعبير العادي الذي تريده.

#### س: كيف يمكنني تمكين استخدام التعبير العادي للبحث عن النص؟

 ج: يتم تمكين استخدام التعبير العادي عن طريق إنشاء ملف`TextSearchOptions` الكائن وتحديد قيمته`true` . قم بتعيين هذا الكائن إلى`TextSearchOptions` ملكية`TextFragmentAbsorber` مثال. وهذا يضمن تطبيق نمط التعبير العادي أثناء البحث عن النص.

#### س: هل يمكنني استرداد أجزاء النص التي تطابق نمط التعبير العادي؟

 ج: بالتأكيد. بعد تطبيق البحث بالتعبير العادي على مستند PDF، يمكنك استرداد أجزاء النص المستخرجة باستخدام الملف`TextFragments` ملكية`TextFragmentAbsorber` هدف. تحتوي أجزاء النص هذه على مقاطع النص التي تطابق نمط التعبير العادي المحدد.

#### س: ما الذي يمكنني الوصول إليه من أجزاء النص المستردة؟

ج: من أجزاء النص المستردة، يمكنك الوصول إلى خصائص مختلفة مثل محتوى النص المطابق والموضع (إحداثيات X وY) ومعلومات الخط (الاسم والحجم واللون) والمزيد. يوضح نموذج التعليمات البرمجية الموجود في حلقة البرنامج التعليمي كيفية الوصول إلى هذه الخصائص وعرضها.

#### س: كيف يمكنني تخصيص الإجراءات على أجزاء النص المستخرجة؟

ج: بمجرد حصولك على أجزاء النص المستخرجة، يمكنك تخصيص التعليمات البرمجية داخل الحلقة لتنفيذ إجراءات إضافية على كل جزء من النص. يمكن أن يشمل ذلك حفظ النص المستخرج أو تحليل الأنماط أو تنفيذ تغييرات التنسيق بناءً على متطلباتك.