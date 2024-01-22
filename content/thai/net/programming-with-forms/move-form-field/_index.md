---
title: ย้ายฟิลด์แบบฟอร์ม
linktitle: ย้ายฟิลด์แบบฟอร์ม
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: ย้ายฟิลด์แบบฟอร์มไปรอบๆ ในเอกสาร PDF ของคุณได้อย่างง่ายดายด้วย Aspose.PDF สำหรับ .NET
type: docs
weight: 200
url: /th/net/programming-with-forms/move-form-field/
---
ในบทช่วยสอนนี้ เราจะแสดงวิธีย้ายฟิลด์แบบฟอร์มในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ทีละขั้นตอนเพื่อแนะนำคุณตลอดกระบวนการนี้

## ขั้นตอนที่ 1: การเตรียมการ

ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าไลบรารีที่จำเป็นและกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: ใส่เอกสาร

โหลดเอกสาร PDF ที่มีอยู่:

```csharp
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
```

## ขั้นตอนที่ 3: รับฟิลด์แบบฟอร์ม

รับฟิลด์แบบฟอร์มที่คุณต้องการย้าย:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## ขั้นตอนที่ 4: เปลี่ยนตำแหน่งของฟิลด์

เปลี่ยนตำแหน่งของฟิลด์แบบฟอร์มโดยการกำหนดพื้นที่สี่เหลี่ยมใหม่:

```csharp
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
```

## ขั้นตอนที่ 5: บันทึกเอกสารที่แก้ไข

บันทึกเอกสาร PDF ที่แก้ไข:

```csharp
dataDir = dataDir + "MoveFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### ตัวอย่างซอร์สโค้ดสำหรับฟิลด์ฟอร์มการย้ายโดยใช้ Aspose.PDF สำหรับ .NET 
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
// รับสนาม
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// ปรับเปลี่ยนตำแหน่งของสนาม
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
dataDir = dataDir + "MoveFormField_out.pdf";
// บันทึกเอกสารที่แก้ไข
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีย้ายฟิลด์แบบฟอร์มในเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถนำทางไปยังฟิลด์เฉพาะและเปลี่ยนตำแหน่งที่ตั้งได้ตามต้องการ


### คำถามที่พบบ่อย

#### ถาม: ฉันสามารถย้ายช่องแบบฟอร์มหลายช่องภายในเอกสาร PDF เดียวโดยใช้ Aspose.PDF สำหรับ .NET ได้หรือไม่

ตอบ: ได้ คุณสามารถย้ายช่องแบบฟอร์มหลายช่องภายในเอกสาร PDF เดียวได้โดยใช้ Aspose.PDF สำหรับ .NET เพียงทำซ้ำขั้นตอนนี้กับช่องแบบฟอร์มแต่ละช่องที่คุณต้องการย้าย

#### ถาม: การย้ายฟิลด์แบบฟอร์มจะส่งผลต่อข้อมูลหรือฟังก์ชันการทำงานที่เกี่ยวข้องหรือไม่

ตอบ: ไม่ การย้ายฟิลด์แบบฟอร์มจะไม่ส่งผลต่อข้อมูลหรือฟังก์ชันการทำงานที่เกี่ยวข้อง ฟิลด์แบบฟอร์มจะรักษาคุณสมบัติและค่าทั้งหมดไว้หลังจากถูกย้ายไปยังตำแหน่งใหม่

#### ถาม: ฉันจะระบุพิกัดที่แน่นอนสำหรับตำแหน่งใหม่ของฟิลด์แบบฟอร์มได้อย่างไร

 ตอบ: คุณสามารถระบุตำแหน่งใหม่ได้โดยใช้`Aspose.Pdf.Rectangle` คลาสที่คุณกำหนดพิกัด X และ Y ของมุมซ้ายบนและพิกัด X และ Y ของมุมขวาล่างของพื้นที่สี่เหลี่ยม

#### ถาม: Aspose.PDF สำหรับ .NET เข้ากันได้กับทั้งสภาพแวดล้อม Windows และ Linux หรือไม่

ตอบ: ได้ Aspose.PDF สำหรับ .NET เข้ากันได้กับทั้งสภาพแวดล้อม Windows และ Linux ทำให้นักพัฒนามีความยืดหยุ่นในการทำงานในระบบปฏิบัติการที่ต้องการ