---
title: ตั้งค่าข้อมูลไฟล์เป็นไฟล์ PDF
linktitle: ตั้งค่าข้อมูลไฟล์เป็นไฟล์ PDF
second_title: Aspose.PDF สำหรับการอ้างอิง .NET API
description: เรียนรู้วิธีใช้ Aspose.PDF สำหรับ .NET เพื่อตั้งค่าข้อมูลไฟล์เป็นไฟล์ PDF ด้วยคำแนะนำทีละขั้นตอนนี้
type: docs
weight: 310
url: /th/net/programming-with-document/setfileinfo/
---
หากคุณกำลังทำงานในโครงการที่ต้องจัดการไฟล์ PDF โดยใช้ Aspose.PDF สำหรับ .NET หนึ่งในคุณสมบัติที่คุณอาจต้องการใช้คือความสามารถในการตั้งค่าข้อมูลไฟล์สำหรับเอกสาร PDF ข้อมูลไฟล์ประกอบด้วยรายละเอียดต่างๆ เช่น ผู้แต่ง วันที่สร้าง คำสำคัญ วันที่แก้ไข หัวเรื่อง และชื่อเรื่อง คู่มือนี้จะแนะนำคุณตลอดขั้นตอนการตั้งค่าข้อมูลไฟล์สำหรับเอกสาร PDF โดยใช้ซอร์สโค้ด C# กับ Aspose.PDF สำหรับ .NET

## คำแนะนำทีละขั้นตอนสำหรับการตั้งค่าข้อมูลไฟล์โดยใช้ Aspose.PDF สำหรับ .NET

1. สร้างโครงการ C# ใหม่ใน Visual Studio IDE ของคุณ
2. เพิ่มการอ้างอิงไปยังไลบรารี Aspose.PDF สำหรับ .NET ในโปรเจ็กต์ของคุณ
3. สร้างออบเจ็กต์เอกสาร PDF ใหม่โดยระบุเส้นทางไปยังไฟล์ PDF ที่คุณต้องการแก้ไขข้อมูลไฟล์

## ขั้นตอนที่ 1: กำหนดเส้นทางไปยังไดเร็กทอรีเอกสาร

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: เปิดเอกสาร PDF

```csharp
// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## ขั้นตอนที่ 3: ใช้วัตถุ DocumentInfo เพื่อเข้าถึงข้อมูลไฟล์ของเอกสาร PDF

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## ขั้นตอนที่ 4: ตั้งค่าข้อมูลไฟล์ที่ต้องการโดยใช้คุณสมบัติของวัตถุ DocumentInfo

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## ขั้นตอนที่ 5: บันทึกเอกสาร PDF ที่อัปเดตไปยังตำแหน่งที่ระบุ

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## ขั้นตอนที่ 6: ตรวจสอบว่าข้อมูลไฟล์ได้รับการอัปเดตสำเร็จแล้ว

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

คุณได้ตั้งค่าข้อมูลไฟล์สำหรับเอกสาร PDF โดยใช้ Aspose.PDF สำหรับ .NET เรียบร้อยแล้ว

### ตัวอย่างซอร์สโค้ดสำหรับตั้งค่าข้อมูลไฟล์โดยใช้ Aspose.PDF สำหรับ .NET


```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// เปิดเอกสาร
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

// ระบุข้อมูลเอกสาร
DocumentInfo docInfo = new DocumentInfo(pdfDocument);

docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";

dataDir = dataDir + "SetFileInfo_out.pdf";
// บันทึกเอกสารเอาท์พุต
pdfDocument.Save(dataDir);

Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

## บทสรุป

โดยสรุป Aspose.PDF สำหรับ .NET มอบวิธีที่ง่ายและมีประสิทธิภาพในการตั้งค่าข้อมูลไฟล์สำหรับเอกสาร PDF ด้วยการทำตามขั้นตอนข้างต้น คุณสามารถตั้งค่าข้อมูลไฟล์ที่ต้องการสำหรับเอกสาร PDF ของคุณได้อย่างง่ายดายโดยใช้ซอร์สโค้ด C#

### คำถามที่พบบ่อยสำหรับการตั้งค่าข้อมูลไฟล์ในรูปแบบไฟล์ PDF

#### ถาม: ฉันสามารถตั้งค่าคุณสมบัติข้อมูลไฟล์เพิ่มเติมที่ไม่ได้กล่าวถึงในตัวอย่างได้หรือไม่

 ตอบ: ได้ คุณสามารถตั้งค่าคุณสมบัติข้อมูลไฟล์เพิ่มเติมได้โดยใช้`DocumentInfo` วัตถุใน Aspose.PDF สำหรับ .NET ที่`DocumentInfo`class จัดเตรียมคุณสมบัติต่างๆ ที่ช่วยให้คุณสามารถตั้งค่าข้อมูลเพิ่มเติม เช่น ผู้ผลิต เวอร์ชัน และคุณสมบัติที่กำหนดเอง

#### ถาม: เป็นไปได้ไหมที่จะดึงข้อมูลไฟล์จากเอกสาร PDF ที่มีอยู่

 ตอบ: ได้ คุณสามารถดึงข้อมูลไฟล์จากเอกสาร PDF ที่มีอยู่ได้โดยใช้ Aspose.PDF สำหรับ .NET เมื่อต้องการทำเช่นนี้ คุณสามารถใช้`DocumentInfo` วัตถุเพื่อเข้าถึงคุณสมบัติข้อมูลไฟล์และอ่านข้อมูลที่เก็บไว้ในเอกสาร PDF

#### ถาม: การตั้งค่าข้อมูลไฟล์จะแก้ไขเอกสาร PDF ต้นฉบับหรือไม่

ตอบ: ไม่ การตั้งค่าข้อมูลไฟล์โดยใช้ Aspose.PDF สำหรับ .NET จะไม่แก้ไขเอกสาร PDF ต้นฉบับ แต่จะสร้างเอกสาร PDF ใหม่พร้อมข้อมูลไฟล์ที่อัปเดตแทน เอกสาร PDF ต้นฉบับยังคงไม่เปลี่ยนแปลง