---
title: تعديل حقل النموذج في وثيقة PDF
linktitle: تعديل حقل النموذج في وثيقة PDF
second_title: Aspose.PDF لمرجع .NET API
description: قم بتحرير حقول النموذج في مستند PDF بسهولة باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 190
url: /ar/net/programming-with-forms/modify-form-field/
---
سنوضح لك في هذا البرنامج التعليمي كيفية تحرير حقل نموذج في مستند PDF باستخدام Aspose.PDF لـ .NET. سنشرح لك كود مصدر C# خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة 1: التحضير

تأكد من استيراد المكتبات الضرورية وتعيين المسار إلى دليل المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند

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

## الخطوة 6: احفظ المستند الذي تم تحريره

احفظ مستند PDF المعدل:

```csharp
dataDir = dataDir + "ModifyFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لتعديل حقل النموذج باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
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

في هذا البرنامج التعليمي، تعلمنا كيفية تحرير حقل نموذج في مستند PDF باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات، يمكنك التنقل بسهولة إلى حقل معين وتغيير قيمته وضبط خصائصه حسب الحاجة.


### الأسئلة الشائعة

#### س: هل يمكنني تحرير حقول نماذج متعددة داخل مستند PDF واحد باستخدام Aspose.PDF لـ .NET؟

ج: نعم، يمكنك تحرير حقول نماذج متعددة داخل مستند PDF واحد باستخدام Aspose.PDF لـ .NET. ما عليك سوى تكرار العملية لكل حقل نموذج تريد تعديله.

#### س: هل يتوافق Aspose.PDF for .NET مع كافة إصدارات .NET Framework؟

ج: نعم، Aspose.PDF for .NET متوافق مع كافة إصدارات .NET Framework، بما في ذلك .NET Core و.NET Standard.

#### س: هل يمكنني تعديل أنواع أخرى من حقول النماذج، مثل مربعات الاختيار أو أزرار الاختيار، باستخدام Aspose.PDF لـ .NET؟

ج: نعم، يدعم Aspose.PDF for .NET تعديل أنواع مختلفة من حقول النماذج، بما في ذلك مربعات الاختيار وأزرار الاختيار والمزيد.

#### س: كيف يمكنني إضافة حقول نموذج جديدة إلى مستند PDF باستخدام Aspose.PDF لـ .NET؟

 ج: لإضافة حقول نموذج جديدة إلى مستند PDF، يمكنك استخدام`Form` ملكية`Document` الصف للوصول إلى`Field` المجموعة ثم قم بإضافة حقول نموذج جديدة برمجياً.

#### س: هل يدعم Aspose.PDF for .NET لغات البرمجة الأخرى إلى جانب C#؟

ج: نعم، يدعم Aspose.PDF for .NET لغات البرمجة المختلفة، مثل VB.NET وASP.NET، بالإضافة إلى C#.