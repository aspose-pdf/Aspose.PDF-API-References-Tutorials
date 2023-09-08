---
title: نقل حقل النموذج
linktitle: نقل حقل النموذج
second_title: Aspose.PDF لمرجع .NET API
description: انقل حقول النموذج بسهولة في مستندات PDF الخاصة بك باستخدام Aspose.PDF لـ .NET.
type: docs
weight: 200
url: /ar/net/programming-with-forms/move-form-field/
---
سنوضح لك في هذا البرنامج التعليمي كيفية نقل حقل نموذج في مستند PDF باستخدام Aspose.PDF لـ .NET. سنشرح لك كود مصدر C# خطوة بخطوة لإرشادك خلال هذه العملية.

## الخطوة 1: التحضير

تأكد من استيراد المكتبات الضرورية وتعيين المسار إلى دليل المستندات الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند

قم بتحميل مستند PDF الموجود:

```csharp
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
```

## الخطوة 3: الحصول على حقل النموذج

احصل على حقل النموذج الذي تريد نقله:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## الخطوة 4: تغيير موقع الحقل

قم بتغيير موقع حقل النموذج عن طريق تحديد منطقة مستطيلة جديدة:

```csharp
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
```

## الخطوة 5: احفظ المستند الذي تم تحريره

احفظ مستند PDF المعدل:

```csharp
dataDir = dataDir + "MoveFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### نموذج التعليمات البرمجية المصدر لنقل حقل النموذج باستخدام Aspose.PDF لـ .NET 
```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// افتح المستند
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
// احصل على حقل
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// تعديل موقع الحقل
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
dataDir = dataDir + "MoveFormField_out.pdf";
// حفظ الوثيقة المعدلة
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية نقل حقل نموذج في مستند PDF باستخدام Aspose.PDF لـ .NET. باتباع هذه الخطوات، يمكنك التنقل بسهولة إلى حقل معين وتغيير موقعه حسب الحاجة.


### الأسئلة الشائعة

#### س: هل يمكنني نقل حقول نماذج متعددة داخل مستند PDF واحد باستخدام Aspose.PDF لـ .NET؟

ج: نعم، يمكنك نقل حقول نماذج متعددة داخل مستند PDF واحد باستخدام Aspose.PDF لـ .NET. ما عليك سوى تكرار العملية لكل حقل نموذج تريد نقله.

#### س: هل سيؤثر نقل حقل النموذج على البيانات أو الوظائف المرتبطة به؟

ج: لا، لا يؤثر نقل حقل النموذج على البيانات أو الوظائف المرتبطة به. يحتفظ حقل النموذج بجميع خصائصه وقيمه بعد نقله إلى موقع جديد.

#### س: كيف يمكنني تحديد الإحداثيات الدقيقة للموقع الجديد لحقل النموذج؟

 ج: يمكنك تحديد الموقع الجديد باستخدام`Aspose.Pdf.Rectangle` فئة، حيث يمكنك تحديد إحداثيات X وY للزاوية العلوية اليسرى وإحداثيات X وY للركن الأيمن السفلي من المنطقة المستطيلة.

#### س: هل يتوافق Aspose.PDF for .NET مع بيئتي Windows وLinux؟

ج: نعم، Aspose.PDF for .NET متوافق مع كل من بيئات Windows وLinux، مما يوفر المرونة للمطورين للعمل في أنظمة التشغيل المفضلة لديهم.