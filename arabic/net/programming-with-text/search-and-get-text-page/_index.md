---
title: ابحث واحصل على صفحة نصية
linktitle: ابحث واحصل على صفحة نصية
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية البحث والحصول على نص من صفحة معينة من مستند PDF باستخدام Aspose.PDF for .NET.
type: docs
weight: 430
url: /ar/net/programming-with-text/search-and-get-text-page/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.PDF لـ .NET للبحث والحصول على نص من صفحة معينة من مستند PDF. يوضح كود المصدر C # المقدم العملية خطوة بخطوة.

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 تأكد من استبداله`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

## الخطوة 4: ابحث عن نص واستخرجه من الصفحة

 إنشاء`TextFragmentAbsorber` للعثور على جميع مثيلات عبارة البحث المدخلة في صفحة معينة:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 يستبدل`"Figure"` مع النص الفعلي الذي تريد البحث عنه.

## الخطوة 5: البحث في صفحة معينة

قبول الممتص لصفحة معينة من الوثيقة:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## الخطوة 6: الحصول على أجزاء نصية مستخرجة

احصل على أجزاء النص المستخرجة باستخدام ملحق`TextFragments` ممتلكات`TextFragmentAbsorber` هدف:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## الخطوة 7: التكرار خلال أجزاء النص وأجزاءه

قم بالتكرار خلال أجزاء نص getd وشرائحها ، وقم بالوصول إلى خصائصها:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text: {0} ", textSegment.Text);
		Console.WriteLine("Position: {0} ", textSegment.Position);
		Console.WriteLine("XIndent: {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent: {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name: {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible: {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded: {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset: {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size: {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color: {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

يمكنك تعديل الكود داخل الحلقة لأداء مزيد من الإجراءات على كل مقطع نصي.

### نموذج التعليمات البرمجية المصدر لـ Search And Get Text Page باستخدام Aspose.PDF for .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
//قم بإنشاء كائن TextAbsorber للعثور على جميع مثيلات عبارة البحث المدخلة
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// تقبل الممتص لجميع الصفحات
pdfDocument.Pages.Accept(textFragmentAbsorber);
// احصل على أجزاء النص المستخرجة
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// حلقة من خلال الأجزاء
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية البحث والحصول على نص من صفحة معينة من مستند PDF باستخدام Aspose.PDF for .NET. قدم هذا البرنامج التعليمي دليلاً خطوة بخطوة ، من تحميل المستند إلى الوصول إلى مقاطع النص المستخرجة. يمكنك الآن دمج ملفات