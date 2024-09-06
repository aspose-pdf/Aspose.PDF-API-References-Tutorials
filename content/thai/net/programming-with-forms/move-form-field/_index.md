---
title: ย้ายช่องฟอร์ม
linktitle: ย้ายช่องฟอร์ม
second_title: เอกสารอ้างอิง Aspose.PDF สำหรับ API ของ .NET
description: ย้ายฟิลด์ฟอร์มไปรอบๆ เอกสาร PDF ของคุณได้อย่างง่ายดายด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 200
url: /th/net/programming-with-forms/move-form-field/
---
ในบทช่วยสอนนี้ เราจะแสดงวิธีการย้ายฟิลด์ฟอร์มในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายโค้ดต้นฉบับ C# ทีละขั้นตอนเพื่อแนะนำคุณตลอดกระบวนการนี้

## ขั้นตอนที่ 1: การเตรียมพร้อม

ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าไลบรารีที่จำเป็นและตั้งค่าเส้นทางไปยังไดเร็กทอรีเอกสารของคุณแล้ว:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดเอกสาร

โหลดเอกสาร PDF ที่มีอยู่:

```csharp
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
```

## ขั้นตอนที่ 3: รับฟิลด์แบบฟอร์ม

รับฟิลด์ฟอร์มที่คุณต้องการย้าย:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## ขั้นตอนที่ 4: เปลี่ยนตำแหน่งสนาม

เปลี่ยนตำแหน่งของฟิลด์ฟอร์มโดยการกำหนดพื้นที่สี่เหลี่ยมใหม่:

```csharp
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
```

## ขั้นตอนที่ 5: บันทึกเอกสารที่แก้ไข

บันทึกเอกสาร PDF ที่แก้ไขแล้ว:

```csharp
dataDir = dataDir + "MoveFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### ตัวอย่างโค้ดที่มาสำหรับการย้ายฟอร์มฟิลด์โดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
// รับสนาม
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// ปรับเปลี่ยนตำแหน่งสนาม
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
dataDir = dataDir + "MoveFormField_out.pdf";
// บันทึกเอกสารที่แก้ไข
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการย้ายฟิลด์ฟอร์มในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เมื่อทำตามขั้นตอนเหล่านี้แล้ว คุณจะสามารถนำทางไปยังฟิลด์ที่ต้องการและเปลี่ยนตำแหน่งตามต้องการได้อย่างง่ายดาย


### คำถามที่พบบ่อย

#### ถาม: ฉันสามารถย้ายฟิลด์ฟอร์มหลายฟิลด์ภายในเอกสาร PDF เดียวโดยใช้ Aspose.PDF สำหรับ .NET ได้หรือไม่

A: ใช่ คุณสามารถย้ายฟิลด์ฟอร์มหลายฟิลด์ภายในเอกสาร PDF เดียวได้โดยใช้ Aspose.PDF สำหรับ .NET เพียงทำซ้ำขั้นตอนนี้สำหรับฟิลด์ฟอร์มแต่ละฟิลด์ที่คุณต้องการย้าย

#### ถาม: การย้ายฟิลด์แบบฟอร์มจะส่งผลต่อข้อมูลหรือฟังก์ชันที่เกี่ยวข้องหรือไม่

ตอบ ไม่ การย้ายฟิลด์แบบฟอร์มจะไม่ส่งผลต่อข้อมูลหรือฟังก์ชันการทำงานที่เกี่ยวข้อง ฟิลด์แบบฟอร์มจะคงคุณสมบัติและค่าทั้งหมดไว้หลังจากย้ายไปยังตำแหน่งใหม่

#### ถาม: ฉันจะกำหนดพิกัดที่แน่นอนสำหรับตำแหน่งใหม่ของฟิลด์แบบฟอร์มได้อย่างไร

 A: คุณสามารถระบุตำแหน่งใหม่ได้โดยใช้`Aspose.Pdf.Rectangle` คลาสที่คุณกำหนดพิกัด X และ Y ของมุมบนซ้ายและพิกัด X และ Y ของมุมล่างขวาของพื้นที่สี่เหลี่ยม

#### ถาม: Aspose.PDF สำหรับ .NET เข้ากันได้กับสภาพแวดล้อมทั้ง Windows และ Linux หรือไม่

ตอบ: ใช่ Aspose.PDF สำหรับ .NET เข้ากันได้กับทั้งสภาพแวดล้อม Windows และ Linux ช่วยเพิ่มความยืดหยุ่นให้กับนักพัฒนาในการทำงานในระบบปฏิบัติการที่พวกเขาต้องการ