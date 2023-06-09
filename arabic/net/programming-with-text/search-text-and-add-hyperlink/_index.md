---
title: نص البحث وإضافة ارتباط تشعبي
linktitle: نص البحث وإضافة ارتباط تشعبي
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية البحث عن نص في ملف PDF وإضافة ارتباطات تشعبية إلى النص الموجود وحفظ المستند المعدل باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 450
url: /ar/net/programming-with-text/search-text-and-add-hyperlink/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.PDF لـ .NET للبحث عن نص معين في مستند PDF وإضافة ارتباط تشعبي إلى النص الموجود وحفظ المستند المعدل. يوضح كود المصدر C # المقدم العملية خطوة بخطوة.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## الخطوة 3: قم بتعيين المسار إلى دليل المستند

 عيّن المسار إلى دليل المستند الخاص بك باستخدام ملف`dataDir` عامل:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

## الخطوة 4: إنشاء TextFragmentAbsorber

 إنشاء`TextFragmentAbsorber` كائن للعثور على جميع حالات إدخال عبارة البحث:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 يستبدل`"\\d{4}-\\d{4}"` بنمط التعبير العادي الذي تريده.

## الخطوة 5: تمكين البحث عن التعبير العادي

تمكين البحث عن التعبير العادي عن طريق تعيين`TextSearchOptions` خاصية الممتص:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## الخطوة 6: افتح وربط وثيقة PDF

 إنشاء`PdfContentEditor` كائن وربطه بملف PDF المصدر:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 يستبدل`"SearchRegularExpressionPage.pdf"` بالاسم الفعلي لملف PDF الخاص بك.

## الخطوة السابعة: قبول ممتص الصفحة

اقبل الممتص للصفحة المطلوبة من المستند:

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 يستبدل`1` برقم الصفحة المطلوب.

## الخطوة 8: أضف ارتباطات تشعبية إلى النص الموجود

قم بالتكرار خلال أجزاء النص المستردة وأضف ارتباطات تشعبية إليها:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // قم بإنشاء مستطيل بناءً على موضع جزء النص
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    // أضف رابط ويب إلى المستطيل
    editor.CreateWebLink(rect, "http://www.aspose.com "، 1، System.Drawing.Color.Blue) ؛
}
```

 يستبدل`"http://www.aspose.com"` مع URL الارتباط التشعبي المطلوب.

## الخطوة 9: احفظ وأغلق المستند المعدل

احفظ المستند المعدل وأغلق المحرر:

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

 تأكد من استبداله`"SearchTextAndAddHyperlink_out.pdf"` باسم ملف الإخراج المطلوب.

### عينة من التعليمات البرمجية المصدر للبحث عن النص وإضافة ارتباط تشعبي باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// قم بإنشاء كائن ممتص للعثور على جميع مثيلات عبارة البحث المدخلة
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// تمكين البحث عن التعبير العادي
absorber.TextSearchOptions = new TextSearchOptions(true);
// افتح المستند
PdfContentEditor editor = new PdfContentEditor();
//ربط ملف PDF المصدر
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// تقبل الممتص للصفحة
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// حلقة من خلال الأجزاء
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http:// Www.aspose.com "، 1، blue، actionName) ؛
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية البحث عن نص معين في مستند PDF وإضافة ارتباطات تشعبية إلى النص الموجود وحفظ المستند المعدل باستخدام Aspose.PDF لـ .NET. قدم هذا البرنامج التعليمي دليلاً تفصيليًا ، بدءًا من إعداد المشروع وحتى تنفيذ الإجراءات المطلوبة. يمكنك الآن دمج هذا الرمز في مشاريع C # الخاصة بك لمعالجة النص وإضافة ارتباطات تشعبية في ملفات PDF.