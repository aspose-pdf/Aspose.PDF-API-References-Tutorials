---
title: نص البحث باستخدام Dot Net Regex
linktitle: نص البحث باستخدام Dot Net Regex
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية البحث عن نص باستخدام التعبيرات العادية لـ .NET في مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 480
url: /ar/net/programming-with-text/search-text-with-dot-net-regex/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.PDF لـ .NET للبحث عن نص باستخدام تعبيرات .NET العادية في مستند PDF. يوضح كود المصدر C # المقدم العملية خطوة بخطوة.

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

## الخطوة 3: قم بتعيين المسار إلى دليل المستند

 عيّن المسار إلى دليل المستند الخاص بك باستخدام ملف`dataDir` عامل:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

## الخطوة 4: إنشاء كائن .NET Regex

 إنشاء`.NET Regex` كائن لتعريف نمط البحث:

```csharp
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
```

 يستبدل`@"[\S]+"` بنمط التعبير العادي الذي تريده.

## الخطوة 5: قم بتحميل مستند PDF

 قم بتحميل مستند PDF باستخدام ملف`Document` فصل:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
```

 يستبدل`"SearchTextRegex.pdf"` بالاسم الفعلي لملف PDF الخاص بك.

## الخطوة 6: احصل على صفحة محددة

احصل على الصفحة المطلوبة من المستند:

```csharp
Page page = document.Pages[1];
```

 يستبدل`1` مع رقم الصفحة المطلوب (فهرس 1).

## الخطوة 7: إنشاء TextFragmentAbsorber

 إنشاء`TextFragmentAbsorber`كائن للعثور على جميع مثيلات التعبير العادي للإدخال:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
```

## الخطوة 8: قبول ممتص الصفحة

تقبل الممتص للصفحة:

```csharp
page.Accept(textFragmentAbsorber);
```

## الخطوة 9: استرجع أجزاء النص المستخرجة

 احصل على أجزاء النص المستخرجة باستخدام ملحق`TextFragments` ممتلكات`TextFragmentAbsorber` هدف:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## الخطوة 10: التكرار خلال أجزاء النص

قم بالتكرار خلال أجزاء النص المسترجعة وقم بتنفيذ الإجراءات المطلوبة:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

قم بتعديل الكود داخل الحلقة لتنفيذ مزيد من الإجراءات على كل جزء نصي إذا لزم الأمر.

### نموذج التعليمات البرمجية المصدر لنص البحث باستخدام Dot Net Regex باستخدام Aspose.PDF for .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// قم بإنشاء كائن Regex للعثور على جميع الكلمات
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
// افتح المستند
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
// احصل على صفحة معينة
Page page = document.Pages[1];
// قم بإنشاء كائن TextAbsorber للعثور على جميع مثيلات إدخال regex
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
// تقبل الممتص للصفحة
page.Accept(textFragmentAbsorber);
// احصل على أجزاء النص المستخرجة
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// حلقة من خلال الأجزاء
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية البحث عن نص باستخدام التعبيرات العادية لـ .NET في مستند PDF باستخدام Aspose.PDF for .NET. قدم هذا البرنامج التعليمي دليلاً خطوة بخطوة ، من إعداد المشروع إلى الوصول إلى أجزاء النص المستخرجة. يمكنك الآن دمج هذا الرمز في مشاريع C # الخاصة بك لإجراء عمليات بحث نصية متقدمة في ملفات PDF.