---
title: استخراج النص من منطقة الصفحة في ملف PDF
linktitle: استخراج النص من منطقة الصفحة في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخراج النص من منطقة معينة على صفحة في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 190
url: /ar/net/programming-with-text/extract-text-from-page-region/
---
سيرشدك هذا البرنامج التعليمي خلال عملية استخراج النص من منطقة معينة على صفحة في ملف PDF باستخدام Aspose.PDF لـ .NET. يوضح كود مصدر C# المقدم الخطوات اللازمة.

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
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## الخطوة 5: استخراج النص من منطقة الصفحة
 إنشاء`TextAbsorber` كائن لاستخراج النص من المستند. تكوين`TextSearchOptions` لقصر البحث على منطقة صفحة معينة محددة بواسطة مستطيل.

```csharp
TextAbsorber absorb = new TextAbsorber();
absorb.TextSearchOptions.LimitToPageBounds = true;
absorb.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
pdfDocument.Pages[1].Accept(absorb);
```

## الخطوة 6: الحصول على النص المستخرج
 الوصول إلى النص المستخرج من`TextAbsorber` هدف.

```csharp
string extractedText = absorb.Text;
```

## الخطوة 7: احفظ النص المستخرج
 إنشاء`TextWriter` وافتح الملف الذي تريد حفظ النص المستخرج فيه. اكتب النص المستخرج إلى الملف وأغلق الدفق.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### نموذج التعليمات البرمجية المصدر لاستخراج النص من منطقة الصفحة باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// قم بإنشاء كائن TextAbsorter لاستخراج النص
TextAbsorber absorber = new TextAbsorber();
absorber.TextSearchOptions.LimitToPageBounds = true;
absorber.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
// قبول الممتص للصفحة الأولى
pdfDocument.Pages[1].Accept(absorber);
// الحصول على النص المستخرج
string extractedText = absorber.Text;
// إنشاء كاتب وفتح الملف
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// اكتب سطرًا من النص إلى الملف
tw.WriteLine(extractedText);
// أغلق الدفق
tw.Close();
```

## خاتمة
لقد نجحت في استخراج النص من منطقة معينة في صفحة مستند PDF باستخدام Aspose.PDF لـ .NET. تم حفظ النص المستخرج في ملف الإخراج المحدد.

### الأسئلة الشائعة

#### س: ما هو الغرض من هذا البرنامج التعليمي؟

ج: يهدف هذا البرنامج التعليمي إلى إرشادك خلال عملية استخراج النص من منطقة معينة على صفحة في ملف PDF باستخدام Aspose.PDF لـ .NET. يوفر كود مصدر C# المصاحب إرشادات خطوة بخطوة لإنجاز هذه المهمة.

#### س: ما هي مساحات الأسماء التي يجب علي استيرادها؟

ج: في ملف التعليمات البرمجية الذي تنوي استخراج النص منه، قم بتضمين ما يلي باستخدام التوجيهات في بداية الملف:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### س: كيف أحدد دليل المستندات؟

 ج: تحديد موقع الخط`string dataDir = "YOUR DOCUMENT DIRECTORY";` في التعليمات البرمجية واستبدال`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

#### س: كيف يمكنني فتح مستند PDF موجود؟

 ج: في الخطوة 4، ستفتح مستند PDF موجودًا باستخدام الملف`Document` منشئ وتوفير المسار إلى ملف PDF الإدخال.

#### س: كيف يمكنني استخراج النص من منطقة صفحة معينة؟

 ج: تتضمن الخطوة 5 إنشاء ملف`TextAbsorber`كائن لاستخراج النص من وثيقة PDF. ستقوم بعد ذلك بتكوين`TextSearchOptions` لتحديد منطقة مستطيلة معينة على الصفحة باستخدام الإحداثيات.

#### س: كيف يمكنني الوصول إلى النص المستخرج؟

 ج: ترشدك الخطوة 6 إلى كيفية الوصول إلى النص المستخرج من ملف`TextAbsorber` هدف.

#### س: كيف يمكنني حفظ النص المستخرج في ملف؟

 ج: في الخطوة 7، ستقوم بإنشاء ملف`TextWriter`، وافتح الملف الذي تريد حفظ النص المستخرج فيه، واكتب النص المستخرج في الملف، ثم أغلق الدفق.

#### س: ما هي الوجبات الرئيسية من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، تعلمت كيفية استخراج النص من منطقة معينة على صفحة مستند PDF باستخدام Aspose.PDF لـ .NET. تم حفظ النص المستخرج في ملف إخراج محدد، مما يسمح لك باستهداف المحتوى النصي المطلوب وتحليله بدقة.