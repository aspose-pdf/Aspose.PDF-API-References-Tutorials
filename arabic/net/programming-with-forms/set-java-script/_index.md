---
title: تعيين Java Script
linktitle: تعيين Java Script
second_title: Aspose.PDF لمرجع .NET API
description: تعرف على كيفية استخدام Aspose.PDF for .NET لتعيين JavaScript في حقول النموذج في ملفات PDF.
type: docs
weight: 270
url: /ar/net/programming-with-forms/set-java-script/
---
في هذا الدليل ، سنشرح خطوة بخطوة كيفية استخدام مكتبة Aspose.PDF لـ .NET لتعريف JavaScript في حقل نموذج لمستند PDF. سنوضح لك كيفية تكوين إجراءات JavaScript لإجراء عمليات محددة في حقل النص.

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- بيئة تطوير .NET مثبتة على نظامك.
- مكتبة Aspose.PDF لـ .NET. يمكنك تنزيله من موقع Aspose الرسمي.

## الخطوة 1: تكوين دليل الوثيقة

 تتمثل الخطوة الأولى في تكوين دليل المستند حيث يوجد ملف PDF الذي تريد العمل عليه. يمكنك استخدام ال`dataDir` متغير لتحديد مسار الدليل.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 تأكد من استبدال`"YOUR DOCUMENTS DIRECTORY"` مع المسار الفعلي إلى دليل المستندات الخاص بك.

## الخطوة الثانية: تحميل ملف PDF المدخل

 في هذه الخطوة ، سنقوم بتحميل ملف PDF المدخل باستخدام الامتداد`Document` فئة Aspose.PDF.

```csharp
// قم بتحميل ملف PDF للإدخال
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

تأكد من أن ملف PDF المدخل موجود في دليل المستندات المحدد.

## الخطوة 3: الوصول إلى حقل TextBox

 لتطبيق JavaScript على حقل نصي معين ، نحتاج أولاً إلى الوصول إلى هذا الحقل. في هذا المثال ، نفترض أن حقل النص يسمى "textbox1". استخدم ال`doc.Form["textbox1"]` طريقة للحصول على المقابل`TextBoxField` هدف.

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

تأكد من وجود حقل النص المحدد في ملف PDF للإدخال.

## الخطوة 4: تكوين إجراءات JavaScript

الآن وقد وصلنا إلى حقل النص ، يمكننا تكوين إجراءات JavaScript المرتبطة بهذا الحقل. في هذا المثال ، سوف نستخدم إجراءين:`OnModifyCharacter` و`OnFormat` . سيتم تحديد هذه الإجراءات باستخدام`JavascriptAction` أشياء.

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

تأكد من تخصيص إجراءات JavaScript وفقًا لاحتياجاتك.

## الخطوة 5: تحديد قيمة الحقل الأولية

قبل حفظ ملف PDF الناتج ، يمكننا تعيين قيمة أولية لحقل النص. في هذا المثال ، سنقوم بتعيين القيمة "123" للحقل.

```csharp
field.Value = "123";
```

قم بتخصيص هذه القيمة وفقًا لاحتياجاتك.

## الخطوة 6: حفظ ملف PDF الناتج

 الآن بعد أن انتهينا من إعداد حقل النص وإجراءات JavaScript ، يمكننا حفظ ملف PDF الناتج باستخدام ملف`Save` طريقة`Document` فصل.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
// حفظ ملف PDF الناتج
doc.Save(dataDir);
```

تأكد من تحديد المسار الكامل واسم الملف لملف PDF الناتج.


### نموذج التعليمات البرمجية المصدر لـ Set Java Script باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// قم بتحميل ملف PDF للإدخال
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
// رقمان بعد النقطة
// لا يوجد فاصل
// النمط السلبي = ناقص
// لا عملة
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
// قم بتعيين قيمة الحقل الأولية
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
// احفظ ملف PDF الناتج
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## خاتمة

في هذا الدليل ، تعلمنا كيفية استخدام مكتبة Aspose.PDF لـ .NET لتعيين JavaScript في حقل نموذج لمستند PDF. باتباع الخطوات الموضحة ، يمكنك تخصيص إجراءات JavaScript لإجراء عمليات متنوعة في الحقول النصية. لا تتردد في استكشاف ميزات Aspose.PDF لـ .NET لتوسيع إمكانيات معالجة ملفات PDF.


### التعليمات

#### س: هل يمكنني استخدام Aspose.PDF لـ .NET لإضافة JavaScript إلى عناصر النموذج الأخرى ، مثل مربعات الاختيار وأزرار الاختيار؟

 ج: نعم ، يتيح لك Aspose.PDF for .NET إضافة JavaScript إلى عناصر النموذج المختلفة ، بما في ذلك مربعات الاختيار وأزرار الاختيار والقوائم المنسدلة. يمكنك استخدام ال`JavascriptAction` فئة لتعريف إجراءات JavaScript لعناصر النموذج المختلفة.

#### س: هل من الممكن التحقق من صحة إدخال المستخدم باستخدام JavaScript في حقول النموذج؟

 ج: نعم ، يمكنك استخدام JavaScript للتحقق من صحة إدخال المستخدم في حقول النموذج. من خلال تحديد إجراءات JavaScript مثل`OnBlur` أو`OnKeystroke` بالنسبة لحقل النموذج ، يمكنك التحقق من صحة البيانات المدخلة وعرض رسائل الخطأ إذا لزم الأمر.

#### س: هل يمكنني تنفيذ وظائف JavaScript المعقدة باستخدام Aspose.PDF لـ .NET؟

 ج: نعم ، يمكنك تنفيذ وظائف JavaScript المعقدة باستخدام Aspose.PDF for .NET. لديك المرونة في تحديد وظائف JavaScript المخصصة واستدعائها داخل ملف`JavascriptAction`.

#### س: هل يدعم Aspose.PDF for .NET أحداث JavaScript بخلاف تلك المذكورة في هذا البرنامج التعليمي؟

 ج: نعم ، يدعم Aspose.PDF for .NET مجموعة كبيرة من أحداث JavaScript ، بما في ذلك`OnMouseEnter`, `OnMouseExit`, `OnMouseDown` ، و`OnMouseUp`، من بين أمور أخرى. يمكنك استخدام هذه الأحداث لتشغيل إجراءات JavaScript بناءً على تفاعلات المستخدم.

#### س: هل يمكنني استخدام Aspose.PDF for .NET لاستخراج كود JavaScript من مستندات PDF الموجودة؟

 ج: يوفر Aspose.PDF for .NET القدرة على استخراج كود JavaScript من مستندات PDF الموجودة. يمكنك استخدام ال`JavascriptAction` class والطرق الأخرى ذات الصلة للوصول إلى إجراءات JavaScript وتحليلها في نموذج PDF.