---
title: مقاطع نصية
linktitle: مقاطع نصية
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية البحث عن مقاطع نصية معينة داخل مستند PDF باستخدام التعبيرات العادية في Aspose.PDF for .NET.
type: docs
weight: 540
url: /ar/net/programming-with-text/text-segments/
---

يشرح هذا البرنامج التعليمي كيفية البحث عن مقاطع نصية معينة داخل مستند PDF باستخدام Aspose.PDF لـ .NET. يوضح كود المصدر C # المقدم سيناريوهات مختلفة باستخدام التعبيرات العادية.

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

## الخطوة 3: استخدم TextFragmentAbsorber للبحث عن النص

 إنشاء`TextFragmentAbsorber`للبحث عن مقاطع نصية محددة باستخدام التعبيرات العادية:

```csharp
TextFragmentAbsorber textFragmentAbsorber;
```

## الخطوة 4: إجراء عمليات بحث نصية باستخدام التعبيرات العادية

قم بإجراء عمليات بحث عن النص بناءً على سيناريوهات مختلفة باستخدام التعبيرات العادية. وفيما يلي بعض الأمثلة على ذلك:

- للبحث عن تطابق تام للكلمة: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"\bWord\b", new TextSearchOptions(true));
```

- للبحث عن سلسلة بأحرف كبيرة أو صغيرة: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber("(?i)Line", new TextSearchOptions(true));
```

- للبحث عن كل السلاسل داخل مستند PDF: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

- للبحث عن نص بعد سلسلة معينة حتى فاصل أسطر: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(?i)the ((.)*)");
```

- للعثور على نص بعد تطابق regex: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(?<=word).*");
```

- للبحث عن الارتباطات التشعبية / عناوين URL داخل مستند PDF: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(http|ftp|https):\/\/([\w\-_]+(?:(?:\.[\w\-_]+)+))([\w\-\.,@?^=%&amp;:/~\+#]*[\w\-\@?^=%&amp;/~\+#])?");
```

استبدل التعبيرات العادية بأنماط البحث التي تريدها.

## الخطوة 5: قم بإجراء البحث ومعالجة النتائج

 قم بإجراء البحث باستخدام ملف`TextFragmentAbsorber` الاعتراض على النتائج ومعالجتها بناءً على متطلباتك.

### نموذج التعليمات البرمجية المصدر لمقاطع النص باستخدام Aspose.PDF لـ .NET 
```csharp
TextFragmentAbsorber textFragmentAbsorber;
// للبحث في المطابقة التامة للكلمة ، يمكنك التفكير في استخدام التعبير العادي.
textFragmentAbsorber = new TextFragmentAbsorber(@"\bWord\b", new TextSearchOptions(true));
//من أجل البحث عن سلسلة بأحرف كبيرة أو صغيرة ، يمكنك التفكير في استخدام تعبير عادي.
textFragmentAbsorber = new TextFragmentAbsorber("(?i)Line", new TextSearchOptions(true));
// من أجل البحث في جميع السلاسل (تحليل كل السلاسل) داخل مستند PDF ، يرجى محاولة استخدام التعبير العادي التالي.
textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
// ابحث عن تطابق في سلسلة البحث واحصل على أي شيء بعد السلسلة حتى فاصل السطر.
textFragmentAbsorber = new TextFragmentAbsorber(@"(?i)the ((.)*)");
// الرجاء استخدام التعبير العادي التالي للعثور على النص التالي لمطابقة regex.
textFragmentAbsorber = new TextFragmentAbsorber(@"(?<=word).*");
// من أجل البحث في مستند PDF الموجود داخل الارتباط التشعبي / URL ، يرجى محاولة استخدام التعبير العادي التالي.
textFragmentAbsorber = new TextFragmentAbsorber(@"(http|ftp|https):\/\/([\w\-_]+(?:(?:\.[\w\-_]+)+))([\w\-\.,@?^=%&amp;:/~\+#]*[\w\-\@?^=%&amp;/~\+#])?");
```


## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية البحث عن مقاطع نصية معينة داخل مستند PDF باستخدام Aspose.PDF لـ .NET. قدم هذا البرنامج التعليمي أمثلة على سيناريوهات البحث المختلفة باستخدام التعبيرات العادية. يمكنك الآن دمج هذا الرمز في مشاريع C # الخاصة بك للبحث عن مقاطع النص ومعالجتها في ملفات PDF.