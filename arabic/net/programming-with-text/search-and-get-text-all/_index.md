---
title: ابحث واحصل على جميع النصوص
linktitle: ابحث واحصل على جميع النصوص
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية البحث والحصول على نص من جميع صفحات مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 420
url: /ar/net/programming-with-text/search-and-get-text-all/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.PDF لـ .NET للبحث والحصول على نص من جميع صفحات مستند PDF. يوضح كود المصدر C # المقدم العملية خطوة بخطوة.

## المتطلبات الأساسية

قبل الشروع في البرنامج التعليمي ، تأكد من أن لديك ما يلي:

- المعرفة الأساسية بلغة البرمجة C #.
- تثبيت Aspose.PDF لمكتبة .NET. يمكنك الحصول عليه من موقع Aspose أو استخدام NuGet لتثبيته في مشروعك.

## الخطوة 1: قم بإعداد المشروع

ابدأ بإنشاء مشروع C # جديد في بيئة التطوير المتكاملة المفضلة لديك (IDE) وأضف مرجعًا إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء الضرورية

أضف التعليمات التالية باستخدام التوجيهات في بداية ملف C # لاستيراد مساحات الأسماء المطلوبة:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## الخطوة 3: قم بتحميل مستند PDF

 عيّن المسار إلى دليل مستند PDF الخاص بك وقم بتحميل المستند باستخدام ملف`Document` فصل:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 تأكد من استبداله`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

## الخطوة 4: البحث عن النص واستخراجه

 إنشاء`TextFragmentAbsorber` كائن للعثور على جميع حالات إدخال عبارة البحث:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 يستبدل`"text"` مع النص الفعلي الذي تريد البحث عنه.

## الخطوة 5: ابحث في جميع الصفحات

قبول الممتص لجميع صفحات المستند:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## الخطوة 6: الحصول على أجزاء نصية مستخرجة

احصل على أجزاء النص المستخرجة باستخدام ملحق`TextFragments` ممتلكات`TextFragmentAbsorber` هدف:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## الخطوة 7: التكرار خلال أجزاء النص

قم بالتكرار خلال أجزاء نص getd والوصول إلى خصائصها:

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

يمكنك تعديل الكود داخل الحلقة لتنفيذ مزيد من الإجراءات على كل جزء نصي.

### عينة من التعليمات البرمجية المصدر للبحث والحصول على جميع النصوص باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
//قم بإنشاء كائن TextAbsorber للعثور على جميع مثيلات عبارة البحث المدخلة
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// تقبل الممتص لجميع الصفحات
pdfDocument.Pages.Accept(textFragmentAbsorber);
// احصل على أجزاء النص المستخرجة
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// حلقة من خلال الأجزاء
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

تهانينا! لقد تعلمت بنجاح كيفية البحث والحصول على نص من جميع صفحات مستند PDF باستخدام Aspose.PDF for .NET. قدم هذا البرنامج التعليمي دليلاً خطوة بخطوة ، من تحميل المستند إلى الوصول إلى أجزاء النص المستخرجة. يمكنك الآن دمج هذا الرمز في مشاريع C # الخاصة بك لتحليل ومعالجة محتوى النص في ملفات PDF.