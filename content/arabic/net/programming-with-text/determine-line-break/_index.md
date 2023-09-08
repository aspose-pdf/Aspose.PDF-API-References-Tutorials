---
title: تحديد فاصل الأسطر في ملف PDF
linktitle: تحديد فاصل الأسطر في ملف PDF
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية تحديد فواصل الأسطر في ملف PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 130
url: /ar/net/programming-with-text/determine-line-break/
---
سيرشدك هذا البرنامج التعليمي خلال عملية تحديد فواصل الأسطر في ملف PDF باستخدام Aspose.PDF لـ .NET. يوضح كود مصدر C# المقدم الخطوات اللازمة.

## متطلبات
قبل أن تبدأ، تأكد من أن لديك ما يلي:

- Visual Studio أو أي مترجم C# آخر مثبت على جهازك.
- Aspose.PDF لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير الحزم مثل NuGet لتثبيته.

## الخطوة 1: إعداد المشروع
1. قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك.
2. قم بإضافة مرجع إلى Aspose.PDF لمكتبة .NET.

## الخطوة 2: استيراد مساحات الأسماء المطلوبة
في ملف التعليمات البرمجية الذي تريد تحديد فواصل الأسطر فيه، أضف ما يلي باستخدام التوجيهات الموجودة في أعلى الملف:

```csharp
using Aspose.Pdf;
using System.IO;
```

## الخطوة 3: قم بتعيين دليل المستند
 في الكود، حدد السطر الذي يقول`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل حيث يتم تخزين المستندات الخاصة بك.

## الخطوة 4: إنشاء مثيل مستند جديد
 إنشاء مثيل جديد`Document` كائن عن طريق إضافة السطر التالي من التعليمات البرمجية:

```csharp
Document doc = new Document();
```

## الخطوة 5: إضافة صفحة إلى المستند
 أضف صفحة جديدة إلى المستند باستخدام`Add` طريقة`Pages`مجموعة. في الكود المقدم، يتم تعيين الصفحة الجديدة للمتغير`page`.

```csharp
Page page = doc.Pages.Add();
```

## الخطوة 6: إضافة أجزاء نصية مع فواصل الأسطر
قم بإنشاء حلقة لإضافة أجزاء نصية متعددة إلى الصفحة، تحتوي كل منها على فقرة بها فواصل أسطر.

```csharp
for (int i = 0; i < 4; i++)
{
     TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
     text.TextState.FontSize = 20;
     page.Paragraphs.Add(text);
}
```

## الخطوة 7: احفظ مستند PDF واستخرج معلومات فاصل الأسطر
 احفظ مستند PDF باستخدام`Save` طريقة`Document` هدف. ثم قم باستخراج معلومات فاصل الأسطر باستخدام الملف`GetNotifications` طريقة الصفحة المطلوبة

```csharp
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

### نموذج التعليمات البرمجية المصدر لتحديد فاصل الأسطر باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.");
	text.TextState.FontSize = 20;
	page.Paragraphs.Add(text);
}
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

## خاتمة
لقد نجحت في تحديد فواصل الأسطر في مستند PDF باستخدام Aspose.PDF لـ .NET. تم استخراج معلومات فاصل الأسطر وحفظها في ملف نصي.

### الأسئلة الشائعة

#### س: ما هو التركيز الرئيسي لهذا البرنامج التعليمي؟

ج: يركز هذا البرنامج التعليمي على إرشادك خلال عملية تحديد فواصل الأسطر في ملف PDF باستخدام مكتبة Aspose.PDF لـ .NET. يوضح كود مصدر C# المقدم الخطوات اللازمة لتحقيق ذلك.

#### س: ما هي مساحات الأسماء التي يجب علي استيرادها لهذا البرنامج التعليمي؟

ج: في ملف التعليمات البرمجية الذي تريد تحديد فواصل الأسطر فيه، قم باستيراد مساحات الأسماء التالية في بداية الملف:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### س: كيف أحدد دليل المستندات؟

 ج: في الكود، ابحث عن السطر`string dataDir = "YOUR DOCUMENT DIRECTORY";` واستبدال`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

#### س: كيف يمكنني إنشاء مثيل مستند جديد؟

 ج: في الخطوة 4، ستقوم بإنشاء نسخة جديدة`Document` الكائن باستخدام الكود المقدم.

#### س: كيف يمكنني إضافة صفحة إلى المستند؟

 ج: في الخطوة 5، ستضيف صفحة جديدة إلى المستند باستخدام الملف`Add` طريقة`Pages` مجموعة.

#### س: كيف يمكنني إضافة أجزاء نصية مع فواصل الأسطر؟

ج: في الخطوة 6، ستقوم بإنشاء حلقة لإضافة أجزاء نصية متعددة إلى الصفحة، تحتوي كل منها على فقرة بها فواصل أسطر.

#### س: كيف يمكنني حفظ مستند PDF واستخراج معلومات فاصل الأسطر؟

 ج: في الخطوة 7، ستحفظ مستند PDF باستخدام ملف`Save` طريقة`Document` هدف. بعد ذلك، ستقوم باستخراج معلومات فاصل الأسطر باستخدام ملف`GetNotifications` طريقة الصفحة المطلوبة وحفظها في ملف نصي.

#### س: ما هو الغرض من معلومات فاصل الأسطر المستخرجة؟

ج: توفر معلومات فاصل الأسطر المستخرجة تفاصيل حول فواصل الأسطر والإشعارات الموجودة في مستند PDF. يمكن أن يكون ذلك مفيدًا لتحليل وفهم كيفية تنظيم النص والفقرات داخل المستند.

#### س: ما هي الوجبات الرئيسية من هذا البرنامج التعليمي؟

ج: باتباع هذا البرنامج التعليمي، تعلمت كيفية تحديد فواصل الأسطر في مستند PDF باستخدام Aspose.PDF لـ .NET. يمكنك استخدام هذه المعرفة لاستخراج وتحليل معلومات فاصل الأسطر من ملفات PDF برمجياً.