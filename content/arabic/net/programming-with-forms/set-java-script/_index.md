---
title: تعيين جافا سكريبت
linktitle: تعيين جافا سكريبت
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: تعرف على كيفية استخدام Aspose.PDF لـ .NET لتعيين JavaScript في حقول النماذج في ملفات PDF.
type: docs
weight: 270
url: /ar/net/programming-with-forms/set-java-script/
---
في هذا الدليل، سنشرح خطوة بخطوة كيفية استخدام مكتبة Aspose.PDF لـ .NET لتحديد JavaScript في حقل نموذج في مستند PDF. وسنوضح لك كيفية تكوين إجراءات JavaScript لأداء عمليات محددة في حقل النص.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة على نظامك.
- مكتبة Aspose.PDF لـ .NET. يمكنك تنزيلها من موقع Aspose الرسمي.

## الخطوة 1: تكوين دليل المستندات

 الخطوة الأولى هي تكوين دليل المستندات الذي يوجد به ملف PDF الذي تريد العمل عليه. يمكنك استخدام`dataDir` متغير لتحديد مسار الدليل.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 تأكد من الاستبدال`"YOUR DOCUMENTS DIRECTORY"` مع المسار الفعلي إلى دليل المستندات الخاص بك.

## الخطوة 2: تحميل ملف PDF المدخل

 في هذه الخطوة، سنقوم بتحميل ملف PDF المدخل باستخدام`Document` فئة Aspose.PDF.

```csharp
// تحميل ملف PDF المدخل
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

تأكد من أن ملف PDF المدخل موجود في دليل المستندات المحدد.

## الخطوة 3: الوصول إلى حقل مربع النص

 لتطبيق JavaScript على حقل نص معين، نحتاج أولاً إلى الوصول إلى هذا الحقل. في هذا المثال، نفترض أن حقل النص يسمى "textbox1". استخدم`doc.Form["textbox1"]` طريقة للحصول على المقابلة`TextBoxField` هدف.

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

تأكد من وجود حقل النص المحدد في ملف PDF المدخل.

## الخطوة 4: تكوين إجراءات JavaScript

 الآن بعد أن تمكنا من الوصول إلى حقل النص، يمكننا تكوين إجراءات JavaScript المرتبطة بهذا الحقل. في هذا المثال، سنستخدم إجراءين:`OnModifyCharacter` و`OnFormat` سيتم تعريف هذه الإجراءات باستخدام`JavascriptAction` أشياء.

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

تأكد من تخصيص إجراءات JavaScript وفقًا لاحتياجاتك.

## الخطوة 5: تعيين قيمة الحقل الأولية

قبل حفظ ملف PDF الناتج، يمكننا تعيين قيمة أولية لحقل النص. في هذا المثال، سنقوم بتعيين القيمة "123" للحقل.

```csharp
field.Value = "123";
```

قم بتخصيص هذه القيمة وفقًا لاحتياجاتك.

## الخطوة 6: حفظ ملف PDF الناتج

 الآن بعد أن انتهينا من إعداد حقل النص وإجراءات JavaScript، يمكننا حفظ ملف PDF الناتج باستخدام`Save` طريقة`Document` فصل.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
// حفظ ملف PDF الناتج
doc.Save(dataDir);
```

تأكد من تحديد المسار الكامل واسم الملف لملف PDF الناتج.


### عينة من كود المصدر لـ Set Java Script باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// تحميل ملف PDF المدخل
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
// رقمين بعد النقطة
// لا يوجد فاصل
// أسلوب سلبي = ناقص
// لا يوجد عملة
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
// تعيين قيمة الحقل الأولية
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
// حفظ ملف PDF الناتج
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## خاتمة

في هذا الدليل، تعلمنا كيفية استخدام مكتبة Aspose.PDF لـ .NET لتعيين JavaScript في حقل نموذج في مستند PDF. باتباع الخطوات الموضحة، يمكنك تخصيص إجراءات JavaScript لإجراء عمليات مختلفة على حقول النص. لا تتردد في استكشاف ميزات Aspose.PDF لـ .NET بشكل أكبر لتوسيع إمكانيات معالجة ملفات PDF.


### الأسئلة الشائعة

#### س: هل يمكنني استخدام Aspose.PDF لـ .NET لإضافة JavaScript إلى عناصر نموذج أخرى، مثل مربعات الاختيار وأزرار الاختيار؟

 ج: نعم، يتيح لك Aspose.PDF for .NET إضافة JavaScript إلى عناصر نموذج مختلفة، بما في ذلك مربعات الاختيار وأزرار الاختيار والقوائم المنسدلة. يمكنك استخدام`JavascriptAction` فئة لتحديد إجراءات JavaScript لعناصر النموذج المختلفة.

#### س: هل من الممكن التحقق من صحة إدخال المستخدم باستخدام JavaScript في حقول النموذج؟

 ج: نعم، يمكنك استخدام JavaScript للتحقق من صحة إدخال المستخدم في حقول النموذج. من خلال تحديد إجراءات JavaScript مثل`OnBlur` أو`OnKeystroke` بالنسبة لحقل النموذج، يمكنك التحقق من صحة البيانات المدخلة وعرض رسائل الخطأ إذا لزم الأمر.

#### س: هل يمكنني تنفيذ وظائف JavaScript المعقدة باستخدام Aspose.PDF لـ .NET؟

 ج: نعم، يمكنك تنفيذ وظائف JavaScript المعقدة باستخدام Aspose.PDF لـ .NET. لديك المرونة في تعريف وظائف JavaScript مخصصة واستدعائها داخل`JavascriptAction`.

#### س: هل يدعم Aspose.PDF لـ .NET أحداث JavaScript بخلاف تلك المذكورة في هذا البرنامج التعليمي؟

 ج: نعم، يدعم Aspose.PDF لـ .NET مجموعة واسعة من أحداث JavaScript، بما في ذلك`OnMouseEnter`, `OnMouseExit`, `OnMouseDown` ، و`OnMouseUp`، من بين أمور أخرى. يمكنك استخدام هذه الأحداث لتشغيل إجراءات JavaScript استنادًا إلى تفاعلات المستخدم.

#### س: هل يمكنني استخدام Aspose.PDF لـ .NET لاستخراج كود JavaScript من مستندات PDF الموجودة؟

 ج: يوفر Aspose.PDF for .NET القدرة على استخراج كود JavaScript من مستندات PDF الموجودة. يمكنك استخدام`JavascriptAction` الفئة والطرق الأخرى ذات الصلة للوصول إلى إجراءات JavaScript وتحليلها في نموذج PDF.