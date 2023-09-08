---
title: إضافة HTML باستخدام DOM
linktitle: إضافة HTML باستخدام DOM
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية إضافة محتوى HTML باستخدام DOM في Aspose.PDF لـ .NET.
type: docs
weight: 40
url: /ar/net/programming-with-text/add-html-using-dom/
---
سيرشدك هذا البرنامج التعليمي خلال عملية إضافة محتوى HTML باستخدام DOM (نموذج كائن المستند) في Aspose.PDF لـ .NET. يوضح كود مصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مترجم C# آخر مثبت على جهازك.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير الحزم مثل NuGet لتثبيته.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء المطلوبة
في ملف التعليمات البرمجية الذي تريد إضافة محتوى HTML إليه، أضف ما يلي باستخدام التوجيهات الموجودة أعلى الملف:

```csharp
using Aspose.Pdf;
```

## الخطوة 3: قم بتعيين دليل المستند ومسار ملف الإخراج
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يتم تخزين المستندات الخاصة بك.

## الخطوة 4: إنشاء كائن مستند جديد
 إنشاء مثيل جديد`Document` كائن عن طريق إضافة السطر التالي من التعليمات البرمجية:

```csharp
Document doc = new Document();
```

## الخطوة 5: إضافة صفحة إلى المستند
 أضف صفحة جديدة إلى المستند باستخدام`Add` طريقة`Pages`مجموعة. في الكود المقدم، يتم تعيين الصفحة الجديدة للمتغير`page`.

```csharp
Page page = doc.Pages.Add();
```

## الخطوة 6: إنشاء HtmlFragment بمحتوى HTML
 إنشاء مثيل ل`HtmlFragment` الكائن وتوفير محتوى HTML المطلوب. في التعليمات البرمجية المقدمة، يتم تعيين محتوى HTML للمتغير`titel`. يمكنك تعديل محتوى HTML حسب الحاجة.

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

## الخطوة 7: تعيين معلومات الهامش
اضبط الهامش السفلي والعلوي لجزء HTML إذا لزم الأمر. في الكود المقدم، تم تعيين الهامش السفلي على 10 والهامش العلوي على 200.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 200;
```

## الخطوة 8: أضف HtmlFragment إلى الصفحة
 أضف ال`HtmlFragment` الاعتراض على مجموعة الفقرات من الصفحة.

```csharp
page.Paragraphs.Add(title);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

## الخطوة 9: احفظ مستند PDF
 احفظ مستند PDF باستخدام`Save` طريقة`Document` هدف. حدد مسار ملف الإخراج الذي قمت بتعيينه في الخطوة 3.

```csharp
doc.Save(dataDir);
```

## الخطوة 10: عرض رسالة النجاح
اعرض رسالة نجاح مع المسار الذي تم حفظ ملف PDF فيه.

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

### نموذج التعليمات البرمجية المصدر لإضافة HTMLUsing DOM باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// إنشاء مثيل لكائن المستند
Document doc = new Document();
// إضافة صفحة إلى مجموعة الصفحات من ملف PDF
Page page = doc.Pages.Add();
// إنشاء مثيل لـ HtmlFragment باستخدام شبكات HTML
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
// تعيين معلومات الهامش السفلي
titel.Margin.Bottom = 10;
// تعيين معلومات الهامش العلوي
titel.Margin.Top = 200;
// إضافة جزء HTML إلى مجموعة الفقرات من الصفحة
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
// حفظ ملف PDF
doc.Save(dataDir);
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

## خاتمة
لقد نجحت في إضافة محتوى HTML باستخدام DOM في Aspose.PDF لـ .NET. يمكن الآن العثور على ملف PDF الناتج في مسار ملف الإخراج المحدد.

### الأسئلة الشائعة

#### س: ما هو الهدف من هذا البرنامج التعليمي؟

ج: يهدف هذا البرنامج التعليمي إلى تقديم دليل خطوة بخطوة حول كيفية إضافة محتوى HTML إلى مستند PDF باستخدام نموذج كائن المستند (DOM) في Aspose.PDF لـ .NET. يتضمن مقتطفات من التعليمات البرمجية المصدر لـ C# لمساعدتك على فهم العملية وتنفيذها.

#### س: ما هي مساحات الأسماء التي أحتاج إلى استيرادها لهذا البرنامج التعليمي؟

ج: في ملف التعليمات البرمجية الذي تخطط لإضافة محتوى HTML إليه، قم باستيراد مساحة الاسم التالية في بداية الملف:

```csharp
using Aspose.Pdf;
```

#### س: كيف يمكنني تحديد دليل المستند ومسار ملف الإخراج؟

 ج: في الكود، ابحث عن السطر`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدال`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

#### س: كيف أقوم بإنشاء كائن مستند؟

 ج: في الخطوة 4، قم بإنشاء مثيل جديد`Document` كائن عن طريق إضافة السطر التالي من التعليمات البرمجية:

```csharp
Document doc = new Document();
```

#### س: كيف يمكنني إضافة صفحة إلى المستند؟

 ج: في الخطوة 5، ستضيف صفحة جديدة إلى المستند باستخدام الملف`Add` طريقة`Pages` مجموعة:

```csharp
Page page = doc.Pages.Add();
```

#### س: كيف يمكنني ضبط محتوى HTML باستخدام DOM؟

 ج: في الخطوة 6، ستقوم بإنشاء`HtmlFragment` الكائن وقم بتعيين محتوى HTML المطلوب إليه. يتم تعيين محتوى HTML للمتغير`titel`:

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

#### س: هل يمكنني ضبط هامش محتوى HTML؟

ج: نعم، في الخطوة 7، يمكنك ضبط الهوامش السفلية والعلوية لجزء HTML حسب الحاجة:

```csharp
titel.Margin.Bottom = 10;
titel.Margin.Top = 200;
```

#### س: كيف يمكنني إضافة HTMLFragment إلى مستند PDF؟

 ج: في الخطوة 8، ستضيف`HtmlFragment` هدف (`titel`) إلى مجموعة الفقرات من الصفحة:

```csharp
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

#### س: كيف يمكنني حفظ مستند PDF الناتج؟

 ج: بعد إضافة محتوى HTML وضبط الهوامش، استخدم ملف`Save` طريقة`Document` كائن لحفظ مستند PDF:

```csharp
doc.Save(dataDir);
```

#### س: هل هناك طريقة للتأكد من نجاح العملية؟

ج: بالتأكيد، في الخطوة 10، يتم عرض رسالة نجاح مع المسار الذي تم حفظ ملف PDF فيه:

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

#### س: ما هي الوجبات الرئيسية من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، لقد تعلمت بنجاح كيفية استخدام نموذج كائن المستند (DOM) في Aspose.PDF لـ .NET لإضافة محتوى HTML إلى مستند PDF. تمكّنك هذه المعرفة من تعزيز قدرات إنشاء ملفات PDF لديك.