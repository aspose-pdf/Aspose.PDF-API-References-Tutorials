---
title: استخراج صفحة النص في ملف PDF
linktitle: استخراج صفحة النص في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخراج النص من صفحة معينة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 200
url: /ar/net/programming-with-text/extract-text-page/
---
سيرشدك هذا البرنامج التعليمي خلال عملية استخراج النص من صفحة معينة في ملف PDF باستخدام Aspose.PDF لـ .NET. يوضح كود مصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مترجم C# آخر مثبت على جهازك.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير الحزم مثل NuGet لتثبيته.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء المطلوبة
في ملف التعليمات البرمجية الذي تريد استخراج النص منه، أضف ما يلي باستخدام التوجيهات الموجودة في الجزء العلوي من الملف:

```csharp
using Aspose.Pdf;
using System.IO;
```

## الخطوة 3: قم بتعيين دليل المستند
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يتم تخزين المستندات الخاصة بك.

## الخطوة 4: افتح مستند PDF
 افتح مستند PDF موجود باستخدام الملف`Document`منشئ وتمرير المسار إلى ملف PDF الإدخال.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## الخطوة 5: استخراج النص من صفحة معينة
 إنشاء`TextAbsorber` كائن لاستخراج النص من المستند. قم بقبول المستوعب للصفحة المطلوبة عن طريق الوصول إليها من خلال`Pages` جمع من`pdfDocument`.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages[1].Accept(textAbsorber);
```

## الخطوة 6: الحصول على النص المستخرج
 الوصول إلى النص المستخرج من`TextAbsorber` هدف.

```csharp
string extractedText = textAbsorber.Text;
```

## الخطوة 7: احفظ النص المستخرج
 إنشاء`TextWriter` وافتح الملف الذي تريد حفظ النص المستخرج فيه. اكتب النص المستخرج إلى الملف وأغلق الدفق.

```csharp
dataDir = dataDir + "extracted-text_out.txt";
TextWriter tw = new StreamWriter(dataDir);
tw.WriteLine(extractedText);
tw. Close();
```

### نموذج التعليمات البرمجية المصدر لاستخراج صفحة نصية باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
// قم بإنشاء كائن TextAbsorter لاستخراج النص
TextAbsorber textAbsorber = new TextAbsorber();
//قبول الممتص لصفحة معينة
pdfDocument.Pages[1].Accept(textAbsorber);
// الحصول على النص المستخرج
string extractedText = textAbsorber.Text;
dataDir = dataDir + "extracted-text_out.txt";
// إنشاء كاتب وفتح الملف
TextWriter tw = new StreamWriter(dataDir);
// اكتب سطرًا من النص إلى الملف
tw.WriteLine(extractedText);
// أغلق الدفق
tw.Close();
Console.WriteLine("\nText extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## خاتمة
لقد نجحت في استخراج النص من صفحة معينة من مستند PDF باستخدام Aspose.PDF لـ .NET. تم حفظ النص المستخرج في ملف الإخراج المحدد.

### الأسئلة الشائعة

#### س: ما هو الغرض من هذا البرنامج التعليمي؟

ج: يرشدك هذا البرنامج التعليمي خلال عملية استخراج النص من صفحة معينة في ملف PDF باستخدام Aspose.PDF لـ .NET. يوضح كود مصدر C# المصاحب الخطوات المطلوبة لتحقيق هذه المهمة.

#### س: ما هي مساحات الأسماء التي يجب علي استيرادها؟

ج: في ملف التعليمات البرمجية الذي تخطط لاستخراج النص منه، قم بتضمين ما يلي باستخدام التوجيهات في بداية الملف:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### س: كيف أحدد دليل المستندات؟

 ج: في الكود، ابحث عن السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدال`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

#### س: كيف يمكنني فتح مستند PDF موجود؟

 ج: في الخطوة 4، ستفتح مستند PDF موجودًا باستخدام الملف`Document` منشئ وتوفير المسار إلى ملف PDF الإدخال.

#### س: كيف يمكنني استخراج النص من صفحة معينة؟

 ج: تتضمن الخطوة 5 إنشاء ملف`TextAbsorber` كائن لاستخراج النص من وثيقة PDF. ستقوم بعد ذلك بقبول المستوعب للصفحة المطلوبة عن طريق الوصول إليها من خلال`Pages` جمع من`pdfDocument`.

#### س: كيف يمكنني الوصول إلى النص المستخرج؟

 ج: ترشدك الخطوة 6 إلى كيفية الوصول إلى النص المستخرج من ملف`TextAbsorber` هدف.

#### س: كيف يمكنني حفظ النص المستخرج في ملف؟

 ج: في الخطوة 7، ستقوم بإنشاء ملف`TextWriter`، وافتح الملف الذي تريد حفظ النص المستخرج فيه، واكتب النص المستخرج في الملف، ثم أغلق الدفق.

#### س: ما هي الوجبات الرئيسية من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، تعلمت كيفية استخراج النص من صفحة معينة في مستند PDF باستخدام Aspose.PDF لـ .NET. تم حفظ النص المستخرج في ملف إخراج محدد، مما يتيح لك استهداف محتوى النص وتحليله من صفحات محددة.