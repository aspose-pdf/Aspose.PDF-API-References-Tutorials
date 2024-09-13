---
title: إضافة HTML باستخدام DOM
linktitle: إضافة HTML باستخدام DOM
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية إضافة محتوى HTML باستخدام DOM في Aspose.PDF لـ .NET.
type: docs
weight: 40
url: /ar/net/programming-with-text/add-html-using-dom/
---
سيرشدك هذا البرنامج التعليمي خلال عملية إضافة محتوى HTML باستخدام DOM (نموذج كائن المستند) في Aspose.PDF لـ .NET. يوضح كود المصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مُجمِّع C# آخر مُثبت على جهازك.
- مكتبة Aspose.PDF لـ .NET. يمكنك تنزيلها من موقع Aspose الرسمي أو استخدام مدير حزم مثل NuGet لتثبيتها.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. أضف مرجعًا إلى مكتبة Aspose.PDF لـ .NET.

## الخطوة 2: استيراد المساحات المطلوبة
في ملف الكود الذي تريد إضافة محتوى HTML إليه، أضف ما يلي باستخدام التوجيهات في الجزء العلوي من الملف:

```csharp
using Aspose.Pdf;
```

## الخطوة 3: تعيين دليل المستند ومسار ملف الإخراج
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل الذي يتم تخزين مستنداتك فيه.

## الخطوة 4: إنشاء كائن مستند جديد
 إنشاء مثيل جديد`Document` الكائن عن طريق إضافة سطر التعليمات البرمجية التالي:

```csharp
Document doc = new Document();
```

## الخطوة 5: إضافة صفحة إلى المستند
 أضف صفحة جديدة إلى المستند باستخدام`Add` طريقة`Pages` المجموعة. في الكود المقدم، يتم تعيين الصفحة الجديدة للمتغير`page`.

```csharp
Page page = doc.Pages.Add();
```

## الخطوة 6: إنشاء HtmlFragment بمحتوى HTML
 إنشاء مثيل`HtmlFragment` الكائن وتوفير محتوى HTML المطلوب. في الكود المقدم، يتم تعيين محتوى HTML للمتغير`titel`يمكنك تعديل محتوى HTML حسب الحاجة.

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

## الخطوة 7: تعيين معلومات الهامش
اضبط الهامش السفلي والعلوي لشظية HTML إذا لزم الأمر. في الكود المقدم، يتم تعيين الهامش السفلي على 10 والهامش العلوي على 200.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 200;
```

## الخطوة 8: أضف HtmlFragment إلى الصفحة
 أضف`HtmlFragment` الاعتراض على مجموعة الفقرات في الصفحة.

```csharp
page.Paragraphs.Add(title);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

## الخطوة 9: احفظ مستند PDF
 احفظ مستند PDF باستخدام`Save` طريقة`Document` حدد مسار ملف الإخراج الذي قمت بتعيينه في الخطوة 3.

```csharp
doc.Save(dataDir);
```

## الخطوة 10: عرض رسالة النجاح
عرض رسالة النجاح مع المسار الذي تم حفظ ملف PDF فيه.

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

### عينة من كود المصدر لإضافة HTML باستخدام DOM باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء كائن مستند
Document doc = new Document();
// إضافة صفحة إلى مجموعة صفحات ملف PDF
Page page = doc.Pages.Add();
// إنشاء مثيل لـ HtmlFragment باستخدام عناصر HTML
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
// تعيين معلومات الهامش السفلي
titel.Margin.Bottom = 10;
// تعيين معلومات الهامش العلوي
titel.Margin.Top = 200;
// إضافة جزء HTML إلى مجموعة فقرات الصفحة
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
// حفظ ملف PDF
doc.Save(dataDir);
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

## خاتمة
لقد قمت بنجاح بإضافة محتوى HTML باستخدام DOM في Aspose.PDF لـ .NET. يمكنك الآن العثور على ملف PDF الناتج في مسار ملف الإخراج المحدد.

### الأسئلة الشائعة

#### س: ما هو هدف هذا البرنامج التعليمي؟

ج: يهدف هذا البرنامج التعليمي إلى تقديم دليل خطوة بخطوة حول كيفية إضافة محتوى HTML إلى مستند PDF باستخدام نموذج كائن المستند (DOM) في Aspose.PDF لـ .NET. وهو يتضمن مقتطفات من التعليمات البرمجية المصدرية بلغة C# لمساعدتك على فهم العملية وتنفيذها.

#### س: ما هي المساحات الأسماء التي أحتاج إلى استيرادها لهذا البرنامج التعليمي؟

أ: في ملف الكود الذي تخطط لإضافة محتوى HTML إليه، قم باستيراد مساحة الأسماء التالية في بداية الملف:

```csharp
using Aspose.Pdf;
```

#### س: كيف يمكنني تحديد دليل المستند ومسار ملف الإخراج؟

 أ: في الكود، ابحث عن السطر`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدالها`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

#### س: كيف أقوم بإنشاء كائن مستند؟

 أ: في الخطوة 4، قم بإنشاء مثيل جديد`Document` الكائن عن طريق إضافة سطر التعليمات البرمجية التالي:

```csharp
Document doc = new Document();
```

#### س: كيف أضيف صفحة إلى المستند؟

 أ: في الخطوة 5، ستضيف صفحة جديدة إلى المستند باستخدام`Add` طريقة`Pages` مجموعة:

```csharp
Page page = doc.Pages.Add();
```

#### س: كيف يمكنني تعيين محتوى HTML باستخدام DOM؟

 أ: في الخطوة 6، ستقوم بإنشاء`HtmlFragment` الكائن وتعيين محتوى HTML المطلوب إليه. يتم تعيين محتوى HTML إلى المتغير`titel`:

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

#### س: هل يمكنني تعديل هامش المحتوى HTML؟

ج: نعم، في الخطوة 7، يمكنك ضبط الهوامش السفلية والعلوية لشظية HTML حسب الحاجة:

```csharp
titel.Margin.Bottom = 10;
titel.Margin.Top = 200;
```

#### س: كيف أضيف HTMLFragment إلى مستند PDF؟

 أ: في الخطوة 8، ستضيف`HtmlFragment` هدف (`titel`) إلى مجموعة فقرات الصفحة:

```csharp
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

#### س: كيف أحفظ مستند PDF الناتج؟

 أ: بعد إضافة محتوى HTML وضبط الهوامش، استخدم`Save` طريقة`Document` كائن لحفظ مستند PDF:

```csharp
doc.Save(dataDir);
```

#### س: هل هناك طريقة للتأكد من نجاح العملية؟

ج: بالتأكيد، في الخطوة 10، يتم عرض رسالة نجاح مع المسار الذي تم حفظ ملف PDF فيه:

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

#### س: ما هو أهم ما يمكن تعلمه من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، تكون قد تعلمت بنجاح كيفية استخدام نموذج كائن المستند (DOM) في Aspose.PDF لـ .NET لإضافة محتوى HTML إلى مستند PDF. تمكنك هذه المعرفة من تحسين قدراتك على إنشاء ملفات PDF.