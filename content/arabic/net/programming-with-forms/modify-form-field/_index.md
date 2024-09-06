---
title: تعديل حقل النموذج في مستند PDF
linktitle: تعديل حقل النموذج في مستند PDF
second_title: مرجع واجهة برمجة التطبيقات Aspose.PDF لـ .NET
description: يمكنك بسهولة تعديل حقول النماذج في مستند PDF باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 190
url: /ar/net/programming-with-forms/modify-form-field/
---
في هذا البرنامج التعليمي، سنوضح لك كيفية تحرير حقل نموذج في مستند PDF باستخدام Aspose.PDF for .NET. وسنشرح لك التعليمات البرمجية المصدرية للغة C# خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة 1: التحضير

تأكد من أنك قمت باستيراد المكتبات الضرورية وقمت بتعيين المسار إلى دليل المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: تحميل المستند

قم بتحميل مستند PDF الموجود:

```csharp
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
```

## الخطوة 3: الحصول على حقل النموذج

احصل على حقل النموذج الذي تريد تحريره:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## الخطوة 4: تغيير قيمة الحقل

تغيير قيمة حقل النموذج:

```csharp
textBoxField.Value = "New Value";
```

## الخطوة 5: تحرير خصائص الحقل

قم بتعديل خصائص حقل النموذج الإضافية حسب الحاجة. على سبيل المثال، يمكنك جعله للقراءة فقط:

```csharp
textBoxField.ReadOnly = true;
```

## الخطوة 6: احفظ المستند المحرر

حفظ مستند PDF المعدل:

```csharp
dataDir = dataDir + "ModifyFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### عينة من كود المصدر لتعديل حقل النموذج باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// فتح المستند
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
// احصل على حقل
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// تعديل قيمة الحقل
textBoxField.Value = "New Value";
textBoxField.ReadOnly = true;
dataDir = dataDir + "ModifyFormField_out.pdf";
// حفظ المستند المحدث
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field modified successfully.\nFile saved at " + dataDir);
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية تحرير حقل نموذج في مستند PDF باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات، يمكنك الانتقال بسهولة إلى حقل معين وتغيير قيمته وضبط خصائصه حسب الحاجة.


### الأسئلة الشائعة

#### س: هل يمكنني تحرير حقول نماذج متعددة داخل مستند PDF واحد باستخدام Aspose.PDF لـ .NET؟

ج: نعم، يمكنك تحرير حقول نماذج متعددة داخل مستند PDF واحد باستخدام Aspose.PDF for .NET. ما عليك سوى تكرار العملية لكل حقل نموذج تريد تعديله.

#### س: هل Aspose.PDF for .NET متوافق مع كافة إصدارات .NET Framework؟

ج: نعم، يعد Aspose.PDF لـ .NET متوافقًا مع جميع إصدارات .NET Framework، بما في ذلك .NET Core و.NET Standard.

#### س: هل يمكنني تعديل أنواع أخرى من حقول النموذج، مثل مربعات الاختيار أو أزرار الاختيار، باستخدام Aspose.PDF لـ .NET؟

ج: نعم، يدعم Aspose.PDF لـ .NET تعديل أنواع مختلفة من حقول النماذج، بما في ذلك مربعات الاختيار، وأزرار الاختيار، والمزيد.

#### س: كيف يمكنني إضافة حقول نموذج جديدة إلى مستند PDF باستخدام Aspose.PDF لـ .NET؟

 أ: لإضافة حقول نموذج جديدة إلى مستند PDF، يمكنك استخدام`Form` ممتلكات`Document` الصف للوصول إلى`Field` التجميع ثم إضافة حقول نموذج جديدة برمجيًا.

#### س: هل يدعم Aspose.PDF لـ .NET لغات برمجة أخرى إلى جانب C#؟

ج: نعم، يدعم Aspose.PDF for .NET لغات البرمجة المختلفة، مثل VB.NET وASP.NET، بالإضافة إلى C#.