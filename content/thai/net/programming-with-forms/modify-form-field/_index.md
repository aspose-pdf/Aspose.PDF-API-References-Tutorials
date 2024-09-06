---
title: ปรับเปลี่ยนฟอร์มฟิลด์ในเอกสาร PDF
linktitle: ปรับเปลี่ยนฟอร์มฟิลด์ในเอกสาร PDF
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: แก้ไขฟิลด์ฟอร์มในเอกสาร PDF ได้อย่างง่ายดายด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 190
url: /th/net/programming-with-forms/modify-form-field/
---
ในบทช่วยสอนนี้ เราจะแสดงวิธีแก้ไขฟิลด์ฟอร์มในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายโค้ดต้นฉบับ C# ทีละขั้นตอนเพื่อแนะนำคุณตลอดกระบวนการนี้

## ขั้นตอนที่ 1: การเตรียมพร้อม

ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าไลบรารีที่จำเป็นและตั้งค่าเส้นทางไปยังไดเร็กทอรีเอกสารของคุณแล้ว:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดเอกสาร

โหลดเอกสาร PDF ที่มีอยู่:

```csharp
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
```

## ขั้นตอนที่ 3: รับฟิลด์แบบฟอร์ม

รับฟิลด์ฟอร์มที่คุณต้องการแก้ไข:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## ขั้นตอนที่ 4: เปลี่ยนค่าฟิลด์

เปลี่ยนค่าช่องฟอร์ม:

```csharp
textBoxField.Value = "New Value";
```

## ขั้นตอนที่ 5: แก้ไขคุณสมบัติฟิลด์

ปรับเปลี่ยนคุณสมบัติของฟิลด์ฟอร์มเพิ่มเติมตามต้องการ ตัวอย่างเช่น คุณสามารถกำหนดให้เป็นแบบอ่านอย่างเดียวได้:

```csharp
textBoxField.ReadOnly = true;
```

## ขั้นตอนที่ 6: บันทึกเอกสารที่แก้ไข

บันทึกเอกสาร PDF ที่แก้ไขแล้ว:

```csharp
dataDir = dataDir + "ModifyFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### ตัวอย่างโค้ดต้นฉบับสำหรับการแก้ไขฟิลด์ฟอร์มโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
// รับสนาม
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// ปรับเปลี่ยนค่าฟิลด์
textBoxField.Value = "New Value";
textBoxField.ReadOnly = true;
dataDir = dataDir + "ModifyFormField_out.pdf";
// บันทึกเอกสารอัพเดต
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field modified successfully.\nFile saved at " + dataDir);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการแก้ไขฟิลด์ฟอร์มในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เมื่อทำตามขั้นตอนเหล่านี้แล้ว คุณจะสามารถนำทางไปยังฟิลด์ที่ต้องการ เปลี่ยนค่า และปรับคุณสมบัติตามต้องการได้อย่างง่ายดาย


### คำถามที่พบบ่อย

#### ถาม: ฉันสามารถแก้ไขฟิลด์ฟอร์มหลายรายการภายในเอกสาร PDF เดียวโดยใช้ Aspose.PDF สำหรับ .NET ได้หรือไม่

A: ใช่ คุณสามารถแก้ไขฟิลด์ฟอร์มหลายฟิลด์ภายในเอกสาร PDF เดียวได้โดยใช้ Aspose.PDF สำหรับ .NET เพียงทำซ้ำขั้นตอนนี้สำหรับฟิลด์ฟอร์มแต่ละฟิลด์ที่คุณต้องการแก้ไข

#### ถาม: Aspose.PDF สำหรับ .NET เข้ากันได้กับ .NET Framework ทุกเวอร์ชันหรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET สามารถใช้งานได้กับ .NET Framework ทุกเวอร์ชัน รวมถึง .NET Core และ .NET Standard

#### ถาม: ฉันสามารถปรับเปลี่ยนฟิลด์ฟอร์มประเภทอื่น เช่น ช่องกาเครื่องหมายหรือปุ่มตัวเลือก โดยใช้ Aspose.PDF สำหรับ .NET ได้หรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET รองรับการแก้ไขฟิลด์ฟอร์มประเภทต่างๆ รวมถึงช่องกาเครื่องหมาย ปุ่มตัวเลือก และอื่นๆ อีกมากมาย

#### ถาม: ฉันจะเพิ่มฟิลด์ฟอร์มใหม่ลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

 ก: หากต้องการเพิ่มช่องฟอร์มใหม่ลงในเอกสาร PDF คุณสามารถใช้`Form` ทรัพย์สินของ`Document` ชั้นเรียนเพื่อเข้าถึง`Field` รวบรวมและเพิ่มฟิลด์ฟอร์มใหม่โดยโปรแกรม

#### ถาม: Aspose.PDF สำหรับ .NET รองรับภาษาการเขียนโปรแกรมอื่นนอกเหนือจาก C# หรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET รองรับภาษาการเขียนโปรแกรมต่างๆ เช่น VB.NET และ ASP.NET นอกเหนือจาก C#