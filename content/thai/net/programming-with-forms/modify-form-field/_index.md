---
title: แก้ไขฟิลด์แบบฟอร์มในเอกสาร PDF
linktitle: แก้ไขฟิลด์แบบฟอร์มในเอกสาร PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: แก้ไขฟิลด์แบบฟอร์มในเอกสาร PDF ได้อย่างง่ายดายด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 190
url: /th/net/programming-with-forms/modify-form-field/
---
ในบทช่วยสอนนี้ เราจะแสดงวิธีแก้ไขฟิลด์แบบฟอร์มในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ทีละขั้นตอนเพื่อแนะนำคุณตลอดกระบวนการนี้

## ขั้นตอนที่ 1: การเตรียมการ

ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าไลบรารีที่จำเป็นและกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: ใส่เอกสาร

โหลดเอกสาร PDF ที่มีอยู่:

```csharp
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
```

## ขั้นตอนที่ 3: รับฟิลด์แบบฟอร์ม

รับฟิลด์แบบฟอร์มที่คุณต้องการแก้ไข:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## ขั้นตอนที่ 4: เปลี่ยนค่าฟิลด์

เปลี่ยนค่าฟิลด์แบบฟอร์ม:

```csharp
textBoxField.Value = "New Value";
```

## ขั้นตอนที่ 5: แก้ไขคุณสมบัติของฟิลด์

แก้ไขคุณสมบัติฟิลด์แบบฟอร์มเพิ่มเติมตามความจำเป็น ตัวอย่างเช่น คุณสามารถทำให้เป็นแบบอ่านอย่างเดียวได้:

```csharp
textBoxField.ReadOnly = true;
```

## ขั้นตอนที่ 6: บันทึกเอกสารที่แก้ไข

บันทึกเอกสาร PDF ที่แก้ไข:

```csharp
dataDir = dataDir + "ModifyFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### ตัวอย่างซอร์สโค้ดสำหรับแก้ไขฟิลด์ฟอร์มโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
// รับสนาม
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// แก้ไขค่าฟิลด์
textBoxField.Value = "New Value";
textBoxField.ReadOnly = true;
dataDir = dataDir + "ModifyFormField_out.pdf";
// บันทึกเอกสารที่อัปเดต
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field modified successfully.\nFile saved at " + dataDir);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีแก้ไขฟิลด์แบบฟอร์มในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถนำทางไปยังเขตข้อมูลเฉพาะ เปลี่ยนค่า และปรับคุณสมบัติของเขตข้อมูลได้ตามต้องการ


### คำถามที่พบบ่อย

#### ถาม: ฉันสามารถแก้ไขช่องแบบฟอร์มหลายช่องภายในเอกสาร PDF เดียวโดยใช้ Aspose.PDF สำหรับ .NET ได้หรือไม่

ตอบ: ได้ คุณสามารถแก้ไขช่องแบบฟอร์มหลายช่องภายในเอกสาร PDF เดียวได้โดยใช้ Aspose.PDF สำหรับ .NET เพียงทำขั้นตอนนี้ซ้ำกับช่องแบบฟอร์มแต่ละช่องที่คุณต้องการแก้ไข

#### ถาม: Aspose.PDF สำหรับ .NET เข้ากันได้กับ .NET Framework ทุกเวอร์ชันหรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET เข้ากันได้กับ .NET Framework ทุกเวอร์ชัน รวมถึง .NET Core และ .NET Standard

#### ถาม: ฉันสามารถแก้ไขฟิลด์แบบฟอร์มประเภทอื่นๆ เช่น กล่องกาเครื่องหมายหรือปุ่มตัวเลือก โดยใช้ Aspose.PDF สำหรับ .NET ได้หรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET รองรับการแก้ไขฟิลด์แบบฟอร์มประเภทต่างๆ รวมถึงช่องทำเครื่องหมาย ปุ่มตัวเลือก และอื่นๆ

#### ถาม: ฉันจะเพิ่มฟิลด์แบบฟอร์มใหม่ลงในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการเพิ่มฟิลด์แบบฟอร์มใหม่ลงในเอกสาร PDF คุณสามารถใช้ไฟล์`Form` ทรัพย์สินของ`Document` คลาสเพื่อเข้าถึง`Field` คอลเลกชันแล้วเพิ่มฟิลด์แบบฟอร์มใหม่โดยทางโปรแกรม

#### ถาม: Aspose.PDF สำหรับ .NET รองรับภาษาการเขียนโปรแกรมอื่นๆ นอกเหนือจาก C# หรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET รองรับภาษาการเขียนโปรแกรมที่หลากหลาย เช่น VB.NET และ ASP.NET นอกเหนือจาก C#